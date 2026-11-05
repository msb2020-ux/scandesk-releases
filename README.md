# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.12.4** (released 2026-11-05)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.12.4 - A damaged installation offers to repair itself (2026-11-05)
- On a new PC Windows reported "ScanDesk.exe - Bad Image: x64\leptonica-1.85.0.dll is either not designed to run on
  Windows or it contains an error": that program file was no longer a program file (antivirus quarantine or an
  interrupted update), so text recognition failed and with it the ScanDesk printer, which needs the running program to
  pick up the print. ScanDesk now checks its program files at every start and, when one is damaged, names it and offers
  Repair: Windows reinstalls the same version from the copy it keeps, without a download.
- Downloaded installers that are no longer needed are removed from the local updates folder (the newest is kept for a
  repair); one PC held nine of them, 1.6 GB.
- .max files that were already converted are no longer counted, offered or listed on another PC. The originals sit in a
  hidden "_MAX originals (converted)" folder, but OneDrive does not carry the hidden mark to other PCs, so a new PC
  counted them again (49 in Oculo-Facial Consultants that the laptop had converted) and showed the folder in the tree.