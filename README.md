# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.11.0** (released 2026-11-03)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.11.0 - Marks you can move, change and remove, before and after the save (2026-11-03)
- Highlights, text, notes, boxes, arrows, stamps and image stamps on PDF pages are now real PDF annotations from the
  moment you place them, the way PaperPort keeps them. Click a mark to select it, drag it to move, pull a corner to
  resize, double-click (or Edit text) to change the words, press Delete to remove it. All of this still works after the
  save, in ScanDesk and in other PDF readers; every step is undoable with Ctrl+Z.
- Marks made by other programs (Acrobat comments, ink scribbles, PaperPort notes) are listed too: ScanDesk moves and
  removes them whole and leaves their look alone. Form fields and links are never touched.
- Every mark carries its own appearance, drawn upright for the page's rotation, so Acrobat, Edge, PaperPort and the
  Smart Assistant's thumbnails all show it the same way. Notes get a yellow note icon everywhere.
- The annotation bar has a Select tool and Edit text / Delete buttons. "Apply marks" is only shown when something must
  be burned in: a redaction (which really removes what is underneath) or a mark on an image page (no annotation layer).