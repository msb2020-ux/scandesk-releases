# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.8.0** (released 2026-11-02)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.8.0 - Modern look, with Classic one click away (2026-11-02)
- View > Appearance > **Modern (Windows 11 look)**: ScanDesk draws its own title bar (icon, name, minimize / maximize /
  close), the ribbon becomes a command bar (tab pills, one row of icon-and-label buttons, no group captions), documents
  sit on cards, the Send To bar floats as a rounded dock, controls have rounded corners and the text uses Segoe UI
  Variable. Everything is in the same place and every command works the same; only the look changes.
- **Classic** stays the default and is what every existing install keeps: the PaperPort-like ribbon with group captions
  and the standard Windows title bar, exactly as before. Switch back and forth at any time; the change is immediate in
  every open window, no restart. The ribbon's Organize > Theme button offers both looks too.
- Picking Modern while the Light blue colors are on switches the colors to Light gray (the neutral palette the look
  is designed for); View > Theme changes them back. Dark works with both looks.
- Dark theme: the folder tree's names are drawn in the theme's text color (they were dark gray on dark); Windows'
  title bars of the Classic look and of every dialog turn dark with the theme.