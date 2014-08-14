OpenVPN
=======
-Creates a tunnel using UDP/TCP to the remote server, all communication
 through this is now encrypted.
-Created a virtual interface which uses this tunnel.
-ANy packet sent through the interface is tunnelled.
-tun is a point to point interface
-tap is an ethernet subnet

Bridging
=======
-Connecting of Physical and Virtual Ethernet interfaces under the same subnet.
    -brctrl is a linux utility that helps accomplish the same

Tunneling
=========
-Carrying the payload of a different level in the OSI standard at some other level.
