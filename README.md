# PIA NetworkManager script for Fedora

This script will setup all of the [Private Internet Access](https://privateinternetaccess.com/) servers in NetworkManager on Fedora 
for you. It will also automatically adjust SELinux contexts for the NetworkManager changes. This script exists because the PIA-provided
installer is only known to work for Debian-based machines and this provides a less-tedious way of adding the VPN hosts to a machine.

## Versions supported

* Fedora 24 Workstation.
* Fedora 25 Workstation.

This script may work for with previous versions of Fedora but it has not been tested on versions on than what is listed.

# Install

```
sudo dnf -y install wget unzip python NetworkManager-openvpn-gnome util-linux coreutils
git clone https://github.com/tlnels/pia-fedora.git
cd pia-fedora
chmod +x pia.sh
sudo ./pia.sh
```

You will be prompted for your PIA username. Enter it, and the script will execute, list the newly added connections 
and write `Done` when completed.

# Notes

This script is meant to be simple and serve as a run-once solution. If you change PIA accounts, you may run the script again
with a different username and it should work fine. Future verisons of this script are going to introduce a number of changes
to security and error handling as well as potentially more features.

Credit to this [techwords.io blog entry](https://techwords.io/configuring-pia-vpn-on-fedora/) for the idea and initial script.
