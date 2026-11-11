# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.12.12** (released 2026-11-11)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.12.12 - Code review fixes: private folders, redactions, updater (2026-11-11)
A full read of the code found 43 defects in paths the tests did not cover (docs/review-2026-11-11.md). 40 are fixed here.
None was caused by last week's changes. The viewer and main-window fixes have not been checked on screen yet.

Private folders (Personal Vault)
- A vault that was linked on 0.12.0 or later was not private until the box was ticked by hand. It is private from the
  moment it is linked now, and a vault linked earlier is made private once at the first start of this version; what the
  index held of it is dropped. (If you had unticked Private on purpose, untick it again.)
- Renaming a private folder no longer makes it public. A private folder that also sits inside another linked folder is
  private from both directions.
- Moving a document into a private folder takes its text, thumbnail and suggestions out of the index. Tags and what the
  assistant learns are not kept for private documents, and their names no longer appear in the log file.
- Printing to ScanDesk or scanning while a locked vault is the open folder never creates a folder where the vault
  belongs: the print lands at the top level of the desktop, the scan is refused with a message.

Redaction and the viewer
- A redaction (or a mark on an image page, or a typed form entry) that has not been applied yet now follows its page
  when pages are deleted, moved or inserted. Before, it could be burned into the neighbouring page.
- Print and Email refuse while a redaction, mark or form entry is not applied yet; the page used to go out without it.
- Flipping quickly between pages no longer leaves the picture of one page on screen while the page counter, Delete,
  Rotate and Redact are on another.
- Typed form entries count as unsaved changes: Save keeps them, closing asks.
- Exiting ScanDesk with unsaved changes in the viewer: Cancel now really cancels (it closed anyway and discarded the edits).
- Pages dragged in from another open document are copied at once; the right page is saved whatever happens to the other.
- Marks and form text on pages turned 90 or 270 degrees land where they were drawn; the text layer of sideways scans is right.

Documents
- Deleting from a network share, a removable drive or a file too big for the Recycle Bin: Windows now asks before
  deleting for good. It used to be permanent without a word.
- Saving a rotated or cleaned JPEG, BMP, GIF or TIFF keeps the format (PNG data was written under the old name);
  multi-page TIFFs can be saved.
- Clean up > Despeckle no longer removes periods, decimal points, colons and i-dots ("2.5 mg" could become "2 5 mg").
  A small mark with print right next to it is left alone; dust that touches the print therefore stays.
- Unstacking every page of a document in a linked folder works. Bringing in a PaperPort folder by copying no longer
  copies into a linked folder of the same name.
- If links.json, tags.json or settings.json cannot be read (antivirus, power loss), the file is kept aside as
  "name.unreadable-<time>" instead of being overwritten with an empty one.
- Previous versions lists only the document's own versions. The reader adds the text layer to a page once. Image stamps
  no longer vanish. Tags follow a document through a move with a name clash and through Cut and Paste. The naming
  dialog keeps ".pdf" when the name has a period in it. A PDF whose password was removed opens at once.

Updates
- The updater now requires the checksum, accepts only https or a folder, has Windows verify that the signature covers
  the file, and insists on the very certificate that signed the installed copy. A package signed with any other
  certificate is refused, so after a certificate change each PC needs one manual install.
- Help > Copy logs for support includes all three installer logs.