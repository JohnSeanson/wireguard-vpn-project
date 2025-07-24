# Sever Setup - WireGuard VPN

This guide explains how to configure the VPN **server** (Ubuntu VM) using WireGuard.

---

## Prerequisites
- Ubuntu 20.04 or 22.04 VM
- WireGuard installed:
'''bash
sudo apt update
sudo apt install wireguard

#Generate Keys

bash

unmaskp077
wg genkey |tee privatekey | wg pubkey > publickey

* Save the privatekey and publickey values.
* You'll use:
	* privatekey in the server config
	* publickey shared with the client

#Create Server Config File

[Interface]
PrivateKey = YOUR_SERVER_PRIVATE_KEY
Address = 10.0.0.1/24
ListenPort = 51820

[Peer]
PublicKey = YOUR_CLIENT_PUBLIC_KEY
AllowedIPs = 10.0.0.2/32

#Enable IP Fowarding (If Routing Traffic)

sudo sysctl -w net.ipv4.ip_forward=1

#Start the VPN

sudo wg-quick up wg0

#Test it:

ping 10.0.0.2 #Client's VPN IP

#Stop the VPN

sudo wg-quick down wg0

