# Network Architecture

I used a secure local network to connect models between a server running low intensity models, my main PC running high intensity models, and my laptop as an aditional usage point. The PC and server are connected via ethernet and a network switch for high speed communication, and this also allows for improved wireless speeds to my laptop when using it. None of the network is exposed publicly so that it is secure as a local network. There is then a further firewall and vpn to ensure the local network is further secured.

## Hardware

|Component|Purpose|
|--------|---------|
|Debian |AI infrastructure|
|Main PC |Primary Development Workstation|
|Laptop |Secondary Mobile Development|
|Tailscale |Secure Local Networking|
|Router |Local Network Connectivity|
|Switch |Ethernet Connectivity|

## Networking

### IP Addressing

I assigned a static IP to ensure I can always access the server. I did this via a reserved router IP. This additionally makes it easier to identify the server as the name for the port is assigned in the router memory as well.

Then with tailscale installed on all devices with access, the static IP means this connection is consistent. The IPs then change slightly to have the form:
```bash
100.x.x.x
```
