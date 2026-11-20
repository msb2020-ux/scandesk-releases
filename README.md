# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.14.8** (released 2026-11-20)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.14.8 - A print window with a preview; documents open and page faster (2026-11-20)

Printing
- **Print now opens ScanDesk's own print window, and it shows a preview.** The Windows print dialog cannot show one for
  a program of this kind (it says "This app doesn't support print preview"), so ScanDesk now draws the preview itself,
  with the same code that draws the printed page: what you see is what comes out, margins included. Arrows, Page Up /
  Page Down and the mouse wheel page through what will be printed.
- **The choices that matter are in the window:** the printer (the one used last is offered first), copies, the pages
  (all, the current page, or ranges such as `1-3, 5` or `8-`), the paper, color or black and white, and two-sided
  printing where the printer can do it. The line at the bottom says how many sheets of paper that makes.
- **Orientation is automatic for every page.** A landscape page is turned to lie along the sheet; before, it was
  printed small across an upright sheet. Portrait or landscape can still be forced.
- **Size: "Fit to the paper" or "Actual size".** Fit uses the area the printer can reach, so nothing is cut off at the
  edge (before, pages were fitted to the whole sheet and the outermost few millimetres could be lost). Actual size
  prints at 100% in the middle of the sheet.
- **Printer properties** opens the printer's own settings (trays, stapling, toner saving). **Use the Windows print
  dialog instead** is still there, one click away, and is used by itself if the print window cannot open.
- **The window stays in use while a document prints.** The pages are sent in the background and the status bar says
  "Printing page 3 of 12..." and then "Sent 12 pages to ...". Each page also goes to the printer faster.
- **Print is always in a document's right-click menu**, above *Show more*.
- Fixed: printing from the viewer wrote "printed" into the audit trail even when the dialog was cancelled.

Speed
- **A document opens with its first page first.** The viewer used to draw the pictures of the page strip ahead of the
  page itself, and packed and unpacked every page on the way. Measured on a 40-page scan of 68 MB: the first page
  appeared after about 1.5 seconds and now appears after 0.2 to 0.3; turning to the next page took about 0.4 seconds
  and is now immediate, because the next page and the one before are drawn ahead.
- **A document is read from disk once while you look at it**, not once for every page and every picture of the strip.
  This matters most for documents in OneDrive or on a share.
- **ScanDesk starts sooner.** The search-by-meaning model and the check of the program files are loaded after the
  window is there instead of before it. Measured: the two took 0.3 seconds of an ordinary start (now about 1.3
  seconds to the window on the test PC) and 2.7 seconds of a first start, when nothing is in memory yet.
- **Deleting, moving or stacking a document no longer makes ScanDesk read the whole folder tree again.** It did, on
  the window's own thread, after every single file that went away. Making or removing a folder now re-reads only the
  folder it happened in.
- **A new scan or print adds one card to the open folder.** The whole folder used to be emptied and filled again for
  one new document, with every picture unpacked again.
- Opening a folder no longer asks the disk two questions per document to find online-only OneDrive files (the folder
  listing already knows), and the folder tree asks "is there a subfolder?" instead of listing them all.
- The background text reader steps aside while pictures of the open folder or a page in the viewer are being drawn,
  and reads a document once instead of once per page.
- The log now says how long the start, a slow folder and every opened document took (lines marked `[speed]`: counts
  and milliseconds, never a name), so a PC that feels slow can be explained from *Help > Copy logs for support*.

434 automated tests pass.