# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.12.5** (released 2026-11-05)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.12.5 - Windows' Controlled folder access no longer blocks ScanDesk (2026-11-05)
- On the office PCs Windows Security's "Controlled folder access" (ransomware protection) was blocking ScanDesk.exe
  from writing into Documents and OneDrive: "Print capture failed: Access to the path is denied", icon arrangements
  that could not be saved, "Unauthorized changes blocked" notifications. The installer now registers ScanDesk's
  programs as allowed (with its administrator rights, on every install and update); the uninstall removes them again.
- ScanDesk also checks at start whether it is blocked and offers to allow itself (one administrator prompt), once per
  version; Help > Allow ScanDesk through Windows Security does it on demand. The print-capture message says when this
  is the cause.
- The publisher-trust package: the script now checks that it was extracted from the zip (Windows extracts only the
  one file when it is run from inside the zip), and it also unblocks ScanDesk installers in Downloads, which is what
  SmartScreen reacts to. The instructions say plainly that a self-signed certificate cannot satisfy SmartScreen's
  reputation check, so "More info > Run anyway" may still be needed once.