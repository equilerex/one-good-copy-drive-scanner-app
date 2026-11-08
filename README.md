# One Good Copy: Linux builds (macOS coming soon)

Scan your drives, see what takes the space, find duplicate files. One Good Copy reads the folders and drives you choose, and deletes only what you confirm.

**Unofficial community builds. No support promise.** Files only: no source is published here.

## Windows

Install from the Microsoft Store, or in a terminal:

```
winget install --id 9mvqsrqnnrh0 --source msstore
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

## macOS (Apple Silicon)

Coming soon.

## Check the download

```
sha256sum -c SHA256SUMS
```

## Your data

| | Catalog and logs |
|---|---|
| Linux | `~/.local/share/one-good-copy` (or `$XDG_DATA_HOME/one-good-copy`) |

Logs are in the `logs` folder there. To uninstall, delete the app (or the AppImage) and that data folder.

## Bugs and feature requests

This repository is the place for both. Open an issue: [Report a bug or ask for a feature](../../issues/new/choose).

For a bug, include:

- Your system: Linux distribution and version, desktop if you know it, and whether it is the AppImage or the tarball.
- The app version (About page, or the file name you downloaded).
- What you did, what you expected, what happened. A screenshot helps.
- The end of `logs/app.log` from the data folder above. If the app closed by itself, also any `crash-*.log` file in the same folder. Look through them first: they list folder and file names from your scans.

No support promise, but every issue is read.

## Updates

There is no auto-update. Use "Watch" on this repository to hear about new releases.

## Licence

See `EULA.txt` in each download. Third-party notices are in each archive. The app collects and sends no data: https://onegoodcopy.com/privacy
