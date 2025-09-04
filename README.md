# parrot-build
Ansible Scripts to Build Parrot OS

# Instructions
* Start with Parrot HTB Edition
* Install Ansible (`sudo apt install ansible`)
* Clone and enter the repo (`git clone https://github.com/Buzzcola81/parrot-build.git && cd parrot-build/`)
* get a sudo token (`sudo whoami`)
* Run ansible (`ansible-playbook main.yml`) add -vvv for verbose logging to troubleshoot.

** If having issues with ansible may have to look into installing with pip install ansible, apt has an older copy **

# HTB VPN Connection setup (Non Ansible task)
* Generate/Download the VPN connection file from HTB
* Load it onto the VM (Desktop)
* Run the command `sudo nmcli connection import type openvpn file /home/buzzcola/Desktop/academy-regular.ovpn`

## VPN Command Reference:
- List VPN Connections
`nmcli connection show`

- Create VPN Connection from file:
`sudo nmcli connection import type openvpn file <File Path>`
EG: `sudo nmcli connection import type openvpn file /home/buzzcola/Desktop/academy-regular.ovpn`
Note: VPN Connection Name will be created based file name.

- Delete VPN connection by name
`sudo nmcli connection delete <VPN NAME>`

- Rename VPN Connection Name
`sudo nmcli connection modify <Current VPN NAME> con-name <New VPN NAME>`

