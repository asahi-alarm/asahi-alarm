# Asahi ALARM

These packages are for the Arch Linux ARM (ALARM) variant of Asahi Linux.

## Install

```bash
curl https://asahi-alarm.org/installer-bootstrap.sh | sh
```

**Follow the installation instructions in the script to the letter.**

We have pre-built images for GNOME and KDE (Plasma). If you want something else, choose the Minimal install and follow
the [manual installation](manual-install.md#manual-installation) steps.

## Switch from the old asahi repo to this one

If you already have the (old) Asahi Linux Arch variant installed, you can follow the steps below
to upgrade to our new packages.

1. First import the signing key

```bash
sudo pacman-key --recv-keys 12CE6799A94A3F1B5DDFFE88F576553597FB8FEB
sudo pacman-key --lsign-key 12CE6799A94A3F1B5DDFFE88F576553597FB8FEB
```

2. Create file `/etc/pacman.d/mirrorlist.asahi-alarm` with the following contents

```bash
Server = https://github.com/asahi-alarm/asahi-alarm/releases/download/$arch
```

3. Edit `/etc/pacman.conf` and remove the `[asahi]` section then add this section:

```
[asahi-alarm]
Include = /etc/pacman.d/mirrorlist.asahi-alarm
```

You can delete `/etc/pacman.d/mirrorlist.asahi` now.

4. Install the new keyring package (will replace the legacy `asahilinux-keyring`):

```
sudo pacman -S asahi-alarm-keyring
```

5. Update

```bash
sudo pacman -Syyu
```

## Steam

We now also have steam support! Check the [Fedora Asahi announcement](https://docs.fedoraproject.org/en-US/fedora-asahi-remix/x86-support/) for details
on how it works.

If you are on our new repo, you can just

```bash
sudo pacman -Sy steam
```

This should install the steam launcher and all required components.

Notes:

- ~~on some systems `xhost +` maybe necessary first~~ fixed
- on some systems `echo "nameserver 1.1.1.1 | sudo tee -a /etc/resolv.conf` may be necessary. (pro tip: set this DNS server in your DHCP server/router)

## Contributing

If you want to help, you can find us at https://github.com/asahi-alarm or on matrix https://matrix.to/#/#asahi-alarm:matrix.org.
If you want to [donate](https://www.paypal.me/asahialarm) (web hosting isn't free), thank you!
