{% include disclaimer.html translated="no" translationOutdated="no" %}

# MKEcoind

`MKEcoind` is the @daemon software that ships with the MKEcoin tree. It is a console program, and manages the blockchain. While a bitcoin wallet manages both an account and the blockchain, MKEcoin separates these: `MKEcoind` handles the blockchain, and `MKEcoin-wallet-cli` handles the account.

This guide assumes you have already set up your VPS account and are using SSH to tunnel into the server console.

## Linux, 64-bit (Ubuntu 16.04 LTS)

### Make sure that port 18080 is open

`MKEcoind` uses this port to communicate with other nodes on the MKEcoin network.

Example if using `ufw`: `sudo ufw allow 18080`
Example if using `iptables`: `sudo iptables -A INPUT -p tcp --dport 18080 -j ACCEPT`

### Download the current MKEcoin Core binaries

    wget https://downloads.getMKEcoin.org/linux64

### Make a directory and extract the files.

    mkdir MKEcoin
    tar -xjvf linux64 -C MKEcoin

### Launch the daemon

    cd MKEcoin
    ./MKEcoind

### Options:

Show list of all options and settings:

    ./MKEcoind --help

Launch the daemon as a background process:

    ./MKEcoind --detach

Monitor the output of `MKEcoind` if running as daemon:

    tail -f ~/.bitMKEcoin/bitMKEcoin.log

Keep the VPS secure with autoupdate:

https://help.ubuntu.com/community/AutomaticSecurityUpdates


