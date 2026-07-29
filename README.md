# DevShed

<img src="banner.png" alt="DevShed Banner" width="100%" />

DevShed is a native macOS menu bar utility for finding and clearing Xcode-related storage that builds up over time. It scans selected developer folders locally, shows how much space they use, and lets you clean individual categories or run a standard cleanup.

Download DevShed at [devshed.codearc.studio](https://devshed.codearc.studio).

## What it does

- Shows the space used by common Xcode storage locations.
- Cleans individual categories or a standard set of Xcode caches.
- Shows a per-project Derived Data breakdown, so you can review what is taking space before deleting it.
- Lets you inspect and remove unavailable simulator devices, and erase an individual simulator when needed.
- Can exclude Swift Package Manager-related cache paths from Xcode cache cleanup.
- Includes optional notifications, cleanup reminders, custom folders, and a command-line tool.

DevShed does not scan your source repositories as part of its standard cleanup. If you add a custom folder, you choose that folder and remain responsible for its contents.

## Safety controls

- Review storage by category before you clean.
- Open the selected folder in Finder from DevShed when you want to inspect it first.
- Enable **Quit Xcode before cleaning** in Settings if you want DevShed to request that Xcode closes before deletion begins.
- Swift Package Manager-related paths inside the Xcode cache are excluded by default. You can change this in Settings.

Cleaning removes cache files and simulator data. Xcode or macOS may recreate some of these files during later builds or simulator use.

## Command-line tool

DevShed can install an optional `devshed` command from **Settings → CLI Tool**. Open a new Terminal window after installation, then use:

```bash
devshed status
devshed clean
```

`devshed status` reports the amount of storage currently marked as cleanable. `devshed clean` requests the app to run its standard cleanup. The app must be installed and running for the command-line tool to communicate with it.

## Requirements

- macOS 14 or later
- Apple silicon or Intel Mac

## Installation

1. Download the latest `DevShed.dmg` from [devshed.codearc.studio](https://devshed.codearc.studio).
2. Open the disk image.
3. Drag `DevShed.app` to your Applications folder.
4. Open DevShed and use its menu bar icon to scan your Xcode storage.

## Privacy

DevShed performs scans and cleanup on your Mac. It does not use third-party analytics or advertising services.

## License and trademarks

DevShed is developed by CodeArc Studio and is available free of charge.

Xcode, macOS, and Mac are trademarks of Apple Inc.
