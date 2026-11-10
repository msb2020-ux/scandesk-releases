# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.12.10** (released 2026-11-10)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.12.10 - No more "Allow ScanDesk?" after every update (2026-11-10)
- Since 0.12.5 the installer has put ScanDesk on Windows Security's Controlled folder access allowed list, but it wrote the
  path as "C:\Program Files\ScanDesk\.\ScanDesk.exe" (a stray dot). ScanDesk looked for the path without the dot, did not
  find itself, and asked "Allow ScanDesk now?" once after every update on PCs where ransomware protection is on. The
  installer now writes the plain path and removes the dotted leftovers; the app finds itself and stays quiet.
- Behind the scenes: the installer's Defender step is now covered by tests, and a release goes out through one
  checked script with a dry run, so a slip like the stray dot is caught before anything ships.
- The .max tools are easier to find: "Convert .max" and "Find .max" sit on the Organize ribbon next to Folder Manager,
  and a folder's right-click menu has "Convert old PaperPort .max files here". File > Convert old PaperPort .max files stays.