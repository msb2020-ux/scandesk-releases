# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.7.0** (released 2026-11-02)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.7.0 - Ask in plain words (2026-11-02)
- Natural-language search. In the Find group choose **Ask in plain words** and describe the document: "the eye clinic
  lease from two years ago", "what do I owe the cable company", "patient sent for cataract assessment". ScanDesk
  compares the meaning of your words with the meaning of every document's text, not just the words themselves, and
  lists the best matches first with how well each matches. Time hints in the question ("two years ago", "March 2025",
  "last year") narrow the dates.
- The meaning index is built in the background by a small language model that ships with ScanDesk
  (all-MiniLM-L6-v2, 23 MB) and runs on this PC; nothing leaves the computer. The status bar shows "Meaning index: n of
  m" until every document that has text is covered; questions work from the first minute on what is covered so far.
- File > Options > "Natural-language search" turns the index off (quiet mode turns it off too).