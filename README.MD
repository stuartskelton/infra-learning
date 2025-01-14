# Introduction

This repo contains the code used to deploy and managing my various LXC's on Proxmox.  Ansible is the main way I deploy things.

A huge HUGE thanks to IronicBadger/AlexKTZ for his [infra GitHub repo](https://github.com/IronicBadger/infra).  I learned a ton poking around that repo and some of the things are copied straight from there, so credit where credit is due.

# Explanation of Shards/Names:

Most of my servers are named after Shards of Adonalsium from my favorite fantasy series by Brandon Sanderson.  So if you look at my roles you'll see a pattern.

* **Adonalsium** - Primary Proxmox Node
* **Autonomy** - Home Automation
* **Cultivation** - Misc. Media
* **Dominion** - Ansible primary host
* **Endowment** - Media distribution/collection
* **Honor** - DMZ/Primary Adguard/Wireguard
* **Omada** - Runs Omada controller for Wifi
* **Preservation** - Databases
* **Valor** - Backup Adguard
* **Ambition** - Cloud VPS

# First Deploy instructions:

`make install` - Installs a github hook to prevent uploading an unencrypted Ansible vault file, adds the Ansible Galaxy roles, and sets up the Ansible vault password

`make boostrap` - Sets up the hosts with a main user and an ansible user that can run sudo without a password

`make bootstrap_desktop host={{host_name}}` - Bootstraps the indicated desktop

`make proxmox` - Creates all LXCs, sets up disks on Proxmox host

`make build host={{host_name}}` - Sets up the various machines (host_name is a variable for the hostname)

# Ansible Vault

`make encrypt` - Encrypts the Ansible vault
`make decrypt` - Decrypts the Ansible vault

# Git

`make git` - Runs the gitupdate script

# Updates

`make update` - Runs apt update and apt upgrade on the servers, and pushes an updated docker-compose.yml file
`make docker` - Runs docker-compose pull {{ containers }} and docker-compose up -d {{ container }} on host and containers specified

### If you appreciate my work, please consider buying me a beer (or coffee, or whatever)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/E1E5796VZ)
