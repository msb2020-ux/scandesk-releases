# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.6.4** (released 2026-11-02)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.6.4 - Filing rules with preview and undo (2026-11-02)
- Edit > Filing rules (also on the Automate ribbon): the rules that recognise document types are now edited in a
  window instead of config.json. A rule can look at the sender ("comes from Mediacom"), phrases that must all occur,
  phrases that must not occur, the file name, and the usual "any of" keywords. It proposes a folder (which may use
  tokens, e.g. Bills\{org}\{year}, created when missing), a name pattern and tags.
- **Test** runs one rule over the current folder or the whole desktop and lists what it would do (document, would
  become, tags, why) without changing anything. **Queue for review** puts those proposals in the review list.
- Review window: proposals show their tags; Accept applies name, folder and tags; **Undo last** (also Edit > Undo
  last filing, Ctrl+Shift+Z) puts every document of the last accepted batch back under its old folder and name and
  removes the tags the rule added. Undone proposals are not offered again.
- The Smart Assistant uses the same rules: folder tokens are filled in, nested folders are created, and the rule's
  tags are offered.
- Indexed text keeps its line breaks from now on, so letterhead senders are also found when a document is read back
  from the index (rule tests, assistant); documents indexed earlier gain this when they are read again.
- Automatic filing stays off: rules only ever make proposals.