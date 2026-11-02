# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.6.6** (released 2026-11-02)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.6.6 - Beta feedback: arrival order, quiet mode, a selection error (2026-11-02)
- The desktop now keeps documents in the order they arrived, oldest first, so a new scan lands at the end as in
  PaperPort. Existing installs that still had the alphabetical default are switched once; Arrange items > by Name
  brings the alphabet back. With Auto Arrange off, a document without a saved place is put after the last one, never
  into a gap you left on purpose.
- File > Options > **Quiet mode**: one tick leaves your scans alone: no background reading (OCR), no suggested names, no
  Smart Assistant pane. Scan, look, rename by hand; search then finds names only. Untick to turn everything back on.
- Fixed: clicking a document could show "Something went wrong: An item with the same key has already been added"
  after the folder listing had been rebuilt (seen on the OFC laptop). The selection is now dropped and restored around
  a rebuild, and a stale selection entry is recovered quietly instead of shown as an error.
- Old PaperPort .max files (the format from before PaperPort switched to PDF) are counted when a folder is added
  (Folder Manager, PaperPort import) and on request (File > Find old PaperPort .max files). ScanDesk cannot read
  them; the message explains how to convert them without loss in PaperPort itself (select, Save As, PDF image).
- The welcome tip now says how to rename (click the name of a selected document, or F2), how to arrange and group
  documents, and where quiet mode is.