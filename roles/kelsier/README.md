# Kelsier Notes

Things I can't ansible but want to remember:
- Need to first install `openssh` and configure basic step
- https://wiki.archlinux.org/title/Wake-on-LAN#Enable_WoL_on_the_network_adapter
- `nmcli con show` and then `nmcli c show "NAME_SHOWN" | grep 802-3-ethernet.wake-on-lan`
    - Finally `nmcli c modify "NAME_SHOWN" 802-3-ethernet.wake-on-lan magic`
- Install zsh4humans: `sh -c "$(wget -O- https://raw.githubusercontent.com/romkatv/zsh4humans/v5/install)"`
    - Handles installing zsh and the basic plugins.  Can't automate it.