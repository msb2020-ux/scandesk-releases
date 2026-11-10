# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.12.11** (released 2026-11-10)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.12.11 - Failed .max files in one folder (2026-11-10)
- After a .max conversion run, a "Collect failed files" button moves the files PaperPort's converter could not read into one
  visible folder, "PaperPort files that did not convert", at the top of the folder you converted, keeping their subfolder
  names, with a "where these came from.txt" listing the original places. It opens in Explorer. Nothing is deleted, nothing
  moves until you click, and the collected files are not offered again (move one back out to retry it). The run itself
  already continued past failures; the two left in a Home folder of 6,723 were the reason for this.
- The failure text now quotes the converter's own reason ("Failed, file could not be converted!") instead of its sign-off line.