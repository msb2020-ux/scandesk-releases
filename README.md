# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.10.1** (released 2026-11-03)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.10.1 - Outlook drops and a background .max conversion (2026-11-03)
- Attachments (and whole messages) dragged out of Outlook onto the desktop, a folder in the tree or the second pane
  are imported like files. Outlook offers them as "virtual files", which ScanDesk refused with a red cursor; they are
  now read from Outlook's stream and copied into the folder. Messages arrive as .msg files.
- The .max conversion window no longer blocks ScanDesk: Hide it (or close it) and keep working; the status bar shows
  "Converting .max files: 28 of 49, about 49 s left", a toast reports the end, and File > Convert old PaperPort .max
  files brings the window back. ScanDesk asks before exiting while a conversion runs.
- The window lists every file as it is done (a tick and the PDF's name, or a cross and the reason), offers "All
  folders" when several have .max files, and says in plain words what happens to the originals: by default each
  .max goes into a hidden "_MAX originals (converted)" folder next to its PDF; nothing is deleted.