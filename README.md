# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.8.2** (released 2026-11-02)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.8.2 - Two monitors, the scan window, and a smarter assistant (2026-11-02)
- ScanDesk reopens on the monitor it was closed on, at the same spot (maximized windows too). Windows that were being
  pushed onto the main monitor at start (a side effect of the 0.7.1 fit-to-screen guard) now stay on the monitor they
  are on, and every dialog, the Scan window included, opens centered on ScanDesk's own window.
- The Scan window opens with the settings of your last scan: profile, color or gray, dpi, feeder, duplex, paper size,
  clean-up ticks. Saved profiles are untouched; this is just "the way you scanned last time".
- Smart naming reads the first page first: the suggested name is queued as soon as page 1 is read, not after the whole
  document, and **Read now** in the Smart Assistant shows the first page's result at once while the rest is read in
  the background.
- The Smart Assistant learns from you: change **Type** (or the sender) before pressing Rename and the next document
  from that sender gets the same type, rule or no rule. The status bar confirms what was remembered; set the type back
  once to forget it. Learned types live in config.json (TypeBySender).
- Credit-card statements: a new **Credit card** starter rule (minimum payment due, new balance, payment due date,
  account ending, closing date, late payment warning, interest charged, ...) and a table of well-known senders
  (KnownSenders in config.json: American Express, Chase, Capital One, Discover, Citi, Bank of America, Wells Fargo,
  Regions, U.S. Bank, Mediacom, Alabama Power, AT&T, Verizon, the IRS, Medicare, the big health insurers, ...) that
  are recognised from a web address or a name anywhere on the page. Mark's American Express bill, whose top line is
  the card's product name, now comes out as "American Express Credit card 2026 October" instead of "Delta SkyMiles
  Platinum Document".