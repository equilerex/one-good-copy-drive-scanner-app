# One Good Copy: Linux and macOS builds

Scan your drives, see what takes the space, find duplicate files. One Good Copy reads the folders and drives you choose, and deletes only what you confirm.

**Unofficial community builds. No support promise.** Files only: no source is published here.

## Windows

Install from the Microsoft Store, or in a terminal:

```
winget install --id XP9M26RSCLNT88 --source msstore
```

There is no separate Windows download here.

## Linux (x86_64)

Download `one-good-copy-<version>-linux-x86_64.AppImage` or the `.tar.gz` from the latest release.

AppImage:

```
chmod +x one-good-copy-*-linux-x86_64.AppImage
./one-good-copy-*-linux-x86_64.AppImage
```

The AppImage needs FUSE 2 (`libfuse2`). Without it, run `./one-good-copy-*.AppImage --appimage-extract-and-run` or use the tarball: unpack it and run `./one-good-copy`.

Built on Ubuntu 22.04, so it needs glibc 2.35 or newer. A desktop with Wayland or X11, and Vulkan drivers, is required. Most desktops already have the libraries it loads. On a minimal system install `libxkbcommon-x11-0`, `libxcb-xkb1`, `libvulkan1`, `libfontconfig1` and `libwayland-client0` (Ubuntu and Debian names). The folder picker uses the desktop portal (`xdg-desktop-portal` with a GTK, GNOME or KDE backend).

## macOS (Apple Silicon, macOS 11 or newer)

**Status:** the macOS build has not been published yet. It is built by hand on an Apple Silicon Mac, so it appears here when one is available. Steps below are for when it is.

Download `one-good-copy-<version>-macos-arm64.dmg`, open it and drag One Good Copy to Applications.

The app is not signed with an Apple developer certificate, so macOS blocks the first start:

1. Open the app once. macOS says it cannot verify it. Close that dialog.
2. System Settings, Privacy & Security, scroll down, "One Good Copy was blocked", **Open Anyway**.
3. If that button never shows, run `xattr -dr com.apple.quarantine "/Applications/One Good Copy.app"` in Terminal and open the app again.

To scan protected folders and other disks, give the app Full Disk Access (Privacy & Security, Full Disk Access). Grant it again after each update. Intel Macs are not supported.

## Check the download

```
sha256sum -c SHA256SUMS      # Linux
shasum -a 256 -c SHA256SUMS  # macOS
```

## Your data

| | Catalog and logs |
|---|---|
| Linux | `~/.local/share/one-good-copy` (or `$XDG_DATA_HOME/one-good-copy`) |
| macOS | `~/Library/Application Support/One Good Copy` |

Logs are in the `logs` folder there. To uninstall, delete the app (or the AppImage) and that data folder.

## Bugs and feature requests

This repository is the place for both. Open an issue: [Report a bug or ask for a feature](../../issues/new/choose).

For a bug, include:

- Your system: Linux distribution and version, or macOS version, and whether it is the AppImage, tarball or dmg.
- The app version (About page, or the file name you downloaded).
- What you did, what you expected, what happened. A screenshot helps.
- The end of `logs/app.log` from the data folder above. If the app closed by itself, also any `crash-*.log` file in the same folder. Look through them first: they list folder and file names from your scans.

No support promise, but every issue is read.

## Updates

There is no auto-update. Use "Watch" on this repository to hear about new releases.

## Licence

See `EULA.txt` in each download. Third-party notices are in each archive. The app collects and sends no data: https://onegoodcopy.com/privacy
