{% include disclaimer.html translated="yes" translationOutdated="no" %}

# MKEcoind

`MKEcoind` jest oprogramowaniem daemona, które współpracuje z MKEcoin. To program konsoli zarządzający łańcuchem bloków. Podczas gdy portfel Bitcoina zarządza zarówno kontem, jak i łańcuchem bloków, MKEcoin rozdzielił je, aby `MKEcoind` operował łańcuchem, a `MKEcoin-wallet-cli` kontem.

Ten przewodnik zakłada, że już założyłeś swoje konto VPS i używasz SSH do tunelowania do konsoli serwerowej.

## Linux, 64-bit (Ubuntu 16.04 LTS)

### Upewnij się, że port 18080 jest otwarty

`MKEcoind` korzysta z tego portu do komunikacji z innymi węzłami w sieci MKEcoin.

Przykład przy użyciu `ufw`: `sudo ufw allow 18080`
Przykład przy użyciu `iptables`: `sudo iptables -A INPUT -p tcp --dport 18080 -j ACCEPT`

### Ściągnij aktualne pliki binarne Centrum MKEcoin

    wget https://downloads.getMKEcoin.org/linux64

### Załóż folder i wypakuj pliki

    mkdir MKEcoin
    tar -xjvf linux64 -C MKEcoin

### Uruchom daemona

    cd MKEcoin
    ./MKEcoind

### Opcje:

Pokaż całą listę opcji i ustawień:

    ./MKEcoind --help

Uruchom daemona w tle:

    ./MKEcoind --detach

Monitoruj rezultaty `MKEcoind`, jeśli daemon jest uruchomiony:

    tail -f ~/.bitMKEcoin/bitMKEcoin.log

Utrzymuj VPS w bezpieczeństwie, korzystając z autoaktualizacji:

https://help.ubuntu.com/community/AutomaticSecurityUpdates


