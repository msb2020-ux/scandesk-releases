# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.6.5** (released 2026-11-02)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.6.5 - Duplicate finder (2026-11-02)
- Edit > Find duplicates (also Automate > Clean up): scans the open folder (and subfolders) or the whole desktop for
  documents that are one document twice. Three signals: identical files (same bytes; the hash is computed only for
  files of equal size), the same text (the same paper scanned twice: the indexed text overlaps 80% or more, OCR slips
  allowed), and first pages that look alike for documents without readable text. Online-only OneDrive files are not
  downloaded for this.
- Each pair shows the older and the newer copy with size and date, and why they match. **Compare side by side** opens
  both in the viewer's compare pane; **Delete newer** / **Delete older** move one copy to the Recycle Bin after a
  question; **Keep both** marks the pair as not a duplicate and hides it for good; **Delete all newer identical
  copies** clears byte-identical duplicates in one go (after listing them). Nothing is deleted by itself.
- Fingerprints are kept in the index per file version, so the second scan of a big desktop is quick.