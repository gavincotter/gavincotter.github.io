---
layout: post
title: "Bitcoin - testnet"
date: 2018-04-16
categories: Bitcoin
---



Testnet—Bitcoin’s Testing Playground

Testnet is the name of the test blockchain, network, and currency that is used for testing purposes. 
The testnet is a fully featured live P2P network, with wallets, test bitcoins (testnet coins), mining,and all the other features of mainnet.
There are really only two differences: testnet coins are meant to be worthless and mining difficulty should be low enough that anyone can mine
testnet coins relatively easily (keeping them worthless).

As of January 2018 the size of the data on disk was 14GB, containing data for about 6 years worth of testnet activity.


Install Bitcoin

Download the bitcoin binary files to the current directory
wget https://bitcoin.org/bin/bitcoin-core-0.16.0/bitcoin-0.16.0-x86_64-linux-gnu.tar.gz


tar
archiving program
f name of archive to operate on
x extract files from an archive
z filter archive through gzip

Extract files from archive and decompress to the current directory
tar xzf bitcoin-0.16.0-x86_64-linux-gnu.tar.gz


su
substitute user. Assume the identity of another user , root by default.
-c execute the command that follows as the new user

install
copy files and set attributes
-m permission mode
-o owner
-g group
-t target directory source

su -c 'install -m 0755 -o root -g root -t /usr/bin bitcoin-0.16.0/bin/*'

create a service account
adduser --system btc

