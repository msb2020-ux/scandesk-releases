# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.6.0** (released 2026-11-01)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.6.0 - Tabbed viewer, pages between tabs, side-by-side compare, saved workspaces (2026-11-01)
- One viewer window with a tab per document. Opening a document that is already open selects its tab. Ctrl+W
  closes a tab, Ctrl+Tab switches, the last tab closes the window; every tab gets the usual save prompt.
- Drag pages from one tab's page strip to another tab (or another viewer window): they are copied there (the
  source keeps them; delete them there to move). Dragging within a tab still reorders.
- Compare (Ctrl+Shift+D in the viewer): a second document on the right, chosen from the open tabs or any file; each
  side has its own zoom, page and tools.
- View > Workspaces: save the current arrangement (open folder, split pane, view, thumbnail size, sort order,
  assistant, Send To bar) under a name and bring it back with one click.
- Help > Invite a tester by email: opens your mail program with the beta-program page, the permanent installer link
  (GitHub Releases, latest version) and the three install steps. The releases page now carries ScanDesk-Setup.msi
  (constant name) and ScanDesk-Trust-Publisher.zip, and its README is the tester page, rewritten at every release.
- A build run from a source tree can run beside the installed ScanDesk (separate single-instance scope).