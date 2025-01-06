# Asahi ALARM

These packages are for the Arch Linux ARM (ALARM) variant of Asahi Linux.

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

## New installs

We have created new installer images, we are investigating hosting options at the moment.
The files are too big to host on github releases, and free hosting plans would quickly
run into bandwidth issues.

For the adventurous, we have a base installer image up, desktop images are too big.
There are a few manual steps, outlined [here](manual-install.md)

## Contributing

If you want to help, you can find us at https://github.com/asahi-alarm or on matrix https://matrix.to/#/#asahi-alarm:matrix.org
