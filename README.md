# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.9.0** (released 2026-11-03)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.9.0 - The desktop as you asked (2026-11-03)
- Documents start in the upper-left corner. With free placement the icons sat on a sheet that floated to the middle of
  the view when the folder had few documents, and nothing could be dragged above its edge; the sheet now starts at the
  top-left and is at least as tall as the view. When the window gets narrower, icons left beyond the right edge are
  pulled back into view (the next free cell, row by row); icons that are still visible stay where you put them.
- PaperPort's own files are hidden: .ppinfocache, *.ptn, maxdesk.ini, maxdesk.ini2 (and Windows' desktop.ini and
  thumbs.db). They stay on disk, so PaperPort still works on the same folders.
- Two monitors: the window's place is now kept in screen pixels with the monitor's name and set before the window
  shows, so a portrait second monitor and mixed scaling work; the log says what was saved and what was done.
- The desktop's right-click menu follows PaperPort's order: Views, Arrange items, Line up items, Refresh; Paste,
  Select all, New; then Smart naming and Open in Explorer.
- The Send To bar shows each target's own icon: the program's icon for program targets, your mail program for Email,
  the printer, Word, Notepad and Explorer for the built-ins, the folder icon for folder targets (the glyph stays when
  no icon can be read).
- A locked OneDrive Personal Vault: double-click its folder to re-check it. Unlocked, its contents show at once; still
  locked, ScanDesk offers to open it in Explorer (OneDrive's unlock prompt) and keeps checking for a minute.
- Taskbar: the installer's shortcuts take their icon from ScanDesk.exe itself instead of a separate file that every
  upgrade deleted (the blank pinned button), and the pinned button and the running window now share one identity.
  Re-pin ScanDesk once after this update; from then on the icon stays.
- Modern look, second pass: folder tree with chevrons and rounded hover and selection, a pill-shaped search box, thin
  rounded scroll bars, rounded drop-down lists, and a soft shadow when the mouse is over a document card.
- Updates: a release on GitHub stays hidden until its installer is fully uploaded, and the dialog explains itself
  when it finds a version whose installer is not there yet.