# Changelog

What changed in **Bookmark Bastion**, version by version, from the point of view of someone who uses it.

## [Unreleased]

## [1.46.0] - 2026-10-18

### Added

- When you activate a Pro license, a certificate of appreciation now thanks you for your support, with fireworks, confetti and the sound of fireworks to go with them, which start gently and build over about a minute to a finale of many bursts at once, after which the last of the confetti finishes falling. Close it with the **Close** button, the **×**, **Esc** or a click outside; the sound stops when you do. If your system is set to reduce motion, you get the certificate and a soft chime without the animation.

## [1.45.0] - 2026-10-18

### Added

- **Automatic backups (Pro).** Settings → Automatic backups saves a copy of your whole library by itself, on a schedule: every 8 hours by default, or any number of days, hours and minutes you choose. The copies go into a folder inside your download folder (you pick its name), and you can compress each one into a zip file. Saved logins are included by default (still encrypted; turn that off for copies without them). You can also skip a copy when nothing has changed since the last one, and choose how many of the newest copies to keep: older ones are deleted, but only files Bookmark Bastion saved itself. **Back up now** saves one right away. Each file is named with the date and time it was made, for example `bookmark-bastion-backup-2026-10-17_14-30.json`. If your library is encrypted and locked when a copy is due, it is made as soon as you unlock. The browser asks to allow downloads when you turn it on, and the permission is given back when you turn it off.
- A new tutorial with screenshots shows how to start from a sample library for your kind of work, with its workspaces, folders and example bookmarks, or just the workspaces and folders.

## [1.44.1] - 2026-10-17

### Fixed

- The trash button on a bookmark inside a workspace now removes only that one place. If the same bookmark is also in other folders of the workspace, it stays there. A new box, “Remove it from every place in this workspace”, is available when you want the old behaviour; it is never ticked for you.

## [1.44.0] - 2026-10-17

### Added

- A theme button above your bookmarks, to the left of Add bookmark. Press it to switch between Match system (sun and moon), Light (sun) and Dark (moon); the picture shows the mode you are in. The choice in Settings is still there.

### Changed

- Encrypting the whole library (bookmark titles, addresses, notes, tags and workspace names) is now part of Pro. Your saved logins and locked notes are still encrypted for everyone. If you already encrypted your library, nothing changes: it keeps working, and you can turn it off without a license.

## [1.43.14] - 2026-10-17

### Added

- New tutorials with screenshots show how to export and import your bookmarks (including the passphrase for saved logins), the three ways to open the manager (in a tab, or in its own window from the pop-up or from the sidebar) and how to save a username and password on a bookmark and use it to sign in to a website.

## [1.43.13] - 2026-10-17

### Fixed

- Upgrading a 1-year license to the lifetime one now says what it should: you only pay the difference, another $5, so the two payments add up to the $10 lifetime price. It said another $10 before.

### Added

- Tutorials with screenshots, in the new `tutorials` folder of this page. One explains how bookmarks, workspaces and folders fit together, one shows how to change a folder's icon, and one shows step by step how to activate Bookmark Bastion Pro.

### Changed

- The logo in the manager's sidebar sits flush with the left edge and has a little more room before the title.

## [1.43.12] - 2026-10-17

### Fixed

- Installing from the zip now gives the same extension id (`ggghpopkdbjekdfgpcbhcdlhnddgpgnl`) on every computer and in every folder, and it matches the packed copy, so your library and settings stay with the extension if you move the folder.

## [1.43.11] - 2026-10-17

### Changed

- The toolbar pop-up shows the Bookmark Bastion logo next to its title instead of a generic bookmark icon, and the manager's sidebar shows the logo larger (32 px).

## [1.43.10] - 2026-10-17

### Changed

- The manager's sidebar shows the version number in small type under the title, and the button that opens the manager in its own window is centred on the title and version together.

## [1.43.9] - 2026-10-17

### Changed

- The README's steps for automatic updates now cover Brave installed as a Flatpak, and say to quit the browser completely before checking that the policy was picked up.

## [1.43.8] - 2026-10-17

### Changed

- The toolbar pop-up shows the version number in small type under its title, and its buttons are centred on the title and version together.

## [1.43.7] - 2026-10-17

### Added

- **Automatic updates (optional).** Every release now also carries a signed packed copy (`.crx`), an `updates.xml` and a browser policy file. With them, a browser on Linux, or a managed Windows PC or Mac, can install Bookmark Bastion and keep it updated by itself. The README explains the steps and the limits. The zip and **Check for updates** keep working as before for everyone else.

## [1.43.6] - 2026-10-17

### Added

- **Settings → Updates → Check for updates** asks GitHub for the newest release and tells you whether a newer version exists, with a link to its download page. It sends one request, only when you press the button, and nothing about you or your library.

### Changed

- To get Pro, choose **$5 for a 1-year license** or **$10 for a lifetime license** on Ko-fi at ko-fi.com/doggbyte. In the Ko-fi note, write which license you want and the email address to send the key to. Your key is sent within 24 hours, and Pro includes support and free updates for the length of the license you choose.
- The notices that say a feature needs Pro now have a link to the Ko-fi page, and Settings → Bookmark Bastion Pro explains how to get a key, right under the key box, including how to upgrade a 1-year license to lifetime.

## [1.43.5] - 2026-10-17

### Added

- Getting Pro is now simple: **$5 for a 1-year license** or **$10 for a lifetime license**, bought on Ko-fi at ko-fi.com/doggbyte. Settings → Bookmark Bastion Pro shows the prices and has a link to the Ko-fi page.

## [1.43.4] - 2026-10-17

### Added

- First public release. Bookmark Bastion keeps every bookmark in one place and groups them into as many workspaces as you like, without ever saving a page twice.
- Save the page you are on with one click, a keyboard shortcut or the right-click menu, and file it into one or more workspaces.
- Organise a workspace into folders, and keep the same bookmark in several folders at once.
- Add a description, a note (optionally encrypted) and tags to any bookmark, then search them.
- Link related bookmarks to each other and jump between them from a button on the card.
- Smartspaces: folders built from tags, such as a Task Manager with todo, in-progress, blocked, closed and done.
- Keep saved logins (username, password, two-factor codes) encrypted with a passphrase only you know, and fill them into the site with one click. The free version holds five; Pro removes the limit.
- Import the bookmarks already in your browser (or, with Pro, pages from its history), and see a report of exactly what was added.
- Export everything to a file and import it somewhere else, with the option to encrypt the whole library with a passphrase.
- Everything stays on your computer. There is no account, no server and no tracking.
