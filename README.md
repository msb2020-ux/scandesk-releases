# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.8.1** (released 2026-11-02)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.8.1 - A mortgage bill is not an insurance document (2026-11-02)
- Fixed: a mortgage statement (heading "HOME LOAN ACCOUNT", escrow lines that mention insurance) was named and filed as
  Insurance. Three starter rules are new: **Mortgage** (mortgage, home loan, loan account, escrow, principal and
  interest, loan number, servicer), **Bank statement** and **Tax**; existing installs get them in front of the Insurance
  rule, and rules you edited or deleted are left alone.
- Smart naming now pays attention to the top of the page: a type word that appears in the heading (the first lines,
  where the title and the account line are) counts extra, so "HOME LOAN ACCOUNT" at the top outweighs an "insurance"
  line in the details. The evidence shows which hits came from the heading.
- If a document still gets the wrong type, change **Type** in the Smart Assistant before pressing Rename, or add a
  rule with the sender's name under Edit > Filing rules so the next one from them is right from the start.