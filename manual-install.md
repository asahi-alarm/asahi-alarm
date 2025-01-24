# Manual installation

Note: you need to have a way to connect to the internet, so you need to be able to [setup wifi](#setting-up-wifi-using-nmcli) using the commandline,
or use a USB ethernet adapter.

```bash
curl https://asahi-alarm.org/installer-bootstrap.sh | sh
```

**Follow the installation instructions in the script to the letter.**

Pick option 1 (Asahi Alarm Minimal)

You can use root/root as password to setup networking and install your desktop environment.

After installation you can install the desktop of your choice and the following package: asahi-desktop-meta

After installing your desktop, enable bluetooth and your login manager:

```
systemctl enable <gdm|sddm|other>
systemctl enable bluetooth
```

Add a non-priviledged user and disable the root user.

### Setting up wifi using nmcli

- `nmcli device wifi connect <SSID> password <password>`
