{% include disclaimer.html translated="yes" translationOutdated="yes" %}

Avec [Qubes](https://qubes-os.org) et [Whonix](https://whonix.org) vous pouvez disposer d'un portefeuille MKEcoin hors connexion fonctionnant sur un système virtuel isolé du démon MKEcoin dont tout le trafic est forcé à passer à travers [Tor](https://torproject.org).

Qubes permet de créer facilement des machines virtuelles pour différents besoins. Tout d'abord, vous crérez une station de travail Whonix sans réseau pour le portefeuille. Ensuite, une seconde station de travail Whonix pour le démon qui utilisera votre passerelle Whonix comme réseau de machine virtuelle. La communication dentre le portefeuille et le démon pourra être réalisée en utilisant Qubes [qrexec](https://www.qubes-os.org/doc/qrexec3/).

Il s'agit d'une approche plus sûre que d'autres solutions routant les appels de procédure distantes du portefeuille à travers un service Tor caché, ou utilisant une isolation physique mais disposant toujours du réseau pour le raccordement au démon. De cette manière vou sn'avez besoin d'aucune connectivité réseau sur le portefeuille, vous préserver les ressources du réseau Tor et vous minimisez la latence.


## 1. [Créer une machine virtuelle applicative Whonix](https://www.whonix.org/wiki/Qubes/Install):

+ En utilisant un modèle Whonix de station de travail, créez deux stations de travail comme suit :

  - La première station de travail sera utilisé pour le portefeuille, on s'y réfèrera en tant que `MKEcoin-wallet-ws`. Vous aurez `NetVM` définit à `none`.

  - La seconde station de travail sera pour le démon `MKEcoind`, on s'y réfèrera en tant que `MKEcoind-ws`. Vous aurez `NetVM` définit sur la passerelle Whonix `sys-whonix`. Before moving on, make sure this workstation has enough private storage. You can estimate how much space you need by checking the size of the [raw blockchain]({{ site.baseurl }}/downloads/#blockchain). Keep in mind that the blockchain will take up more space with time.

## 2. Dans la machine virtuelle applicative `MKEcoind-ws`:

+ Créez un fichier `systemd`.

```
user@host:~$ sudo nano /home/user/MKEcoind.service
```

Collez-y le contenu suivant :

```
[Unit]
Description=MKEcoin Full Node
After=network.target

[Service]
User=user
Group=user

Type=forking
PIDFile=/home/user/.bitMKEcoin/MKEcoind.pid

ExecStart=/usr/local/bin/MKEcoind --detach --data-dir=/home/user/.bitMKEcoin \
    --no-igd --pidfile=/home/user/.bitMKEcoin/MKEcoind.pid \
    --log-file=/home/user/.bitMKEcoin/bitMKEcoin.log --p2p-bind-ip=127.0.0.1

Restart=always
PrivateTmp=true

[Install]
WantedBy=multi-user.target
```

+ Configurez le lancement du démon `MKEcoind` au démarrage en éditant le fichier `/rw/config/rc.local`.

```
user@host:~$ sudo nano /rw/config/rc.local
```

Ajoutez les lignes suivantes à la fin du fichier :

```
cp /home/user/MKEcoind.service /lib/systemd/system/
systemctl start MKEcoind.service
```

Rendez le fichier exécutable.

```
user@host:~$ sudo chmod +x /rw/config/rc.local
```

+ Créez le fichier d'action d'appel de procédure distante.

```
user@host:~$ sudo mkdir /rw/usrlocal/etc/qubes-rpc
user@host:~$ sudo nano /rw/usrlocal/etc/qubes-rpc/user.MKEcoind
```

Ajoutez cette ligne :

```
socat STDIO TCP:localhost:18081
```

+ Éteignez `MKEcoind-ws`.

## 3. Dans la machine virtuelle applicative `MKEcoin-wallet-ws`:

+ Éditez le fichier `/rw/config/rc.local`.

```
user@host:~$ sudo nano /rw/config/rc.local
```

Ajoutez-y la ligne suivante à la fin :

```
socat TCP-LISTEN:18081,fork,bind=127.0.0.1 EXEC:"qrexec-client-vm MKEcoind-ws user.MKEcoind"
```

Rendez le fichier exécutable.

```
user@host:~$ sudo chmod +x /rw/config/rc.local
```

+ Éteignez `MKEcoin-wallet-ws`.

## 4. Dans `dom0`:

+ Créez le fichier `/etc/qubes-rpc/policy/user.MKEcoind`:

```
[user@dom0 ~]$ sudo nano /etc/qubes-rpc/policy/user.MKEcoind
```

Ajoutez la ligne suivante :

```
MKEcoin-wallet-ws MKEcoind-ws allow
```
