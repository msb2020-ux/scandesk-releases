# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.6.1** (released 2026-11-02)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.6.1 - Folder Manager, update prompt in the middle of the window (2026-11-02)
- File > Folder Manager (also on the Organize ribbon and in the folder tree's right-click menu): the top-level folders
  of the desktop in one list, like PaperPort's Folder Manager. **Add...** puts a folder that already holds documents
  (OneDrive, a network share, any folder on this PC) on the desktop under a name of your choice; the documents stay
  where they are and are read and edited in place, nothing is moved or copied. **Remove** takes a linked folder off
  the desktop (documents untouched); **Rename...**, **Move Up / Move Down** (the order is kept and shown in the tree),
  **New folder...**, **PaperPort folders...** (the registry import) and **Open in Explorer**. The bottom line shows where
  the selected folder's documents are.
- The update question at startup now opens in the middle of the window ("ScanDesk Desktop x.y.z is ready to
  install. Install it now?" with the release notes, Install now / Later) instead of a small corner toast. It waits for
  the first-start prompts and never opens on top of another dialog. A tray (hidden) start still gets the toast.
- Bring in PaperPort folders: a locked OneDrive Personal Vault can be ticked and linked (it was greyed out).
- Renaming a folder keeps its color.
- For testers and support: the environment variable SCANDESK_DATA_DIR moves settings, links, index, cache and logs
  under one folder, so a second copy can run beside the installed one without sharing its data.