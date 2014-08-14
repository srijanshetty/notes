Security Terms
==============
-Authentication: Identity Establishment
-Confidentiality: message can be read only by intended parties
-Non-repudiate: Proof that the message is sent by someone

MAC
===
-Message Authentication Code, MAC is a message used to check the authenticity of a message.
-A keyed MAC provides additional authenticity check as well.

DH
==
-Diffe-Hellman
-Standard Key Exchange protocol
-Discreet log and Elliptic Curve DH.
-Discreet log
    -Server sends N,g and g^b mod N.
    -Client generates a and sends g^a mod N.
    -Now both client and server have g^ab mod N.
-Both get a secret key without revealing details.

TLS/SSL
=======
-A simple protocol for authentication and encryption.
    -Client sends hello
    -Server sends hello and certificate
    -Client sends pre-message key
    -Using pre-message key, client and server obtain a derived key

-This does not have perfect forward secrecy. For perfect forward secrecy, we need
 ephemeral keys using DH algorithm.

