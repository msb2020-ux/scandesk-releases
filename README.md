# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.8.3** (released 2026-11-03)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.8.3 - Stray copies in linked folders (2026-11-03) - please update
- Fixed a bug that made copies of documents. In a linked folder on another drive (Personal Vault, Home, the office
  folders on D: with the desktop on C:), every time ScanDesk kept a previous version of a file (after OCR wrote the
  text layer, after a rotate or clean-up) the backup was written next to the original instead of into the hidden
  .Versions store, named "name.20261103-061844-789.pdf". The background reader then treated that copy as a new
  document, gave it a text layer, backed it up again, and a folder could fill with copies. Versions 0.6.1 to 0.8.2 did
  this. Backups now always go into the store ("_linked\<drive>\..." for linked folders), and a stamped copy is never
  rewritten even if one slips through.
- Help > **Clean up stray version copies** finds those copies (only where the original is still beside them) and
  moves them into the store, where they stay listed under Previous versions. Nothing is deleted. At the first start
  after the update ScanDesk looks for them once and offers the same.
- Until you update: File > Options > Quiet mode stops the background reader and with it the copying.