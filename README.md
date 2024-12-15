# Asahi ALARM repo

These packages are for the Arch linux ARM variant of Asahi Linux.

## Switch from the old asahi repo to this one

First import the signing key

```bash
sudo pacman-key --recv-keys 1F35A37F9D85CBC2B74F595E37CE6162C969C50E
sudo pacman-key --lsign-key 1F35A37F9D85CBC2B74F595E37CE6162C969C50E
```

Create file `/etc/pacman.d/mirrorlist.asahi-alarm` with the following contents

```bash
Server = https://github.com/asahi-alarm/asahi-alarm/releases/download/$arch
```

Edit `/etc/pacman.conf` and remove the `[asahi]` section then add this section:

```
[asahi-alarm]
Include = /etc/pacman.d/mirrorlist.asahi-alarm
```

You can delete `/etc/pacman.d/mirrorlist.asahi` now.

Remove the old keyring package:

```
sudo pacman -Rdd asahilinux-keyring
```

Update

```bash
sudo pacman -Syyu
```
