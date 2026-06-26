# Building MikuOS

MikuOS is currently built from an Archiso profile with local MikuOS packages.

## Requirements

Use Arch Linux or an Arch-based system with:

```bash
sudo pacman -S archiso base-devel git pacman-contrib
```

Optional but useful:

```bash
sudo pacman -S qemu-desktop virt-manager
```

## Repository layout

```text
archiso/                  Archiso profile
packages/                 MikuOS package sources
repo/                     Local package repo used by archiso
out/                      Built ISO output
work/                     Temporary archiso build directory
installer-packages.txt    Planned installed-system package list
```

## Build local packages

Build the MikuOS branding package:

```bash
cd ~/MikuOS/packages/mikuos-branding
makepkg -f
cp *.pkg.tar.zst ~/MikuOS/repo/
```

Build the desktop config package:

```bash
cd ~/MikuOS/packages/mikuos-desktop-config
makepkg -f
cp *.pkg.tar.zst ~/MikuOS/repo/
```

Update the local repo database:

```bash
cd ~/MikuOS
repo-add -R repo/mikuos.db.tar.gz repo/*.pkg.tar.zst
```

Make sure the custom packages are listed in:

```text
archiso/packages.x86_64
```

## Build the ISO

From the project root:

```bash
cd ~/MikuOS
sudo rm -rf work
sudo mkarchiso -v -w work -o out archiso
```

The ISO will be created in:

```text
out/
```

## Test checklist

Boot the ISO in a VM and check:

- ISO boots
- KDE Plasma loads
- live user autologin works
- network works
- `sudo whoami` returns `root`
- wallpaper applies
- Plymouth splash appears
- Fastfetch displays MikuOS branding
- Calamares opens

Installer testing is still required. Do not assume the installed system is safe until Calamares install, bootloader setup, and installed-system cleanup are verified.

## Release checklist

Create a checksum:

```bash
cd ~/MikuOS/out
sha256sum mikuos-*.iso > SHA256SUMS
```

Upload both files:

- ISO
- `SHA256SUMS`

Recommended release naming:

```text
v0.1.0-prealpha
v0.1.1-prealpha
```
## NOTE:
Change the line had the <name> to your User
