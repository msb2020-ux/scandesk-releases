# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.12.9** (released 2026-11-10)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.12.9 - Paste a picture, zoom slider, finish screen (2026-11-09)
- Paste a picture (Ctrl+V on the desktop) from the Snipping Tool, Print Screen or any copied image: it becomes a one-page
  PDF named "Pasted yyyy-MM-dd HH-mm-ss.pdf" in the open folder, placed on a letter sheet (portrait or landscape to suit
  the picture, half-inch margins, never enlarged), so it stacks, prints, annotates and searches like a scan. In the viewer,
  Ctrl+V inserts the picture as a new page after the current one. Until now Paste accepted only files.
- The viewer's status bar has a zoom slider (25% to 400%, marks at 25, 50, 100, 200 and 400) with minus and plus beside
  the percentage. Ctrl+mouse wheel, Ctrl+plus/minus and Fit width / Fit page work as before.
- The installer's finish screen now says that the shortcut is on the desktop and in the Start menu, and how to pin
  ScanDesk to the taskbar (an installer cannot do that on Windows 10/11).