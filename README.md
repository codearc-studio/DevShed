# DevShed

<img src="banner.png" alt="DevShed Banner" width="100%" />

A lightweight, high-performance native macOS menu bar application and CLI tool engineered to surgically reclaim gigabytes of disk space hoarded by Xcode, simulators, and package managers.

DevShed maps out developer cache directories natively using Apple system frameworks, scanning directories in milliseconds without interfering with active build pipelines.

DevShed operates 100% locally on your workstation. It features zero tracking, zero telemetry, and zero ads.

---

## Key Features

* **Ghost Cache Tracking:** Xcode leaves behind heavy compilation index files inside DerivedData long after you delete or relocate an .xcodeproj or .xcworkspace. DevShed flags these abandoned assets for safe deletion.
* **Execution Safe Mode:** Prevents index corruption. DevShed prompts you to save open files and gracefully closes running Xcode processes before firing a deletion routine.
* **Swift SPM Protection:** Surgically excludes core Swift Package Manager registries by default to preserve compiler indexes and save internet bandwidth on subsequent builds.
* **Multi-Platform Cache Catalogs:** Native support for clearing heavy developer caching roots, including Flutter Pub Cache, Homebrew binaries, Carthage, CocoaPods, and deep nested node_modules.
* **Simulator Device Tracker:** Clears stale log states, device runtime containers, and legacy iOS/watchOS/tvOS simulator versions abandoned by Apple system updates.

---

## CLI Usage

DevShed bundles a lightweight command-line tool for developers who prefer the terminal or want to script their maintenance routines.

```bash
~/Developer $ devshed status
Analyzing compiler registries... Done.
- DerivedData: 14.50 GB
- SimulatorLogs: 8.20 GB
- Xcode Caches: 4.10 GB
Total purgeable files: 26.80 GB waiting to clear.

~/Developer $ devshed clean
Terminating Xcode workspaces gracefully... Closed.
Clearing compiler caches securely... Done.
✔ Success: Cleared 26.80 GB of background cache files safely.
```

---

## What We Clean (And Protect)

| Target Directory | What DevShed Does | Protection Mechanism |
| :--- | :--- | :--- |
| DerivedData & Archives | Clears intermediate objects, module maps, and stale debug builds. | Safely purges without breaking structural paths. |
| SPM Caches | Keeps project mapping records intact. | SPM Protection prevents re-downloading dependency frameworks. |
| Simulator Runtimes | Wipes orphan hardware connection logs and expired iOS profiles. | Restores global defaults automatically. |
| Package Registries | Audits local node_modules, Flutter, and Homebrew caches. | Interactive Planner lets you selectively exclude active directories. |

---

## Requirements and Installation

* **System Support:** macOS 13 (Ventura), macOS 14 (Sonoma), or macOS 15 (Sequoia).
* **Architecture:** Native Apple Silicon (M1/M2/M3/M4) and Intel Core architectures.

### Download
DevShed is currently in early access. Sign up for immediate notification at launch over at https://devshed.codearc.studio

---

## Frequently Asked Questions

#### Is this safe? Will it delete my source code?
Absolutely safe. DevShed never views, indexes, or touches your personal source code repositories or project files. It exclusively targets volatile cache layers, system logs, and temporary virtual environments that macOS and Xcode are engineered to automatically regenerate on your next compilation step.

#### What makes it faster than a script?
DevShed is built directly on native Swift, AppKit, and SwiftUI APIs. Instead of executing slow sequential shell deep-finds, it interfaces directly with file system APIs to query directory state sizes instantly.

---

## License and Legal

Developed by CodeArc Studio. Released completely free to the developer community.

Xcode, macOS, and Mac are registered trademarks of Apple Inc., registered in the U.S. and other countries.
