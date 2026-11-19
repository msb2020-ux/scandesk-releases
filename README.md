# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.14.7** (released 2026-11-18)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.14.7 - Dropping documents on one another stacks them into one multi-page PDF; an empty feeder is reported; a new document shows its preview at once (2026-11-18)
One update; 0.14.2 to 0.14.6 were trial builds and were never released on their own.

Stacking
- **Dropping a document on another one now stacks them, into ONE multi-page PDF, as PaperPort does.** With Auto Arrange
  off (the usual setting) a drop did nothing useful before: the icon was only laid over the other one. Now the document
  under the pointer is marked while you drag, and letting go joins the two.
- **The result pages and opens like any multi-page PDF.** Its thumbnail has the page arrows and the page count, a
  double-click opens it in the viewer, and it goes out by e-mail as one attachment. In the viewer the bookmarks name
  the documents that went into it.
- **What you drop lies on top.** Its pages come first; the pages of the document you dropped on follow. Drop more on it
  later and those go on top again.
- **Several documents dropped together** go on top in the order the desktop shows them, row by row from the top left.
- **It stays where you dropped.** The result keeps the name and the place of the document you dropped on. A picture you
  drop on becomes a PDF of the same name.
- **PDFs and pictures can be stacked.** For any other file (a Word document, a text file) and for a password-protected
  PDF, ScanDesk says which file it is and changes nothing.
- **Nothing is lost.** The single files go to the Recycle Bin, and the document you dropped on keeps its previous state
  under *Versions*. Tags of the single documents move to the stacked one.
- ***Unstack*** takes a stacked document apart again, one document per page.
- **Stacking answers at once.** What you dropped leaves the desktop immediately and the document you dropped on shows
  "Stacking..." until it is ready, usually well under a second. The window stays usable meanwhile, and you can drop
  the next document right away. Moving the single files to the Recycle Bin, which can take seconds in a OneDrive
  folder, happens afterwards in the background.
- Piles made by an earlier version (shown with an item count instead of pages) still open as a list. Drop something
  on one, or use *Merge stack to one PDF*, and it becomes one document in its place.

Fixed
- **Scanning with an empty feeder.** ScanDesk now asks the scanner whether paper is loaded before it starts. If the
  feeder is empty it says so ("The feeder is empty. Put the pages in the scanner and scan again.") and stops.
  Before, *Scan now* could sit at "Scanning..." while the scanner's own software waited in a window of its own.
  Scanners that cannot tell whether paper is loaded scan as before.
- When a scan cannot start (scanner switched off, in use by another program, driver will not open), ScanDesk now
  shows the reason instead of "Scan host ended unexpectedly".
- A document that had just arrived on the desktop, printed to ScanDesk or scanned, could stay without its preview
  picture until you flipped a page with the arrows on it. It now shows its preview by itself.
- The same could leave other documents in a folder without a preview after the folder was read again; they now get
  their picture too.
- A folder named `.scandesk` could show in the folder tree. It is ScanDesk's own storage inside a library and is
  never shown now, also when a sync program has taken away its hidden flag.
- With one document in a folder and that one selected, the status bar said "1 items, 1 selected". It says "1 item".
- An empty feeder is noted in the log as one plain line, no longer as an error with a full trace.
- 388 automated tests pass.