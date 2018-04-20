---
layout: post
title: "Linux service - systemd"
date: 2018-04-16
categories: Bitcoin
---

cd /home
adduser --system bitcoin --group
chown -R bitcoin:bitcoin /home/bitcoin/
chmod -R og-rwx /home/bitcoin/


wget -P /home/bitcoin https://raw.githubusercontent.com/bitcoin/bitcoin/master/contrib/debian/examples/bitcoin.conf

wget -P /lib/systemd/system/ https://raw.githubusercontent.com/bitcoin/bitcoin/master/contrib/init/bitcoind.service


nano /lib/systemd/system/bitcoind.service

Binary: /usr/bin/bitcoind

readable to only bitcoin
Configuration file: /home/bitcoin/bitcoin.conf
chmod ugo-rwx /home/bitcoin/bitcoin.conf && chmod u+r /home/bitcoin/bitcoin.conf

readable to only bitcoin
Data directory: /home/bitcoin
chmod ugo-rwx /home/bitcoin/ && chmod u+r /home/bitcoin/


PID file: /home/bitcoin/testnet3/bitcoind.pid (systemd)



ln -s /lib/systemd/system/bitcoind.service bitcoind.service

