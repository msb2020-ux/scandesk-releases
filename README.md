# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.14.13** (released 2026-11-23)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.14.13 - Printing works on printers that refused it; ScanDesk stays ready and opens at once; Undo a rename; Copy path (2026-11-23)
One update; 0.14.9 to 0.14.12 were trial builds and were never released on their own.

Printing
- **Fixed: on some printers, Print did nothing.** ScanDesk said the pages had been sent, and nothing came out. The
  printer's driver was refusing the way ScanDesk handed over its print jobs; this was so in every version up to
  now, with the Windows print dialog as with ScanDesk's own print window. Print jobs now go the ordinary way that
  nearly every Windows program uses, which every printer driver is built for. A printer that printed before prints
  as before.
- *Use the Windows print dialog instead* now opens the classic Windows print dialog (printer, page range, copies,
  Preferences) and prints the same way.
- **Fixed: the numbers in the print window's Copies and Pages boxes were hard to read.** In the Modern look only
  a sliver of the number showed. The same fault cut a little off the text in the search box and in the stamp
  name box of the viewer; all four now show their whole text.

Undo a rename
- **A folder or document renamed by mistake gets its old name back in two clicks.** *Edit > Undo a rename...* (also
  in a folder's right-click menu) lists the renames from the audit log, newest first: when, what it is called now,
  what it was called, in which folder, by whom. Choose one and click *Rename back*.
- Nothing is moved or deleted by this, and renaming back is itself recorded, so it can be undone in turn.
- A rename that can no longer be undone is shown in grey and says why (renamed again, moved or deleted, or
  something else has the old name now).
- After a folder is renamed, the status bar says where the way back is.
- Every rename of a folder or a document has always been recorded in the audit log with its old name, the user and
  the time; that is what this list is read from. Renames inside a private folder are not listed, because no names
  are kept for those.

ScanDesk stays ready
- **ScanDesk now opens in a fraction of a second.** It starts with Windows, hidden, and closing its window with
  the X keeps it in the notification area (the tray) instead of ending it. Opening it again is then showing a
  window, not starting a program. Measured: 0.17 seconds from the click on the shortcut, against 1.4 seconds for a
  start (and 2 to 4 seconds for the first start after an update).
- **It is started by a Windows task at sign-in.** Windows makes ordinary start-up programs wait their turn after a
  boot (measured: four and a half minutes on a PC with eight of them); a task with a sign-in trigger does not wait.
  The task belongs to your Windows user, needs no administrator rights and runs ScanDesk without raised rights. It
  is listed in Windows' Task Scheduler as *ScanDesk Desktop at sign-in*, and unticking *Keep ScanDesk ready* removes it.
- **To end ScanDesk:** *File > Exit*, or right-click its icon in the notification area > *Exit*. The first time the
  window is closed, a note at the icon says so; it is not repeated.
- **It uses little memory while hidden.** A little while after its window is closed, ScanDesk gives its memory
  back to Windows (measured: from about 200 MB to about 20 MB) and takes it again when the window is opened.
- **Updates are still found.** A ScanDesk that runs for days looks for an update when its window is opened and the
  last look is more than six hours old. The question is asked once per version, as before.
- **To turn it off:** *File > Options*, untick *Keep ScanDesk ready*. ScanDesk then starts and ends with its window,
  as it did before.
- The scanner button, the Ctrl+Alt+S hotkey, watched folders and Print to ScanDesk keep working while the window
  is closed, as they did with the old "keep in the tray" choice.

New
- **Copy path** in a document's right-click menu, right under *Copy* (also in the Edit menu, and Ctrl+Shift+C): it
  copies the complete path of the document, file name included, as text. Paste it into the *File name* box of an
  upload window (a web portal, another program) and the document is chosen without browsing to it. With several
  documents selected, all their paths are copied in the form that box takes for several files. For a document in a
  linked folder it is the path where the file really is.

Speed
- **The first folder shows as soon as the window is there.** The tray icon, the scan button's service, watched
  folders and print capture were set up between the window and the folder, and the folder waited for them (0.2 to
  0.6 seconds, measured). They are now set up right after the folder is on screen.
- **The icons of the Send To bar no longer hold the window.** Asking Windows for them took about 0.1 second inside
  every start; the bar now shows at once and its icons a moment later.
- **The first document of the day opens like every later one.** A few seconds after the start, while nobody is
  waiting, ScanDesk gets its viewer ready in the background. Measured: the first open took 0.23 seconds, now 0.11.
- The log's timing of a document now starts at the click, and the start line says what the window spent its time
  on, so a slow start on any PC can be explained from *Help > Copy logs for support*.

Fixed
- **Sending documents to the Recycle Bin could stop and never finish** when it ran in the background (the step
  after stacking documents) and several such steps came close together. Windows expects this call on a particular
  kind of thread, one at a time; ScanDesk now does exactly that.

458 automated tests pass.