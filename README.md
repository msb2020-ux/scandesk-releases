# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.12.7** (released 2026-11-08)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.12.7 - Nothing is created or moved through a locked vault (2026-11-08)
- Adding a folder, importing, moving, renaming, stacking, deleting or saving inside a linked folder whose target is not
  there (a locked OneDrive Personal Vault, an unplugged drive) now stops with a clear message and changes nothing.
  Before, "New folder" on a locked vault created a plain folder of the vault's name with just the new path inside; the
  tree then showed that stand-in instead of the real vault, so whole year folders looked missing, and OneDrive synced
  the stand-in to the other PCs as "Personal Vault-DrBrown-Mobile" (it held no documents and has been removed).