# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.6.7** (released 2026-11-02)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.6.7 - Beta feedback: icons stay put, unstack a page, send feedback (2026-11-02)
- A document dropped anywhere on the desktop stays there. Auto Arrange is now off by default (switched off once for
  existing installs); View > Arrange items > Auto Arrange turns the fixed order back on. Folders with more than 600
  documents keep the fixed order.
- Unstack a page, as in PaperPort: in the viewer, select pages and press **Unstack page** (they become documents of
  their own next to the original, which keeps the rest; a version is saved); on the desktop, flip the thumbnail to a
  page and right-click > **Unstack the shown page**. **Unstack** on a multi-page document makes every page its own
  document and moves the original to the Recycle Bin.
- Old PaperPort .max files: File > **Convert old PaperPort .max files** converts them to PDF through PaperPort's own
  console converter (cvmaxpdf_console.exe, part of PaperPort 14, found on the PC by itself): one file per process so a
  crash or hang on one file cannot stop the batch, every PDF checked before it is accepted, page images kept exactly
  as they are (no MRC), PaperPort annotations carried over, the .max originals moved into a hidden "_MAX originals
  (converted)" subfolder (or left in place, or recycled, as you choose), progress with time left, Stop at any time.
  The message that appears when a folder with .max files is added offers the same. On a PC without PaperPort the
  message says where the converter is.
- Help > **Send feedback**: your message plus, if ticked, a zip of the logs on your Windows desktop (file names,
  actions and settings only, never document contents), handed to your mail program (private) or to a new issue on
  the GitHub releases page (public; needs a GitHub account). Nothing is sent until you press Send there.