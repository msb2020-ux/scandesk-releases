# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.6.3** (released 2026-11-02)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.6.3 - Previews for Office, CSV and other files (2026-11-02)
- Word, Excel, PowerPoint, CSV, text and every other file kind now show a picture on the desktop: the same thumbnail
  Explorer shows (a picture of the first page when the file's program provides one, for example Word and Excel when
  Office is installed), otherwise the program's icon on a card. Thumbnail sizes, the details view and the Smart
  Assistant preview use it too. Double-click still opens the file in its own program.
- The text of .docx, .xlsx and .pptx files is read for search and smart naming (no Office needed). Older binary
  .doc/.xls/.ppt files show their icon and open in their program but are not searched.
- Send To > Text file / Word works for Office files as well.
- Support switch: the environment variable SCANDESK_SOFTWARE_RENDER=1 makes ScanDesk draw its windows without the
  graphics card, for a PC whose display driver leaves WPF windows blank (seen on the dev PC on 2026-11-02; any WPF
  program was affected until the driver was restarted).