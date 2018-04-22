---
layout: post
title: "Cryptography - Digital signatures"
date: 2018-03-30
categories: Cryptography
---

<h2>How to digitally sign a document using Openssl on Linux.</h2>
<br>
<b>#generate a public and private RSA key pair</b>
<br>openssl genrsa -out private.key 2048 openssl rsa -pubout -in private.key -out public.key

<b>#Assign correct file permissions</b>
<br>chmod 700 ~/.ssh; chmod 600 ~/.ssh/private.key; chmod 600 ~/.ssh/public.pub

<b>#Hash the message. Encrypt the hash with the private key</b>
<br>openssl dgst -sha256 -sign private.key -out signature.bin message.txt

<b>#Decrypt the digital signature. Hash the message and compare both hashes.</b>
<br>openssl dgst -sha256 -verify public.key -signature signature.bin message.txt
![My helpful screenshot]({{ "/assets/screenshot.jpeg" | absolute_url }})
