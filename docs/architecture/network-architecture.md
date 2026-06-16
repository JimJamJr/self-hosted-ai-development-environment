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

### Security Architecture

#### SSH Keys

I used SSH keys to link my laptop, PC, and the server so that, especially during install, I didn't need to consistently input the user password. This also makes the connection more secure betweent he network nodes. The password could be leaked, or bruteforced, but the ssh keys make communications far more secure. This was simple to do by generating the keys for the nodes and then sharing the public keys between them.

#### Firewall

I installed and actived UFW on the server for an aditional level of security for the server network. I then allowed only the ports for Open WebUI, Ollama, and SSH.

#### Tailscale

I decied to use Tailscale VPN for an extra level of local network security. This is mainly because there are many people using my home network so isolating this network makes it more secure. It also removed the need for port forwarding and encrypts the connection for extra safety. The install was easy, only needing tailscale installing on each device then verifying with each device.

#### Service access

Using tailscale, each server port can be accessed securely using the IPs asigned by tailscale and the usual port. This ensures the secure, encrypted access.
