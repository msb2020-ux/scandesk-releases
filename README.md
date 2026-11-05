# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.12.2** (released 2026-11-04)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.12.2 - Outlook drops that failed to read; a folder that refuses its store (2026-11-04)
- On Catherine's PC, arranging icons in a linked OneDrive folder showed "Something went wrong: Could not find file
  '...\.scandesk\layouts'": OneDrive would not let ScanDesk make the folder's hidden store. ScanDesk now keeps the icon
  arrangement locally and the previous versions in its local pending store when a folder refuses the store, and no
  box appears.
- Dragging from Outlook onto the desktop could end in "Invalid FORMATETC structure" with nothing imported (the
  laptop's log, 2026-11-03 14:49). Outlook refuses a request for several transfer mediums at once, and a dragged
  message comes as a compound file rather than a stream. Each item is now asked for one medium at a time, and
  messages are copied storage-to-storage into a proper .msg file.