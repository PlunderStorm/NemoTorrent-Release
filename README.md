<p align="center">
  <img src="assets/logo.svg" width="128" height="128" alt="NemoTorrent logo: an orange porthole with a white download arrow">
</p>

<h1 align="center">NemoTorrent</h1>

<p align="center"><b>Download as no one.</b></p>

<p align="center">
  <a href="https://github.com/PlunderStorm/NemoTorrent-Release/releases/latest"><b>Download the latest version</b></a> · <a href="https://plunderstorm.github.io/NemoTorrent-Release/">Website</a>
</p>

NemoTorrent is a Windows app for torrents, magnet links and direct downloads that sends all of that traffic through a WireGuard VPN tunnel you choose. If the tunnel drops, downloads stop, and nothing leaves through your real IP address.

This repository only hosts the official installers and the update manifest. The source code is not published.

## Features

- Torrents, magnet links and HTTP, HTTPS and FTP links.
- Manual WireGuard profiles (`.conf` files) and NordVPN (NordLynx) profiles.
- Two-level kill-switch: the app stops downloads when the tunnel drops, and the Windows firewall blocks any download traffic outside the tunnel, even if the app crashes.
- Optional Real-Debrid support, still inside the tunnel.
- Speed profiles (Turbo, Medium, Slow, Night) that you can schedule by hour.
- English and Italian interface, dark, light and high-contrast themes.
- No telemetry.

## Install

1. Open the [latest release](https://github.com/PlunderStorm/NemoTorrent-Release/releases/latest).
2. Download `NemoTorrent_<version>_x64-setup.exe` and run it. An `.msi` is also available for managed installs.
3. On first launch NemoTorrent checks for WireGuard and offers to install the official package if it is missing.

Requirements: Windows 10 or 11 (x64) with WebView2, and a WireGuard or NordVPN account.

Windows SmartScreen may warn you the first time, because the installer is not yet signed with a code-signing certificate. Choose "More info", then "Run anyway", only if you downloaded the installer from this page.

## Updates

Once installed, NemoTorrent updates itself from this page:

- It checks only while the VPN is connected, and only through the tunnel: bound to the tunnel address, with DNS over HTTPS inside the tunnel. With the VPN off it checks nothing.
- Each installer is signed. The app installs an update only if the signature matches the NemoTorrent key built into it and names the same version, so a tampered or older file is refused.
- You can turn off the automatic check, or check by hand, in Settings > Info > Updates.

Each release contains the installer, its `.sig` signature and `latest.json`, the manifest the app reads.

## Licence

NemoTorrent is free for personal, non-commercial use. See [LICENSE.txt](LICENSE.txt), which the installer also shows.

NemoTorrent includes third-party components that keep their own licences, listed in `THIRD-PARTY-NOTICES.txt` in the installation folder. In particular, it ships [aria2](https://aria2.github.io/) 1.37.0 unmodified, under the GNU GPL version 2. The complete source code of that aria2 version is attached to every release as `aria2-1.37.0.tar.xz`.

© 2026 PluNdeR
