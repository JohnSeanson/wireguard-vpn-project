# Client Setup - WireGuard VPN

This guide explains how to configure the VPN **client** (Ubuntu VM) using WireGuard.

---

## Prerequisites
- Ubuntu 20.04 or 22.04 VM
- WireGuard installed:
'''bash
sudo apt update
sudo apt install wireguard

# Generate Keys

unmask 077

wg genkey | tee privatekey | wg pubkey > publickey

* Save the privatekey and publickey values.
* You'll use:
	* privatekey in the client config
	* publickey shared with the server

# Create the Client config file

[Interface]
PrivateKey = YOUR_CLIENT_PRIVATE_KEY
Address = 10.0.0.2/24

[Peer]
PublicKey = YOUR_SERVER_PUBLIC_KEY
Endpoint = your.server.ip:51820
AllowedIPs = 0.0.0.0/0
Persistentkeepalive = 25

#Replace placholder values with actual keys/IPs

#Start the VPN

Bash

sudo wg-quick up wg0

#Test it:

bash

ping 10.0.0.1 #Server's VPN IP

#Stop the VPN

bash

sudo wg-quick down wg0
