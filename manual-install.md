# Manual installation

Note: you need to have a way to connect to the internet, so you need to be able to [setup wifi](#setting-up-wifi-using-nmcli) using the commandline,
or use a USB ethernet adapter.

```bash
curl https://asahi-alarm.org/installer-bootstrap.sh | sh
```

**Follow the installation instructions in the script to the letter.**

Pick option 1 (Asahi Alarm Minimal) 

After installation you can install the desktop of your choice and the following packages:
- asahi-desktop-meta
- calamares
- asahi-calamares-configs
- feh
- xorg-server
- xf86-input-evdev
- xorg-xinput
- xorg-xinit
- xorg-xdpyinfo
- bluez-utils
- bluez-tools

You can use root/root as password to setup networking and install your desktop environment.

After installing your desktop, enable calamares, network manager, bluetooth and your login manager:
```
systemctl enable calamares.service
systemctl enable <gdm|sddm|other>
systemctl enable bluetooth
```

Now reboot to get into our calamares setup utility to setup your user, timezone, etc. After calamares has finished, the root user will be disabled.

### Setting up wifi using nmcli
- `nmcli device wifi connect <SSID> password <password>`

