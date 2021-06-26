{% include disclaimer.html translated="yes" translationOutdated="no" %}

# MKEcoind

`MKEcoind` is de daemon-software die onderdeel uitmaakt van de MKEcoin-code. Het is een console-programma waarmee de blockchain wordt beheerd. Terwijl een Bitcoin-portemonnee zowel een account als de blockchain beheert, worden deze functies in MKEcoin gescheiden: `MKEcoind` beheert de blockchain en `MKEcoin-wallet-cli` beheert het account.

Deze handleiding gaat ervan uit dat je al een VPS-account hebt ingesteld en SSH gebruikt als tunnel om te communiceren met de serverconsole.

## Linux, 64-bits (Ubuntu 16.04 LTS)

### Zorg dat poort 18080 open staat

`MKEcoind` gebruikt deze poort om te communiceren met andere nodes op het MKEcoin-netwerk.

Voorbeeld als je `ufw` gebruikt: `sudo ufw allow 18080`
Voorbeeld als je `iptables` gebruikt: `sudo iptables -A INPUT -p tcp --dport 18080 -j ACCEPT`

### Download de huidige MKEcoin Core-binaries

    wget https://downloads.getMKEcoin.org/linux64

### Maak een directory aan en pak de bestanden uit.

    mkdir MKEcoin
    tar -xjvf linux64 -C MKEcoin

### Start de daemon

    cd MKEcoin
    ./MKEcoind

### Opties:

Een lijst met alle opties en instellingen weergeven:

    ./MKEcoind --help

De daemon starten als een achtergrondproces:

    ./MKEcoind --detach

De uitvoer van `MKEcoind` als achtergrondproces loggen:

    tail -f ~/.bitMKEcoin/bitMKEcoin.log

De VPS beveiligen met automatische updates:

https://help.ubuntu.com/community/AutomaticSecurityUpdates


