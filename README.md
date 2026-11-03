# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.10.0** (released 2026-11-03)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.10.0 - Libraries, a lighter touch on your files, and a beta channel (2026-11-03)
- Every linked folder is now a library with its own hidden store inside it (a ".scandesk" folder): the previous
  versions of its documents and the icon arrangement of its folders live there, next to the documents. They follow
  the folder to your other PC through OneDrive, and they no longer depend on which drive the ScanDesk desktop is on
  (the cause of the stray copies in 0.8.3). Versions that older releases kept under the desktop are moved into the
  libraries once, at the first start.
- OCR no longer rewrites PDFs in linked folders. Searching inside ScanDesk never needed the text layer; writing it
  into a OneDrive file re-syncs the file and was the chain in the stray-copy bug. The desktop's own folders still get
  the layer when Options > OCR says so; for a linked folder tick "OCR text into PDFs" in File > Folder Manager.
- The Smart Assistant's evidence line says why the sender was chosen ("from American Express (americanexpress.com)",
  "written for ..." when you corrected it) next to the type words that matched.
- Beta channel: Options > Updates > "Beta channel" offers test versions before everyone else gets them. Off, only
  versions marked stable are offered. (This release is stable; the channel applies from the next test build.)
- Modern look for the dialogs: rounded check boxes and radio buttons with an accent tick, thin progress bars,
  card-like group boxes, flat list headers; the Audit, Review and Clean-up windows follow the theme colors.
- PaperPort's .ptn2 thumbnail files are hidden too.
- Under the hood: the test suite now runs a scenario on a second drive letter (SUBST), the seam where the worst bugs
  lived; it covers versions, layouts, the text-layer policy and the migration.