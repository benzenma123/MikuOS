# MikuOS

MikuOS is an Arch-based Linux distribution featuring KDE Plasma, Miku-inspired branding, a custom boot splash, and the Calamares installer.

<p align="center">
  <strong><span style="color:red">⚠ As of June 24, 2026, the ISO may be unstable. This is an early preview. Use a virtual machine or non-critical hardware.</span></strong>
</p>

## Features

- KDE Plasma desktop
- Arch Linux base
- MikuOS branding and wallpaper
- Custom Plymouth boot splash
- Calamares graphical installer
- AMD and Intel support
- Fastfetch MikuOS branding

## Current Status

MikuOS is currently in pre-alpha.

Working:

- Live ISO boots
- KDE Plasma live session works
- MikuOS branding is applied
- Plymouth splash works
- Fastfetch branding works
- Network works in the live environment
- Calamares opens

Known issues:

- Calamares installation is not fully validated and may fail
- Installed-system cleanup still needs work
- Bootloader installation needs more testing
- Hardware testing is currently limited

## Testing

The installer has not been fully validated. Back up important data before testing it on physical hardware.

Please report bugs and suggest features, packages, removals, or fixes through [GitHub Issues](https://github.com/benzenma123/MikuOS/issues).

## Download

Download the ISO and checksum from [GitHub Releases](https://github.com/benzenma123/MikuOS/releases).

## Verify

```bash
sha256sum -c SHA256SUMS
```

## Preview

<p align="center">
<img width="1902" height="1021" alt="image" src="https://github.com/user-attachments/assets/81ff215f-0139-4baa-8044-073043d4fec2" />
</p>

## Build

Build instructions are available in [BUILD.md](BUILD.md).

## License

MikuOS project code and configuration are licensed under GPL-3.0-or-later. Bundled software and third-party assets retain their respective licenses.
