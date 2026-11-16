# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.14.1** (released 2026-11-15)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.14.1 - Office e-mail buttons, a right-click e-mail section, and one update question per version (2026-11-14)
One update that also carries everything listed under 0.13.0 below (0.13.0 and 0.14.0 were never released on their own).

New: e-mail buttons on the Send To bar
- **The office's two standard e-mail buttons are built in.** Every PC shows them after this update: the recipient's
  logo beside your mail program's icon, with the To and CC addresses already set. Nobody has to set them up, and when
  an address changes the next update changes it on every PC.
- **Drop documents on a button, or select them and click it:** the new message opens at once with each document
  attached and the addresses filled in. You read it and press Send yourself; ScanDesk never sends anything.
- Hold **Shift** while you drop or click to get the box with *Merge into one PDF* and *Password-protect* first. The
  plain Email button still shows that box every time.
- **Buttons of your own:** Send To bar > *Add... > Add e-mail button*: a name, To and CC addresses (several, separated
  by a semicolon) and, if you like, a picture such as a logo. Right-click an e-mail button > *Set addresses and
  picture...* to change it. Your own buttons belong to this PC and this Windows user.
- An office button's addresses cannot be changed on a PC; a picture of your own can replace its logo. A PC that does
  not want an office button can remove it; *Add... > Reset to the default buttons* brings it back. Removing a button
  with addresses, and Reset when you have buttons of your own, ask first.

New: right-click a document
- An **e-mail section** right under *Rotate Left / Rotate Right*: *Email...*, then one *Email to ...* line for every
  e-mail button that has addresses. Such a line opens the message at once.
- The other commands (clean up, password, print, merge, split, stacks, versions, properties) are behind **Show more**.
  Click it and they open in place; the menu remembers that, also after a restart, until you click *Show less*.

Email works differently underneath
- The Email button, the e-mail buttons and *Help > Send feedback* can no longer freeze ScanDesk: the mail program is
  asked in the background.
- Classic Outlook is asked directly, as its own program, to open the message. Other mail programs (Thunderbird,
  eM Client) are reached as before.
- If Outlook has not answered after 30 seconds, ScanDesk says so, says that nothing was sent, and keeps working; the
  message opens as soon as Outlook answers. If Outlook refuses (a dialog box is open in Outlook), ScanDesk gives the
  reason and shows copies of the documents to drag into a message.

Updates
- The "update is ready" question at start is asked **once per version**. After *Later* it does not come back at the
  next start; the status bar mentions the update, and *Help > Check for updates* names the version and installs it
  whenever it suits you. This begins with the update after this one.

Fixed
- **One drag off the desktop could count 32 times** (Auto Arrange off): the extra drags were dropped at once wherever
  the pointer was, onto a Send To button, a folder or another program. A drag now starts once.
- The same documents sent to the same Send To button twice within two seconds are sent once.
- While you drag documents across a Send To button, its highlight no longer flickers.
- Second pane: the Delete key offered to delete the document selected in the FIRST pane. It now deletes what is
  selected in the second pane; F2 and Ctrl+A, C, X, V no longer act on the first pane from there.
- Viewer: after paging with Page Down, the arrows or the mouse wheel, *Delete page* and *Rotate* acted on the thumbnail
  that was still highlighted, not on the page on screen. The highlight now follows the page on screen.
- Saving (Rotate, the viewer's Save) tries again for about a second when OneDrive or another program holds the file.

Under the hood
- ScanDesk now runs on .NET 10, supported until November 2028. Nothing has to be installed: the installer carries it.
- 336 automated tests pass.