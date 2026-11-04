# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.11.2** (released 2026-11-03)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.11.2 - The locked Personal Vault shows its padlock again (2026-11-03)
- A locked OneDrive Personal Vault has no folder on disk, only its shortcut; that absence is how ScanDesk knows to show
  the padlock. Since 0.10.0 the library store created a plain folder of the vault's name to put its hidden store in,
  so the padlock vanished and the vault looked empty, and the 0.11.1 start moved the vault documents' previous versions
  into that folder, where OneDrive could have synced them outside the vault. ScanDesk never creates a library's root
  folder now; a folder that holds nothing but ScanDesk's store next to the vault's shortcut counts as locked.
- Previous versions of documents in a library that is not reachable (locked vault, unplugged drive) wait in a local
  folder that OneDrive never sees and move into the library's own hidden store the next time it is open in ScanDesk.
  Versions kept by older releases under the desktop stay put until their library is reachable.