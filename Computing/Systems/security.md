Security Terms
--------------

- Authentication: Identity Establishment
- Confidentiality: message can be read only by intended parties
- Integrity: Is the data untampered.
- Non-repudiate: Proof that the message is sent by someone
- Availability:
- Authorization: Is someone authorized to access the data.

MAC
---

-Message Authentication Code, MAC is a message used to check the authenticity of a message.
-A keyed MAC provides additional authenticity check as well.

DH
--

- Diffe-Hellman
- Standard Key Exchange protocol
- Discreet log and Elliptic Curve DH.
- Discreet log
  - Server sends N,g and g^b mod N.
  - Client generates a and sends g^a mod N.
  - Now both client and server have g^ab mod N.
- Both get a secret key without revealing details.

TLS/SSL
-------

- A simple protocol for authentication and encryption.
  - Client sends hello
  - Server sends hello and certificate
  - Client sends pre-message key
  - Using pre-message key, client and server obtain a derived key

- This does not have **perfect forward secrecy**. For perfect forward secrecy, we need ephemeral keys using DH algorithm.

OpenVPN
-------

- Creates a tunnel using UDP/TCP to the remote server, all communication through this is now encrypted.
- Created a virtual interface which uses this tunnel.
- Any packet sent through the interface is tunnelled.
- *tun* is a point to point interface
- *tap* is an ethernet subnet

Bridging
--------

- Connecting of Physical and Virtual Ethernet interfaces under the same subnet.
  - brctrl is a Linux utility that helps accomplish the same

Tunneling
---------

- Carrying the payload of a different level in the OSI standard at some other level.
