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

## Docker Tools
### PCredz
source: https://github.com/lgandx/PCredz

- To run the tool Example:
`docker run --net=host -v "/$(pwd)":/opt/data pcredz python3 Pcredz -f /opt/data/demo.pcapng`

### MANSPIDER
source: https://github.com/blacklanternsecurity/MANSPIDER
- To run the tool Example:
`docker run --rm -v "/$(pwd)":/root/.manspider manspider 10.129.234.173 -c 'Administrator' -u 'jbader' -p 'ILovePower333###'`


## Manual Tool installs
### PKINITtools 
Source: https://github.com/dirkjanm/PKINITtools
HTB Module Source: https://academy.hackthebox.com/module/147/section/1335

Ansible automation was taking so long to do.

```
git clone https://github.com/dirkjanm/PKINITtools.git && cd PKINITtools
python3 -m venv .venv
source .venv/bin/activate
pip3 install -r requirements.txt
pip3 install -I git+https://github.com/wbond/oscrypto.git

```
Exit Python Virtual env: `deactivate`
