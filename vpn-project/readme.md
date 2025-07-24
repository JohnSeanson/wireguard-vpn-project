#WireGuard VPN on Ubuntu (VitualBox)

This project sets up a secure VPN tunnel between two Ubuntu VMs using WireGuard. One acts as the VPN server and one as the client.

##Technologies Used
- Ubuntu 22.04 (Server & Client)
- Wireguard
- Oracle VirtualBox

## How It Works
- VPN tunnel is configured using 'wg0.conf' files
- Secure communication between the two VMs
- Key pairs for authentication
- Manual setup for learning purposes

## Setup Steps
1. Install WireGuard: 'sudo apt install wireguard'
2. Generate Keys on both machines
3. Configure the server and client 'wg0.conf' files
4. Bring up the interface: 'sudo wg-quick up wg0'
5. Test connection with 'ping'

## Security Note
Config files have been sanitized. Never commit private keys or sensitive IPs to public repositories.

## What I learned
- VPN fundementals
- WireGuard configuration
- Linux networking basics
- GitHub project workflow

## Files
- 'wg0.conf' - Sample WireGuard configuration
- 'client-setup.md' - Client installtion steps
- 'server-setup.med' - Server installtion steps

---

*This is part of my learning journaey and portfolio.*


