---
layout: post
title: "Bitcoin - install and run a regtest network"
date: 2018-05-04
categories: Bitcoin
---



#GITHUB
#https://github.com/gavincotter

#HOMEPAGE
#https://gavincotter.github.io


#ADD SYSTEM USER TO RUN THE BITCOIND DAEMON
adduser --system --group --home /home/bitcoin bitcoin

#GET BITCOIN.CONF 
wget -P /etc/ https://raw.githubusercontent.com/gavincotter/playground/master/bitcoin.conf

#GET BITCOIND.SERVICE
wget -P /lib/systemd/system/ https://raw.githubusercontent.com/gavincotter/playground/master/bitcoind.service

#MAKE SYMBOLIC LINK FOR SYSTEMD
ln -s /lib/systemd/system/bitcoind.service /etc/systemd/system/bitcoind.service

#Download the bitcoin 
wget -P /tmp/ https://bitcoin.org/bin/bitcoin-core-0.16.0/bitcoin-0.16.0-x86_64-linux-gnu.tar.gz

#Extract files from archive and decompress to the current directory
tar xzf /tmp/bitcoin-0.16.0-x86_64-linux-gnu.tar.gz

#COPY FILES AND SET ATTRIBUTES
su -c 'install -m 0755 -o root -g root -t /usr/bin /tmp/bitcoin-0.16.0/bin/*'

#SET NEW OWNERSHIP AND PERMISSIONS
chown bitcoin:bitcoin /etc/bitcoin.conf
chmod a-rwx /etc/bitcoin.conf
chmod ug+r /etc/bitcoin.conf

#START BITCOIND DAEMON
systemctl start bitcoind

#ENABLE USER(S) READ ACCESS TO BITCOIN.CONF
adduser bitcoin user
