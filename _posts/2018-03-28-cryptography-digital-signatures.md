---
layout: post
title: "Cryptography - Digital signatures"
date: 2018-03-30
categories: Cryptography
---

<h2>How to digitally sign a document using Openssl on Linux.</h2>
<pre>
#generate a public and private RSA key pair
openssl genrsa -out private.key 2048
openssl rsa -pubout -in private.key -out public.key

#Assign correct file permissions
chmod 700 ~/.ssh; chmod 600 ~/.ssh/private.key; chmod 600 ~/.ssh/public.pub

#Hash the message. Encrypt the hash with the private key
openssl dgst -sha256 -sign private.key -out signature.bin message.txt

#Decrypt the digital signature. Hash the message and compare both hashes.
openssl dgst -sha256 -verify public.key -signature signature.bin message.txt</pre>
![My helpful screenshot]({{ "/assets/screenshot.jpeg" | absolute_url }})
