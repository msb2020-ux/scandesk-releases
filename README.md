# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.12.0** (released 2026-11-03)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.12.0 - Private folders: nothing of a vault leaves the vault (2026-11-03)
- File > Folder Manager has a **Private** column for linked folders. A private folder is read and edited in place and
  ScanDesk keeps nothing of its documents anywhere else: no previous versions, no thumbnails, no text in the search
  index, no naming suggestions, no text layer written by the reader, no hidden store inside the folder. The audit
  names only the folder. Search still finds these documents by name; nothing else is recorded about them.
- A OneDrive Personal Vault link is private from the first start of this version. Untick it in the Folder Manager
  if you want the vault indexed like any other folder. Turning Private on drops what the index already held of that
  folder.
- Reading a document's version list no longer creates the hidden store in a folder; only keeping a version does.