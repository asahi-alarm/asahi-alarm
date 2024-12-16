# Asahi ALARM repo

These packages are for the Arch linux ARM variant of Asahi Linux.

## Switch from the old asahi repo to this one

First import the signing key

```bash
sudo pacman-key --recv-keys 12CE6799A94A3F1B5DDFFE88F576553597FB8FEB
sudo pacman-key --lsign-key 12CE6799A94A3F1B5DDFFE88F576553597FB8FEB
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

Install the new keyring package (will replace the legacy `asahilinux-keyring`):

```
sudo pacman -S asahi-alarm-keyring
```

Update

```bash
sudo pacman -Syyu
```
