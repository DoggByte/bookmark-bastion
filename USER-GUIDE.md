# Bookmark Bastion user guide

> This is the same guide as the one inside the extension (open the manager and choose **User guide** in the sidebar). Where it says "the manager" or "the sidebar", it means the extension's own full-page window.

<a id="welcome"></a>

## Welcome

**Bookmark Bastion** is a bookmark manager for Chromium browsers (Chrome, Edge, Brave, Vivaldi, Opera and others) that keeps every bookmark in **one place** and lets you group them into as many **workspaces** as you like, without ever saving a page twice.

This guide explains every feature and how to use it. Use the **table of contents** on the left to jump to a topic, or type in the **search box** above to find a word anywhere in the guide: matches are highlighted and the contents list shows how many each topic has.

> [!TIP]
> New here? Read [Quick start](#quick-start) (five minutes) and [Key concepts](#concepts). Everything else is reference you can come back to when you need it.

<a id="what-it-does"></a>

### What you can do with it

- Save the page you are on with one click, a shortcut or the right-click menu, and file it into one or more workspaces.
- Organise a workspace into **folders**, and keep the same bookmark in several folders at once.
- Add a **description**, a **note** (optionally encrypted) and **tags** to any bookmark, then search them.
- **Link** related bookmarks to each other (up to 3 each) and jump between them from a button on the card.
- Keep **saved logins** (username, password, two-factor codes) encrypted with a passphrase only you know, and fill them into the site with one click.
- **Export** everything to a file and **import** it somewhere else, with a report of exactly what happened.
- Everything stays on your computer. There is no account, no server and no tracking.

<a id="quick-start"></a>

## Quick start

1. **Pin the extension.** Click the puzzle-piece (Extensions) icon in your browser's toolbar and pin *Bookmark Bastion*, so its button is always visible.
2. **Save your first page.** Open any site and click the toolbar button (or press <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>S</kbd>). The pop-up is already filled in with the page's title. Tick a workspace, or type a name in **New workspace…** and press **Add**, then press **Save**.
3. **Open the manager.** Click **Manager** in the pop-up, press <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>M</kbd>, or right-click the toolbar button and choose **Options**. The manager is the full-size page you are looking at now.
4. **Bring your existing bookmarks.** On a fresh install the manager opens and offers to import the bookmarks already in your browser. You choose how they are organised, or skip it and do it later. See [Importing your browser's bookmarks](#backup-browser). Starting with nothing? An empty library can instead begin from a [sample library](#backup-samples) for your kind of work.
5. **Organise.** In the manager, click **+** next to *Workspaces* to create workspaces. Drag bookmarks from *All Bookmarks* onto a workspace in the sidebar. Use **New folder** to split a big workspace into sections.
6. **Find things.** Press <kbd>/</kbd> to jump to the search box and type a word from a title, a web address, a note or a tag.
7. **Back it up.** Open **Settings → Backup & transfer → Export JSON** and keep the file somewhere safe. See [Backup, export and import](#backup).

> [!NOTE]
> Saved logins are optional and off until you set them up. Nothing is encrypted or stored for them until you do. See [Saved logins](#logins).

<a id="concepts"></a>

## Key concepts

Knowing six words makes the rest of this guide easy.

| Word | What it means |
| --- | --- |
| **Bucket** | Where every bookmark is stored, exactly once. It is shown as **All Bookmarks**. |
| **Workspace** | A named, coloured list of bookmarks, such as *Work*, *Research* or *Home*. A workspace holds **references** to bookmarks in the bucket, not copies. |
| **Reference** | The link between a workspace and a bookmark. The same bookmark can be referenced by many workspaces. |
| **Unassigned** | Bookmarks that are in no workspace. Handy as an inbox. |
| **Folder** | An optional section inside one workspace (one level deep). |
| **Vault** | The encrypted store for saved logins and locked notes. It is opened with your passphrase. |

<a id="bucket-and-workspaces"></a>

### One bucket, many workspaces

Most bookmark tools make you choose a folder, so a page that belongs to two projects has to be saved twice, and the two copies drift apart. Here, *what you saved* is kept apart from *where you use it*:

- The **bucket** holds each bookmark once. Its title, description, note and tags live there.
- A **workspace** is an ordered list of references into the bucket.
- Edit a bookmark's title, note or tags once, and every workspace that references it shows the change.

<a id="remove-vs-delete"></a>

### Remove versus delete

These are different things, and the program always asks which you mean:

| Action | What happens |
| --- | --- |
| **Remove from a workspace** | Only the reference goes. The bookmark stays in **All Bookmarks** and in your other workspaces. This is undoable. |
| **Delete a bookmark** | The bookmark itself is deleted, and with it every reference in every workspace, and its saved login. This cannot be undone. |
| **Delete a workspace** | The workspace (and its folders) go. Its bookmarks are **never** deleted: they stay in All Bookmarks. |
| **Delete a folder** | The folder goes. Its bookmarks stay in the workspace, under **No folder**. |

<a id="install"></a>

## Installing and updating

<a id="install-unpacked"></a>

### Load it unpacked

1. Get the project folder (the one that contains `manifest.json`), or unzip `bookmark-bastion-vX.Y.Z.zip` somewhere permanent.
2. Open your browser's extensions page (the table below).
3. Turn on **Developer mode** (top right).
4. Click **Load unpacked** and select the folder.
5. Pin the extension from the puzzle-piece menu.

| Browser | Extensions page | Shortcuts page |
| --- | --- | --- |
| Google Chrome | `chrome://extensions` | `chrome://extensions/shortcuts` |
| Microsoft Edge | `edge://extensions` | `edge://extensions/shortcuts` |
| Brave | `brave://extensions` | `brave://extensions/shortcuts` |
| Vivaldi, Opera and other Chromium browsers | the same page under the browser's own prefix, such as `vivaldi://extensions` or `opera://extensions` | from the extensions page |

Keep the folder where it is: the browser reads the extension from it every time it starts.

> [!NOTE]
> The extension uses only standard Chrome extension features and needs browser version 110 or newer, which every current Chromium browser has. It is developed and tested in Brave; the other browsers are expected to behave the same but are not part of its automated tests. Firefox and Safari are not supported.

<a id="install-update"></a>

### Updating

To find out whether a newer version exists, press **Settings → Updates → Check for updates**: it asks GitHub for the newest release (one request, only when you press the button; nothing about you or your library is sent) and links to its download page. You can also open the [releases page](https://github.com/DoggByte/bookmark-bastion/releases/latest) yourself. Download the zip, replace the files with it, then press the **reload** icon on the extension's card on your browser's extensions page. Your data is stored in the browser profile, so it is kept, and it is upgraded automatically when the storage format changes.

<a id="install-move"></a>

### Moving to another computer

Nothing in your library is synced between devices. The one exception is a Pro license key, if you enter one (see [Bookmark Bastion Pro](#pro)). To move your library, export it on the old computer and import it on the new one. See [Backup, export and import](#backup).

<a id="saving"></a>

## Saving bookmarks

There are five ways to add a bookmark. All of them refuse to save the same page twice (see [Duplicates](#duplicates)).

<a id="saving-popup"></a>

### The toolbar pop-up

Click the toolbar button, or press <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>S</kbd>. The pop-up opens already filled in with the current tab.

1. Check or edit the **Title**. A description is read from the open page for you.
2. Add a **Note** (why you saved it) and **Tags** if you want.
3. Under **Workspaces**, tick the workspaces it should appear in. To make a new one, type a name into **New workspace…** and press **Add**.
4. Optionally open **Sign-in (optional, encrypted)** to save a login. See [Saved logins](#logins).
5. Press **Save**.

If the page is already in your library the pop-up shows an **Already saved** badge, fills in what you saved before, and its button reads **Update**: use it to change the existing bookmark instead of making another.

The pop-up also has a **Manager** button that opens the manager, and a small **pop-out icon** beside it that opens the manager in its own window.

> [!NOTE]
> The pop-up shows a locked note as locked and leaves it exactly as it is. Read or edit a locked note in the manager.

<a id="saving-context"></a>

### The right-click menu

Right-click any page, or any link, and choose **Save to Bookmark Bastion**. Then pick:

- **Bucket only (no workspace)**: saves it with no workspace, so it appears under *Unassigned*.
- A **workspace**: saves it there.
- For a workspace that has folders, a submenu with **No folder** and each of its folders.

A green tick flashes on the toolbar button when it worked, and a red **!** if it did not. A page that is already saved is not duplicated: it is filed into the workspace (or folder) you chose. The menu is kept up to date as you add, rename and reorder workspaces and folders.

<a id="saving-manager"></a>

### Add bookmark in the manager

Click **Add bookmark** in the manager's toolbar. Type or paste a **URL** (a bare address such as `example.com` becomes `https://example.com`), then fill in the other fields as described in [Editing a bookmark](#editing). When a workspace or folder is open, the new bookmark is pre-assigned to it.

The **QR…** button next to the URL reads the address from a picture of a QR code: choose a file, or paste a screenshot into the URL box, or drop the picture on it. The address is filled in for you to check (and the title too, when the code carries one and the Title box is empty). See [Add from a QR code picture](#saving-qr).

<a id="saving-paste"></a>

### Paste an address

Copy a web address, then either click **Paste URL** in the manager's toolbar or press <kbd>Ctrl</kbd>+<kbd>V</kbd> anywhere on the page that is not a text box.

- With a workspace (or folder) open, the page is added to it. On *All Bookmarks* or *Unassigned* it is saved with no workspace.
- The first click of **Paste URL** asks the browser for the optional *read the clipboard* permission. Ctrl+V works without it.
- Pasting several addresses at once adds them all: put each on its own line, with nothing else on the line (up to 50 at a time). A sentence that merely contains an address is not a web address.

<a id="saving-drag"></a>

### Drag an address in

Drag the page address from the browser's address bar, or a link, or a tab, onto the manager page:

- Drop it on a **workspace** or **folder** in the sidebar, or on a **folder** in the list, to add it there.
- Drop it anywhere else in the list to add it to the open workspace (and open folder). On *All Bookmarks* and *Unassigned* it is saved with no workspace.
- A hint at the bottom of the window says where it will land. A page that is open in a tab lends its title.

<a id="saving-qr"></a>

### Add from a QR code picture

A picture of a QR code that holds a web address can be added instead of typing the address, for example a photo of a poster or a screenshot sent by a friend. (Your own bookmarks make such codes: see **Show QR code** on a card.)

> **Pro:** the free version reads one picture at a time; choosing, dropping or pasting several needs [Pro](#pro).

- Click **Scan QR…** in the manager's toolbar and choose one or more pictures (up to 10 at a time).
- Or drop pictures from your file manager onto the manager page, onto a workspace or folder in the sidebar, or onto a folder in the list.
- Or paste a screenshot or a copied picture with <kbd>Ctrl</kbd>+<kbd>V</kbd> anywhere on the page that is not a text box, or copy it and click **Paste URL**.
- The bookmark goes where a pasted address would: the open workspace (and folder), or no workspace on *All Bookmarks* and *Unassigned*. A bookmark code (`MEBKM:`) that carries a title gives the bookmark that title.
- The report lists every picture. One without a usable address says why: no QR code was found, it holds a Wi-Fi code, it is a two-factor setup code (add those to a bookmark's saved login instead, see [Two-factor codes](#logins-totp)), or it holds text that is not a web address. Only http, https and ftp addresses can be bookmarked.
- Pictures are read on this device and are not uploaded or kept. A two-factor code in a picture is refused and not stored.

<a id="saving-report"></a>

### The report

After you paste or drop an address or a picture, a small report says what happened:

- **Added**, and where.
- **Not added** because it is **already in your library**. Nothing is duplicated. If it is not in the workspace you were in, the report offers **Also add it to “Workspace”**.
- **Not added** because what you pasted **is not a web address**, or because a picture **holds no web address** (the reason is listed with the picture).

<a id="duplicates"></a>

### Duplicates

The same page is only ever saved once. Two addresses count as the same page when they differ only by a `#fragment`, a trailing slash, or the letter case of the host. So `Example.com/docs/` and `example.com/docs#intro` are one bookmark.

<a id="manager"></a>

## The manager

Open the manager with the pop-up's **Manager** button, with <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>M</kbd>, or by right-clicking the toolbar button and choosing **Options**. It has three parts: the sidebar, the toolbar with its filters, and the list of bookmarks.

<a id="sidebar"></a>

### The sidebar

The sidebar on the left is your navigation. The **Bookmark Bastion** title stays at the top and **User guide**, the logins lock and **Settings** stay at the bottom; the library, smartspaces and workspaces scroll in between when there are many.

- **All Bookmarks**: the whole bucket, with a count.
- **Unassigned**: bookmarks that are in no workspace.
- **Workspaces**: each with its colour dot and bookmark count. Click one to open it. Click **+** to create a new one. A workspace's **⋯** button (or a right-click on it) opens its menu. Drag a workspace up or down to reorder.
- **Folders** of an expanded workspace are listed under it, indented, with their counts. See [Folders](#folders).
- **Smartspaces**: sets of tag folders such as *Task Manager* (to-do, in progress, done). Click **+** to create one. Its **tag folders** are listed under an expanded smartspace. See [Smartspaces](#smartspaces).
- At the bottom, below the dividing line: **User guide** (this page), **Lock Logins & Notes** or **Unlock Logins & Notes** (only once saved logins are set up; the button says what a click does, and its padlock shows the current state; when the whole library is encrypted it reads **Lock Library** / **Unlock Library** instead), and **Settings**.
- The icon at the top right of the sidebar moves the manager out of its browser tab into its own window. See [Pop-out window](#popout).

<a id="sidebar-expand"></a>

#### Expanding and collapsing

Every workspace and smartspace that has folders (or tag folders) shows a small **chevron** on its row.

- Click the **chevron** to expand or collapse that row. It does not open the workspace or change what you are looking at.
- Click a row to **open** it; it expands at the same time. Click the row that is **already open** to collapse it, and again to expand it.
- Rows are independent: opening or collapsing one never closes another, so several can stay expanded. Which ones are expanded is remembered between visits.
- A collapsed workspace or smartspace still opens its folders while you drag a bookmark over it, so you can drop straight into one.

<a id="toolbar"></a>

### The toolbar

Above the list you will find:

- The **title** of what you are viewing, and how many bookmarks it holds (`3 of 12` while a filter is active). In a workspace, hover the title to see a **⋯** button; it opens the same menu as the sidebar.
- The **theme button**, at the left of the buttons: its picture is the colour mode in use (a **moon** for dark, a **sun** for light, a **sun and moon** for match system) and each press moves to the next one. See [Themes](#theme).
- **New folder** (workspaces only), **Paste URL**, **Scan QR…** and **Add bookmark**.
- A **search box** and a **sort order**. See [Searching, filtering and sorting](#search-filter).

<a id="tagbar"></a>

### The tag bar

Under the toolbar, every tag used by the bookmarks you are looking at is shown as a chip with a count. Click a chip to filter by it; click several to show only bookmarks that have **all** of them. With two or more chips selected, a switch appears: **Show bookmarks with all / any of these tags**. *Any* shows bookmarks that have at least one of them. **Right-click a chip** to **rename** that tag. **Clear filters** appears while any filter is active.

<a id="cards"></a>

### Bookmark cards

Each bookmark is a card showing its site icon, title, web address, description, note and tags.

- **Click the title** to open the page. **Ctrl-click** (or Cmd-click) opens it in a background tab.
- A **key icon** next to the title means a login is saved. Click it to copy from the login. See [Copying from a card](#logins-copy).
- A **link icon** next to the title (after the key, if there is one) means the bookmark is linked to others. Click it to list them; choosing one opens its page. See [Linking bookmarks](#links).
- A small `HTTP auth` tag means the bookmark answers the browser's sign-in pop-up. See [Browser sign-in prompts](#logins-httpauth).
- **Tags** on a card are clickable: they filter by that tag.
- **Workspace chips** show the other workspaces that reference the bookmark. Click one to jump there.
- **Also in …** shows other folders of this workspace that also hold it.
- The buttons on the right: **Edit**, **Show QR code**, **Move to…** (in a workspace) and the **trash** button.
- **Show QR code** opens a large QR code for the bookmark's address: point a phone's camera at the screen to open the page there. The code is drawn when you open it and is not stored anywhere, so it always matches the current address. An address too long to fit in a QR code says so instead.

<a id="popout"></a>

### Pop-out window

To keep the manager beside your other windows, click the **pop-out icon**: either beside *Manager* in the pop-up, or at the top of the sidebar. The manager opens in its own window with no tabs or address bar, and clicking the icon again brings that window to the front. Any manager tab is closed when you pop it out.

<a id="theme"></a>

### Themes

Press the **theme button** at the left of the buttons above the list to change the colours: it cycles **Match system** (a sun and moon), **Light** (a sun) and **Dark** (a moon), and its picture always shows the mode you are in. You can also choose **Light**, **Dark** or **Match system** under **Settings → Appearance**. Either way it applies to the pop-up and the manager. The button is not shown while the user guide is open; use Settings there.

<a id="live"></a>

### Live updates

The manager updates by itself. A bookmark saved from the pop-up, the right-click menu or another manager window appears straight away.

<a id="editing"></a>

## Editing a bookmark

Click **Edit** on a card (or **Add bookmark** in the toolbar) to open the bookmark dialog.

| Field | What it does |
| --- | --- |
| **URL** | The web address. A bare host gets `https://`. |
| **Title** | Up to 300 characters. Leave it empty to use the site name. |
| **Description** | Up to 500 characters. See [Descriptions](#descriptions). |
| **Note** | Free text, up to 5,000 characters, with a padlock to encrypt it. See [Notes](#notes). |
| **Tags** | Short labels. See [Tags](#tags). |
| **Linked bookmarks** | Up to 3 other bookmarks this one is linked to. See [Linking bookmarks](#links). |
| **Workspaces** | Tick every workspace the bookmark should appear in. For a workspace with folders you also choose where in it. |
| **Sign-in (optional, encrypted)** | The saved login. See [Saved logins](#logins). |

Press **Save changes**. If you change a bookmark's URL to one that is already saved, you are told, and offered **Edit the existing bookmark** instead.

<a id="editing-workspaces"></a>

### Choosing workspaces and folders

Under **Workspaces**, tick each workspace the bookmark belongs to. Un-ticking a workspace removes the reference to it. When a ticked workspace has folders, toggles appear underneath: **No folder** and one for each folder. Tick as many as you like, so the bookmark sits in all of those places at once; un-ticking them all puts it at the top level.

<a id="descriptions"></a>

### Descriptions

A description is a short summary of the page, shown on the card (up to two lines) and searchable. It is read from the page's own `description`, `og:description` or `twitter:description` tag.

- **In the pop-up**, it is filled in from the open tab. Edit or clear it before saving.
- **In the dialog**, press **Fetch from page**. The first time, the browser asks for the optional site-access permission. A new bookmark fetches it by itself when you enter a URL and permission is already granted.
- **For existing and imported bookmarks**, descriptions are looked up in the background for bookmarks that have none (when site access is granted): when a bookmark is saved or imported, when the browser starts, and when you grant site access. A page is asked once; one with no description is asked again only after a month.
- A description you typed is **never overwritten**, and clearing one is respected too.

<a id="notes"></a>

### Notes

A note is plain text, up to 5,000 characters, for remembering why you saved a page.

On a card a note is shown as **one line**, ending in an ellipsis if it is longer. When something is hidden, a **Show** link appears: it opens the whole note, and **Hide** folds it back.

<a id="notes-lock"></a>

#### Locking a note

Every note is unlocked by default. To encrypt one, click the **padlock** beside *Note* in the dialog. When you save, the note is encrypted with the same passphrase as your saved logins. If you have not set that up, or it is locked, the padlock offers to set it up or unlock it.

- On the card a locked note shows **Encrypted note** and a **Show** button. Show asks for the passphrase if needed and reveals the text; **Hide** hides it again, and so does locking your logins.
- To edit it, open the bookmark: the note is decrypted into the form (after **Unlock to read** if the vault is locked). Click the padlock again to **unlock** the note, and it is stored as plain text.
- A locked note is **not searchable**, because its text is not kept in your library.
- If you export without logins, a bookmark that had a locked note is exported without a note.
- Forgetting the passphrase loses locked notes just as it loses saved logins. There is no recovery.

<a id="tags"></a>

### Tags

Tags are short labels you can filter by. They are lower-cased, trimmed and de-duplicated. Type a tag and press **Enter** or **comma** to add it. Press **Backspace** on an empty field to remove the last one. Tags you already use are suggested as you type. A bookmark can have only one tag of each [smartspace](#smartspaces).

<a id="tags-manage"></a>

### Renaming tags and removing bookmarks by tag

- **Rename a tag everywhere:** right-click it in the [tag bar](#tagbar), or use **Settings → Library clean-up → Manage tags…** and press **Rename** on its row. Every bookmark that has the tag gets the new name. If a bookmark already has the new name it just keeps one. Renaming a tag that is a tag folder renames the folder too. A rename that would leave a bookmark with two tags of one [smartspace](#smartspaces) is refused, with a message, and changes nothing.
- **Remove bookmarks by tag:** in **Manage tags…**, tick some tags, choose **all of the ticked tags** or **any of the ticked tags**, and press **Delete matching bookmarks…**. The dialog shows how many bookmarks match, and the confirmation names the tags and what goes with the bookmarks (their workspace references and saved logins). This deletes the bookmarks themselves and cannot be undone.
- Prefer to look first? Pick the tags in the tag bar (switching **all / any**), then use **Select all** and the bulk actions in [Selecting several bookmarks](#selecting).

<a id="links"></a>

### Linking bookmarks

Link bookmarks that belong together (a service and its documentation, a ticket and its pull request). A bookmark can have up to **3 links**.

- **In the dialog:** under **Linked bookmarks**, type part of a title or address and pick a bookmark from the list (click it, or use the arrow keys and <kbd>Enter</kbd>). Click the **×** on a chip to remove a link. A bookmark that already has 3 links is listed but cannot be picked.
- **By drag and drop:** hold <kbd>Shift</kbd> and drop a card on another card. The target is outlined and a hint at the bottom says what the drop will do (or why it cannot). A toast offers **Undo**. Without <kbd>Shift</kbd>, dropping still reorders or files the bookmark as before.
- **On the card:** a **link icon** appears right of the title on every linked bookmark. Click it to see the bookmarks it is linked to; choosing one opens its page, like clicking its title.
- **Links work both ways.** Linking A to B puts B on A's list and A on B's, and removing the link removes it from both. The limit of 3 applies to each bookmark, so a link is refused (with the name of the full bookmark) when either one already has 3.
- Links belong to the bookmark, not to a workspace: they show in every workspace the bookmark is in. Deleting a bookmark removes it from the links of the others.
- Links are included in exports and backups, and come back on import. A file that has links is refused by older versions of the extension rather than silently losing them. Importing never changes the links of bookmarks you already have, except to add the links a *new* bookmark brings, while both sides have room.

<a id="selecting"></a>

### Selecting several bookmarks

Tick the **box** beside a card's site icon, right of the drag handle (it is faint until you point at the card, and always shown once something is selected) to select it. A bar appears above the list with what you can do with the selection:

> **Pro:** selecting bookmarks, and dragging a selection, are part of [Pro](#pro). Without a license ticking a card shows a notice instead.

- **Select all** (every bookmark drawn in the list, so not the ones inside a collapsed folder) and **Deselect all**. **Shift+click** a box to select everything from the last one you ticked to this one. <kbd>Esc</kbd> clears the selection, and so does opening another view. A search or filter that hides a selected bookmark drops it from the selection.
- **Move to…** (in a workspace): file the selection in one of this workspace's folders, or move it to another workspace and folder.
- **Add to workspace…**: also put the selection in another workspace (and a folder of it). Bookmarks already there stay where they are.
- **Remove from workspace** (in a workspace) takes only the references out; the bookmarks stay in All Bookmarks. In a smartspace the button is **Remove from “…”** and takes the tag folder's tag off.
- **Tag…**: **Add a tag…** gives every selected bookmark a tag (a tag folder's tag replaces the other tag of its smartspace), and **Remove a tag** lists the tags the selection carries, with how many, to take one off.
- **Delete…** asks first, saying how many bookmarks and workspace references go and how many saved logins or locked notes. This deletes the bookmarks themselves and cannot be undone.

Move, Add, Remove and Tag changes have an **Undo** in the notification.

**Dragging the selection:** with two or more bookmarks selected, drag one of the **selected** cards and every selected bookmark comes along (a small label shows how many, and the cards dim). Drop them anywhere a single bookmark can go: a workspace or folder in the sidebar, a spot in the list, or a tag folder. They keep their order, follow the same rules as a single bookmark (<kbd>Ctrl</kbd> or <kbd>Alt</kbd> still copies), and one notification offers **Undo**. A card that is *not* selected drags alone and leaves the selection as it is. Linking (hold <kbd>Shift</kbd>) works on one bookmark at a time.

<a id="opening"></a>

### Opening a bookmark

Click the title to open the page in a new tab. **Ctrl/Cmd-click** opens it in the background. Some internal pages (`chrome://`, `brave://`, `file://`) can be blocked for extensions; copy the address into the address bar instead.

<a id="deleting"></a>

### Removing and deleting a bookmark

The **trash** button asks what you mean.

- **Inside a workspace**, the trash button removes **just the card you pressed it on**, and nothing else. A bookmark can sit in several places of one workspace (the top level and several folders), and only that one place goes: the dialog says so (**Remove from “Docs”?**) and names the places the bookmark stays in. Tick **Remove it from every place in this workspace** (unticked by default) to take it out of all of them. If that place is the bookmark's only one in the workspace, the dialog is **Remove from “Work”?** and the bookmark leaves the workspace. Either way the bookmark stays in All Bookmarks and in your other workspaces (or under *Unassigned* if this was its last workspace), and **Undo** in the notification puts back what was removed, folder included.
- To delete the bookmark itself, tick **Also delete this bookmark from Bookmark Bastion** (it is **unticked by default**). The dialog explains that every reference in every workspace goes too, naming each workspace and mentioning its saved login. The button becomes **Delete everywhere**. This cannot be undone.
- In **All Bookmarks** or **Unassigned** there is no reference to remove, so the trash button is a plain **Delete bookmark?** confirmation that lists the workspaces whose references will go with it.
- **Cancel**, <kbd>Esc</kbd>, or clicking outside the dialog leaves everything as it was.

<a id="workspaces"></a>

## Workspaces

A workspace is a named, coloured list of bookmarks. Create as many as you like.

<a id="workspaces-create"></a>

### Creating a workspace

Click **+** next to *Workspaces* in the sidebar. Enter a **name** (up to 60 characters, unique) and choose a **colour**. A new workspace starts on the first colour no other workspace uses. The new workspace opens straight away.

<a id="workspaces-colours"></a>

### Colours

Pick one of **32 named colours** (hover a swatch to see its name) or choose any custom colour. The colour appears on the sidebar dot, the title, the *Move to…* menu and on the folders' icons. Every colour is chosen to be visible on both the light and the dark theme.

<a id="workspaces-menu"></a>

### The workspace menu

Click the **⋯** button on a workspace in the sidebar, right-click the workspace, or hover its title in the toolbar and click **⋯**.

| Item | What it does |
| --- | --- |
| **Edit workspace** | Rename it or change its colour. |
| **New folder** | Create a folder in it. See [Folders](#folders). |
| **Open all in new window** | Opens every bookmark in a new browser window. Over 20 bookmarks, you are asked first. |
| **Export workspace** | Saves this workspace, with its folders, as a JSON file. See [Exporting](#backup-export). |
| **Delete workspace** | Deletes the workspace and its folders. Its bookmarks are **never** deleted. |

<a id="workspaces-reorder"></a>

### Reordering workspaces

Drag a workspace in the sidebar onto another one to put it before or after. A line shows where it will land.

<a id="folders"></a>

## Folders

A workspace can be split into **folders, one level deep**. Folders are purely organisational: they do not change which workspaces a bookmark belongs to, how many bookmarks a workspace has, or anything in the bucket. A workspace with no folders is a plain list.

<a id="folders-create"></a>

### Creating a folder

Open a workspace and click **New folder** in the toolbar (or use **New folder** in the workspace menu). Give it a name and, if you like, an [icon](#folders-icons). Names must be unique in the workspace, and a workspace can hold up to **50** folders.

<a id="folders-layout"></a>

### How a workspace with folders looks

Bookmarks that are not in a folder come first under **No folder**, followed by one section per folder, in **alphabetical order** (letter case and accents are ignored, and numbers sort naturally: *Folder 2* comes before *Folder 10*). The order is automatic; there is no manual folder ordering, and renaming a folder moves it to its new place.

Click a folder's name or chevron to **collapse or expand** it. This is remembered between visits. Folders of an expanded workspace are also listed in the sidebar with their counts (see [Expanding and collapsing](#sidebar-expand)).

<a id="folders-focus"></a>

### Opening a single folder

Click a folder in the sidebar to show **only that folder's bookmarks**.

- The folder is highlighted, and its workspace stays marked more quietly. The title reads *Work › Docs*.
- The count, search and tag filters apply to just that folder.
- **Add bookmark** pre-selects the open folder, and you can reorder inside it by dragging.
- Click the folder again, or its workspace, to go back to the whole workspace.
- The open folder is remembered. Deleting it returns you to the whole workspace.

While a folder is open there is no *No folder* section. To take a bookmark out of its folder, use **Move to…** or drop it on the workspace in the sidebar.

<a id="folders-move"></a>

### Moving bookmarks into folders

- **Drag** a card onto a folder (see [Drag and drop](#dnd)).
- Click **Move to…** on the card and pick a folder, **No folder**, or a folder of another workspace.
- Choose the folder in the bookmark's **Edit** dialog.
- The pop-up and the right-click menu can file straight into a folder too.

<a id="folders-several"></a>

### The same bookmark in several folders

A bookmark can sit in **any number of the folders of one workspace, and at its top level, at the same time**.

- It is shown once in each of those sections, and says **Also in …** on the card.
- It counts once in the workspace and once in each folder, and editing it changes it everywhere.
- Make one by **Ctrl/Alt-dragging** a card into another folder, by **Move to… › Also show in**, or by ticking several places in the **Edit** dialog.
- **Move to… › Remove from …** takes it out of just that one place, with **Undo**.
- Removing the bookmark from the workspace removes every place. Deleting a folder removes only that place, so a bookmark that sits only there goes to the top level.
- Its position is one position in the workspace's order, so reordering it in one folder reorders it in the others too.

<a id="folders-menu"></a>

### The folder menu

Click the **⋯** on a folder's header, click the **⋯** on its sidebar row (shown on hover), or right-click either one.

| Item | What it does |
| --- | --- |
| **Edit folder** | Rename it or change its icon. |
| **Open all in new window** | Opens every bookmark in the folder in a new window. |
| **Export folder** | Saves this folder's bookmarks as a JSON file. See [Exporting](#backup-export). |
| **Delete folder** | Deletes the folder only. Its bookmarks stay in the workspace under **No folder**. |
| **Move folder to workspace** | Sends the whole folder, with its bookmarks, to another workspace. |

<a id="folders-transfer"></a>

### Moving a folder to another workspace

Pick a workspace under **Move folder to workspace** in the folder menu, or drag the folder's row in the sidebar onto that workspace.

- The folder (name and icon) and the bookmarks in it **leave** this workspace and arrive in the other. The bookmarks themselves are untouched.
- A bookmark that also sits in another place of this workspace stays here, in that place.
- If the other workspace already has a folder of that name (in any letter case), the bookmarks **join it** instead of making a duplicate. A bookmark that workspace already holds is also filed in that folder.
- A notification says what happened and has **Undo**. A move that would take the other workspace past 50 folders is refused.

<a id="folders-icons"></a>

### Folder icons

*New folder* and *Edit folder* have an icon picker under the name.

- **Search** by name or topic (“rocket”, “money”, “server”) and narrow by **category**.
- Choose **Outline** or **Filled** style, from over 6,000 icons.
- The icon is drawn in the colour of the folder's workspace, so recolouring the workspace recolours its folders.
- **Default folder** goes back to the plain folder glyph.
- Icons are included in exports and imports. They come from the open-source Tabler Icons set.

<a id="folders-search"></a>

### Folders and searching

Searching and filtering show matching bookmarks inside their folders (expanded) and hide sections with no matches. While a search, a filter or a non-manual sort is active, dropping a bookmark on a folder still files it but does not reorder it.

<a id="folders-limits"></a>

### What folders cannot do

There is deliberately **no nesting**: a folder cannot contain another folder. Folders are always listed alphabetically.

<a id="smartspaces"></a>

## Smartspaces

A smartspace is like a workspace, but sorted by **tags** instead of by hand. Its folders are **tag folders**: a bookmark appears in one because it has that tag. You don't file bookmarks into a smartspace, and they keep all their workspaces. Every library starts with **Task Manager**, with the tag folders `todo`, `in-progress`, `blocked`, `closed` and `done`, which makes a simple to-do board. The **Smartspaces** section of the sidebar sits above Workspaces.

<a id="smartspaces-manage"></a>

### Creating and managing smartspaces

- Click **+** next to **Smartspaces** to create one. A smartspace's **⋯** button (or a right-click on it) has **Rename smartspace**, **New tag folder** and **Delete smartspace**.
- Click a smartspace to see all its bookmarks, one section per tag folder. Its tag folders are listed under it while it is expanded; click one to see just that folder.
- Drag a smartspace up or down in the sidebar to reorder them.
- A tag folder's **⋯** button (or right-click) has **Rename tag folder** and **Delete tag folder**.
- **Renaming a tag folder renames the tag on every bookmark that has it**, so they stay in the folder. (Any other tag can be renamed too: see [Renaming tags](#tags-manage).)
- **Deleting** a tag folder or a smartspace never deletes a bookmark. The bookmarks keep the tag as an ordinary tag, unless you tick **Also remove the tag from the bookmarks that have it** in the confirmation.
- Drag a tag folder onto another one of the same smartspace to reorder them. Unlike a workspace's folders, tag folders keep the order you give them.
- A tag can be a folder of only **one** smartspace.

> **Pro:** the free version has the default smartspace. Creating more is part of [Pro](#pro); the smartspaces a library already has keep working.

<a id="smartspaces-one"></a>

### One tag per smartspace

A bookmark can have **only one tag of each smartspace**. If you edit a bookmark and give it two tags of Task Manager (say `todo` and `closed`), the dialog says so and does not save until you keep just one. It can still have one tag from each of several smartspaces (say `in-progress` in Task Manager and `high` in a *Priority* smartspace), and any number of ordinary tags. Importing a file or your browser's bookmarks follows the same rule: a bookmark keeps the tag it already had, otherwise the first one in the file.

<a id="smartspaces-use"></a>

### Moving bookmarks between tag folders

- **Drag a bookmark onto a tag folder** (in the sidebar, or onto a section in the smartspace's page) to give it that tag. The tag of that smartspace it had before is **replaced**, so it moves between folders. The toast has **Undo**. From any page, hover a smartspace while dragging and its tag folders open, even when it is collapsed.
- A card's **✕ Remove from…** button takes it out of the smartspace (takes off its tag). Removing the tag in the **Edit** dialog does the same.
- A bookmark you add while a tag folder is open starts with that tag.
- Dropping a bookmark on a tag folder never moves it between workspaces.

<a id="dnd"></a>

## Moving and drag and drop

You can organise by dragging cards and rows, or by using menus. Everything drag and drop does can also be done with the **Move to…** button and the **Edit** dialog.

<a id="dnd-table"></a>

### Drag and drop reference

| Gesture | Result |
| --- | --- |
| Bookmark from **All Bookmarks / Unassigned** onto a workspace in the sidebar | Adds a reference (nothing is moved or duplicated). It lands under **No folder**. |
| Bookmark from **inside a workspace** onto another workspace | **Moves** it: removed from the source, added to the target. |
| Same, holding <kbd>Ctrl</kbd> or <kbd>Alt</kbd> | **Copies** it: it stays in the source too. |
| Bookmark onto another row in the same workspace | **Reorders** it. Needs *Manual order* and no active search or filters. |
| Bookmark onto another **card**, holding <kbd>Shift</kbd> | **Links** the two bookmarks, both ways (up to 3 each). Works in every view. See [Linking bookmarks](#links). |
| Workspace in the sidebar onto another workspace | **Reorders** the sidebar. |
| A **folder row** in the sidebar onto another workspace | **Moves the whole folder** with its bookmarks. |
| Bookmark onto a folder's header (or an empty folder) in its workspace | **Moves** it there, at the end. Places it already had elsewhere are kept. |
| Bookmark onto a row in a folder | The same, and puts it **before** that row. |
| Bookmark onto the **No folder** header | Takes it **out** of the folder it came from, to the top level. |
| Any of the three above, holding <kbd>Ctrl</kbd> or <kbd>Alt</kbd> | **Also** places it there, so it sits in both places. |
| Bookmark that is already in a folder onto **its workspace** in the sidebar | Takes it **out of its folder**, to the top level. |
| Any bookmark onto a **tag folder** of a smartspace (sidebar row or list section) | Gives it that tag and **replaces** the tag of that smartspace it had. Its workspaces are untouched. |
| With two or more bookmarks selected: one of the **selected** cards onto any of the above | The **whole selection** goes there together, in list order. See [Selecting several bookmarks](#selecting). |
| A **smartspace** in the sidebar onto another | **Reorders** the smartspaces. |
| A **tag folder** in the sidebar onto another of the same smartspace | **Reorders** its tag folders. |
| Any bookmark onto a **folder in the sidebar** | Adds it to that workspace if needed and files it in the folder. From another workspace it **moves** (Ctrl/Alt copies). |

A workspace's folders are listed in the sidebar while it is expanded, and also while a bookmark is dragged over a collapsed workspace, so you can drop straight into any of them.

<a id="dnd-moveto"></a>

### The Move to… menu

The **Move to…** button on a card (a folder with an arrow, shown in any workspace view) opens a menu:

1. **In this workspace**: pick **No folder** or a folder to **move** the card there. A ✓ marks the places it already sits in.
2. **Also show in**: pick a place to **add** the bookmark there too, so it sits in several places.
3. **This place › Remove from …**: take it out of just this one place.
4. **Move to another workspace**: every other workspace with its folders. Pick one to move the reference there in one click.

Moved to another workspace, the reference leaves the current one (the bookmark itself is untouched). The notification's **Undo** puts it back in its old places and position.

<a id="dnd-reorder"></a>

### Reordering

Drag a card above or below another to reorder it. This needs the sort order to be **Manual order** and no search or tag filter to be active; otherwise the list is showing a different order and there is nothing to reorder.

<a id="search-filter"></a>

## Searching, filtering and sorting

<a id="search"></a>

### Search box

Click the search box or press <kbd>/</kbd> anywhere on the page (outside a text field). Press <kbd>Esc</kbd> to clear it.

- Plain words must **all** match somewhere in the title, web address, description, note or tags. `docs api` finds bookmarks containing both words.
- Words starting with **#** match **tags only**. `#recipes` finds bookmarks tagged *recipes*.
- Search works inside the view you are in: All Bookmarks, Unassigned, a workspace or a folder.
- The text of a locked note cannot be searched.

<a id="search-tags"></a>

### Tag filter

Click tags in the tag bar or on a card. Selecting several shows only bookmarks that have **all** of them. Click a selected tag again to remove it.

<a id="sort"></a>

### Sort order

| Sort | Meaning |
| --- | --- |
| **Manual order** | Your own order, set by dragging. Only available inside a workspace; elsewhere it behaves like *Newest first*. |
| **Newest first** / **Oldest first** | By when the bookmark was saved. |
| **Title A–Z** | Alphabetical. |

Your sort choice is remembered. **Clear filters** resets the search and tags in one click. Switching to another view also clears them.

<a id="logins"></a>

## Saved logins

A bookmark can remember the **username and password** for its site, and fill them in for you when the site asks you to sign in. It can also hold a **two-factor key**. This is optional: until you set it up, nothing is stored or encrypted and the rest of the extension works exactly as before.

> The free version keeps up to **5** saved logins (bookmarks that have one) and **one account** on each; [Pro](#pro) has no limit on either. A login you already have can always be changed, and a backup with more logins still imports in full.

> [!WARNING]
> **Read this first.** Each login is encrypted on your device with a random key that a **passphrase you choose** protects. The passphrase is never stored anywhere. **Without it your saved logins cannot be decrypted by anyone, and there is no recovery.** If you forget it, the only option is to delete the saved logins and start again.

Only logins and the [notes you lock](#notes-lock) are encrypted. Titles, web addresses, other notes and tags are stored as normal, unless you also [encrypt the whole library](#logins-library).

<a id="logins-setup"></a>

### Setting it up

1. Open **Settings → Saved logins → Set up encrypted logins…**. (The same button appears in a bookmark's Edit dialog and in the pop-up.)
2. Choose a passphrase of **at least 12 characters**. Several random words are strong and easy to remember. A strength hint is shown.
3. Tick *“I understand that if I forget this passphrase, my saved logins cannot be recovered.”* and confirm.
4. Open any bookmark → **Edit**, scroll to **Sign-in (optional, encrypted)** and enter the username and password. Press **Save changes**.

A small **key icon** on the card shows that a login is saved. You can also add or change a login from the pop-up's collapsible **Sign-in** section.

<a id="logins-accounts"></a>

### Several accounts on one bookmark

Some sites have more than one user behind the same sign-in page: a personal and a work account, or a few people sharing one bookmark. A bookmark can keep **several accounts**, each with its own username, password and [two-factor key](#logins-totp).

> **Pro:** more than one account on a bookmark is part of [Pro](#pro). The free version keeps one account on each bookmark. Accounts you already have are never removed if a license lapses.

1. Edit the bookmark (or open the pop-up's **Sign-in** section) and press **Add another account** under the login. A second set of boxes appears.
2. Fill in the username, password and, if the site asks for it, the authenticator key. Repeat for as many accounts as you need (up to 20).
3. Press **Save changes**. An account left completely empty is not saved.

With two or more accounts each one gets a heading and three small buttons: **move up**, **move down** and **remove this account**. The order is the order of the list when you [fill a login](#logins-fill). The first account is the one that answers a [browser sign-in pop-up](#logins-httpauth), because a pop-up cannot ask you which one you want. **Remove saved login** removes every account on the bookmark.

<a id="logins-fill"></a>

### Filling a login

1. Open the site's sign-in page.
2. Click the toolbar button. A **Saved login for this site** card appears when a bookmark with a saved login matches the page. Press **Fill login**, or **Unlock and fill** and enter your passphrase if the vault is locked. With several matches there is one **Fill: title** button for each.
3. If the bookmark has [several accounts](#logins-accounts), a **list of their usernames** appears beside the button. Choose the account you want and press **Fill**. (The usernames are encrypted, so when the vault is locked the list appears after you unlock: choose, then press **Fill**.) The account you used last is selected next time.
4. Or press <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>L</kbd> to fill without opening the pop-up. When the bookmark has several accounts the shortcut fills nothing: it opens the pop-up so you can choose.
5. Review the form and sign in yourself. **The extension never submits the form for you.**

The toolbar button briefly shows what happened:

| Badge | Meaning |
| --- | --- |
| ✓ (green) | The login was filled. |
| **1/2** (amber) | Only the username was filled; the password will be filled when its screen appears. |
| **?** (amber) | No saved login matches this page. |
| **LOCK** (amber) | The vault is locked. Unlock it from the pop-up or the manager first. |
| **▾** (amber) | The bookmark has several accounts. Choose one in the pop-up, which opens. |
| **!** (red) | The form could not be filled. |

The toolbar icon itself also shows whether the vault is locked: while it is locked the icon changes to a **locked version with a padlock**, and it goes back to normal once you unlock it. Until you set up saved logins the icon never shows the padlock.

<a id="logins-twostep"></a>

### Two-step sign-in pages

Some sites ask for the username first and the password on the next screen. After a username-only fill, press the page's **Next**: the page is watched for its password screen, and the password is filled when it appears. If a verification-code screen follows, it is filled too, so you go *username → Next → password → Sign in → code* from one click.

The watch is deliberately narrow: only that page, for at most **90 seconds**, one visible password box, filled once, never submitted, and replaced by any newer fill. If the page reloads instead of swapping screens, or the watch has ended, fill again.

<a id="logins-safety"></a>

### Safety rules

These rules are built into the code, not only the screens:

- A login is only offered for a page whose **origin matches exactly** (scheme, host and port). `app.example.com` never matches a login saved for `example.com`, and `http` never matches `https`.
- Nothing is filled on plain **`http://`** pages, because your password would cross the network unencrypted. The exception is `localhost`.
- A matching page's **frames from other origins never receive the login**.
- Filling only happens when **you** click the button or press the shortcut. There is no automatic fill on page load and no prompt in web pages.
- The extension has no standing access to any site. It uses the browser's `activeTab` permission, which lasts for the moment you ask.
- There is no way to widen that: a login is never offered on another site, and an import can never turn on answering browser pop-ups for a bookmark you already have.

<a id="logins-httpauth"></a>

### Browser sign-in prompts

Some sites (intranet pages, routers, staging servers) answer with “401 Unauthorized”, and the browser shows its own username and password pop-up. To have your saved login answer that pop-up:

> **Pro:** answering the pop-up is part of [Pro](#pro). Without a license the tick box can't be turned on and the browser shows its own pop-up.

1. Edit the bookmark, tick **Answer the browser’s sign-in pop-up on this site** and save the login.
2. Open **Settings → Saved logins → Browser sign-in prompts** and press **Turn on…**. This asks for the optional `webRequest`, `webRequestAuthProvider` and all-sites permissions. Nothing is requested at install.

It is narrow on purpose:

- Only a bookmark with that box **ticked** is used. An ordinary website login is never sent to a pop-up.
- With [several accounts](#logins-accounts) on the bookmark, the **first** one that has a username or a password answers.
- Only for **the page you are opening**, never for an image, script or frame another page embeds.
- The address must be **https** (or `localhost`) and match the bookmark's origin exactly.
- **Proxy** sign-in prompts and other schemes (NTLM, Kerberos) are never answered.
- Each request is answered **once**. If the server refuses the login, the browser's own pop-up appears instead of looping.
- The vault must be unlocked. Otherwise the badge shows **LOCK** and the browser's pop-up appears.

Turn it off again in the same place.

<a id="logins-totp"></a>

### Two-factor codes

A login can hold the **authenticator key** that apps like Google Authenticator, Microsoft Authenticator or Authy use, so the code is generated and filled for you.

1. When a site offers two-factor sign-in with an authenticator app, choose **enter the key manually** (or *can't scan the QR code*). Copy that text, or the `otpauth://` link if the site shows one.
2. In the bookmark's Sign-in section, paste it into **Authenticator key**, or read it from a QR picture (see [Scanning a QR picture](#logins-qr)).
3. A valid key immediately shows the **current code** with a countdown and a Copy button. Check it against what the site asks for. A key the extension cannot use is refused, with the reason, and nothing is saved.
4. Save. The key is **encrypted with the login**: same passphrase, same backups, and re-encrypted when you change the passphrase.

**Filling:** when you fill a login, any verification-code box on the page gets the current code. That includes boxes marked as a one-time code, boxes named like `otp`, `totp`, `verification code`, `security code` or `2fa`, and a row of single-character boxes as long as the code. A page that shows only the code box gets just the code.

The page is **never given the key**, only the codes for the next minute and a half. Page scripts cannot read them, and they are dropped when the watch ends.

<a id="logins-totp-types"></a>

#### Supported key types

- **Time-based (TOTP)**: `SHA1` (the usual), `SHA256` and `SHA512`; 6, 7 or 8 digits; periods of 10 to 120 seconds (30 is usual).
- **Counter-based (HOTP)**: paste an `otpauth://hotp/…` link or scan its QR code. The form shows the code for the saved counter with a **Next code** button. Each time a fill actually enters the code, the counter moves on by one.
- **Steam Guard**: an `otpauth://steam/…` or `steam://SECRET` link gives Steam's five-character codes.
- **Google Authenticator transfer codes** (*Transfer accounts → Export*): scan the QR picture, then pick the account for this site from the list (a login holds one key). A large export split over several QR codes says which part you scanned; scan each in turn.
- **Codes split over one box per digit** are filled one digit per box, masked boxes included.

Not supported: push approvals, SMS or e-mail codes, and keys that are not one of the kinds above.

> [!IMPORTANT]
> A second factor stored next to the password is **less independent** than one on a separate device. It is convenient and still encrypted, but if you rely on two-factor to protect against someone who has your passphrase, keep the key in a separate authenticator app.

<a id="logins-qr"></a>

### Scanning a QR picture

Instead of typing the key, give the form a picture of the QR code the site showed. A screenshot is fine.

- **In the Add / Edit dialog:** press **Scan QR image…** to choose a file, drop a picture on the key box, or paste a screenshot with <kbd>Ctrl</kbd>+<kbd>V</kbd> anywhere in the Sign-in section.
- **In the pop-up:** paste a screenshot or drop the picture. (There is no file button, because the browser closes the pop-up when the system file dialog opens.)
- PNG, JPEG, WebP and GIF up to 10 MB. A small code inside a big screenshot, and light-on-dark codes, are found.
- The key box is filled and the live code appears so you can check it. The status line names the account the code was for.
- A picture that is not a usable key is refused with the reason: no QR code found, not an authenticator code, or a damaged transfer code.

**Privacy of the picture.** It is read on your device and leaves no trace. It is never uploaded, and only ever held in memory: not written to extension storage, browser storage, a cache or a database, and never shown on the page. As soon as the text has been read, every pixel buffer made along the way is overwritten with zeros. A screenshot you **paste** is also on the system clipboard, so after a code is read from it the clipboard is replaced with a blank. (Your operating system's own “recent files” list, which the extension cannot reach, may still name a file you picked.)

<a id="logins-copy"></a>

### Copying from a card

A bookmark with a saved login shows a **key button**. Click it to copy, without opening the editor:

- the **username**,
- the **password**,
- or the current **authenticator code**.

With [several accounts](#logins-accounts) each item says whose it is, for example *Copy password: alice*.

A counter-based code moves its counter on when copied. The passphrase is asked first if the vault is locked.

<a id="logins-clipboard"></a>

### Clipboard clearing

A copied password or code (not a username) is wiped from the clipboard after the time in **Settings → Saved logins** (30 seconds by default; 1 or 2 minutes, or never).

- It happens even if the page that copied it was closed or the browser is in the background.
- The clipboard is replaced with a blank.
- If the clipboard can be read and you have copied something else in the meantime, that is left alone.

<a id="logins-lock"></a>

### Locking and unlocking

After you enter the passphrase the vault stays **unlocked until the browser closes**, and **locks automatically after 15 minutes of not being used**. Using a login resets the countdown.

- Change the delay under **Settings → Saved logins → Auto-lock**: 5, 15, 30 or 60 minutes idle, or only when the browser closes.
- The vault also **locks the moment your computer's screen locks** (Windows+L, closing a laptop lid and so on), and a copied secret is wiped from the clipboard at the same time. Turn this off with **Settings → Saved logins → Lock saved logins when the computer’s screen locks**.
- Lock it any time with the **Lock Logins & Notes** button at the bottom of the manager's sidebar, or **Settings → Saved logins → Lock now**. While locked, the same button reads **Unlock Logins & Notes**; click it to unlock again. If your whole library is encrypted, the button is called **Lock Library** / **Unlock Library**.
- Seeing *which* bookmarks have a login never needs the passphrase. Seeing or filling the login itself does.
- Locking the vault also hides any locked notes you were showing.

<a id="logins-reset"></a>

### Changing the passphrase or starting over

- **Change passphrase or method…** (Settings → Saved logins) asks for the current passphrase, then protects the vault's key with the new passphrase and, if you choose, a different **key-derivation method** (you can keep your passphrase and change only the method). No saved login or locked note is touched, so nothing can be lost halfway. A backup of this same vault made earlier still imports into it without a passphrase; on another device it needs the passphrase it was exported with.
- **Delete all saved logins…** permanently removes the vault, every saved login and the text of every locked note. Use it if you have forgotten the passphrase. Your bookmarks are not affected (those with a locked note lose the note).
- Deleting a bookmark deletes its saved login and locked note too. Removing a login from a bookmark removes only the login.

<a id="logins-library"></a>

### Encrypting the whole library (optional)

> **Pro:** turning on encryption of the whole library is part of [Pro](#pro). Your saved logins and locked notes are encrypted without a license. A library that is **already encrypted** keeps working, and you can unlock it and **Turn off…** with or without a license; a license that ends never locks you out of your bookmarks.

By default only logins and locked notes are encrypted. Anyone who copies your browser profile can still see the titles, web addresses, notes and tags of your bookmarks. **Settings → Saved logins → Encrypt the whole library…** (off by default) encrypts those too, with the same key that protects your logins, so nothing readable is left in the browser's storage.

- The dialog explains what changes and asks you to confirm that **without your passphrase the library cannot be recovered**. It also offers to export a backup first.
- **While the vault is locked** (after the idle time, when the screen locks, or when the browser closes) the manager and the pop-up show a passphrase prompt instead of your bookmarks. The right-click menu offers only *Unlock to save…*, and saving, looking up descriptions and filling wait until you unlock.
- Changing your passphrase or its method does not affect it. Using the manager or the pop-up counts as activity, so the idle lock does not catch you mid-work.
- **Turn off…** in the same place stores your library as readable text again.
- **Forgot the passphrase?** on the lock screen erases everything this extension holds (after a confirmation) and starts afresh. **Delete all saved logins…** is refused while the library is encrypted.
- Exports are still plain-text files: keep them somewhere safe. Text that was stored before you turned this on may stay readable in the browser's files until it tidies them, so this protects what you save from now on.
- It needs your saved logins set up and unlocked. A vault made by an older version is brought up to date by unlocking it once.

<a id="logins-backup"></a>

### Exporting and importing logins

When you press **Export JSON** and you have saved logins or locked notes, you are asked:

- **Without passwords** *(default)*: bookmarks, notes, tags and workspaces only. No login information leaves the browser.
- **With encrypted logins** (and notes): also includes them, **still encrypted**. The file holds only the encrypted data and the settings needed to derive the key, never your passphrase or any plain-text password. Keep your passphrase safe: you need it to import them on another device.

Exporting never needs the vault to be unlocked. When importing a file that contains logins or locked notes you are offered **Also import N saved logins and M locked notes** and asked for **the passphrase used when the file was exported**:

- On a device with no vault yet, that passphrase becomes the vault passphrase.
- On a device with a different vault, you unlock your own vault first and the imported logins are re-encrypted for *your* vault.
- A wrong passphrase changes nothing at all: no bookmarks are imported and no vault is created.
- **Merge** never overwrites a login or note you already have. **Replace** replaces your logins and locked notes along with the library.

<a id="logins-security"></a>

### How it is protected

| Layer | Detail |
| --- | --- |
| Key hierarchy | A random 256-bit **vault key** encrypts every login and note. Your passphrase only protects (wraps) that key, so changing the passphrase never touches your logins. |
| Key derivation | **PBKDF2-HMAC-SHA256, 600,000 iterations** (default), or **Argon2id** (64 MiB, 3 passes, 4 lanes), which needs memory as well as time and so is much harder to guess at on graphics cards or custom chips (unlocking takes about a second). Random 16-byte salt. The passphrase is Unicode-normalised. |
| Encryption | **AES-256-GCM**, a fresh random IV for every login, using the browser's built-in Web Crypto. Argon2id, only if you choose it, is the open-source *hash-wasm* library, included with the extension and checked against a known fingerprint. |
| Integrity | GCM detects tampering or a wrong key. Each login and note is bound to its bookmark, so it cannot be moved onto another one. |
| Passphrase check | None is stored. A wrong passphrase simply fails to unlock the vault key, so there is no hash to attack. |
| Updates | A vault made by an older version moves to this layout, in one step, the next time you unlock it. A PBKDF2 vault below 600,000 iterations is raised to it. Your choice of method is never changed for you. |
| At rest | Only ciphertext is written to the browser's storage. The passphrase and key are never stored on disk. |
| While unlocked | The key is held only in the browser's memory (session storage). It is cleared on lock and when the browser closes. |

<a id="logins-limits"></a>

### What this does and does not protect against

- ✅ Someone who copies your browser profile, a backup or an export file **cannot read your logins without the passphrase**.
- ✅ Page content, other extensions and websites cannot read the vault. A website only sees a login you chose to fill into it.
- ⚠️ **A weak or reused passphrase can be guessed offline**, even with 600,000 iterations. Use a long, unique passphrase.
- ⚠️ While the vault is **unlocked**, malware running as you, or someone using your unlocked browser, can use it. Lock it when you step away.
- ✅ A fill goes only into frames on the login's exact origin, never into an embedded frame from another site, and only into fields you could see: not transparent, off-screen, tiny or covered by something else.
- ✅ The extension is locked down against other extensions and web pages: nothing is exposed to them, they cannot send it messages, and its own pages run under a strict security policy.
- ✅ Locking the vault reloads the manager and closes the pop-up, so text they had decrypted does not stay in memory. (If a dialog is open, this waits until you close it, so nothing you were typing is lost.)
- ⚠️ When you fill a login, the page's own scripts **and any other browser extension that can access that page** can read the values from the form, as with any autofill. That is why fills only happen on an exact-origin match over HTTPS and only when you ask.
- ⚠️ A program that can read your browser's memory while the vault is unlocked is beyond what an extension can defend against.
- ⚠️ Titles, web addresses, tags and notes you have not locked are **not encrypted** unless you [encrypt the whole library](#logins-library), so by default a stolen profile still reveals which sites you have bookmarked.
- ⚠️ This is a convenience for the bookmarks you already keep here, **not a full password manager**: there is no password generator, breach monitoring, cross-device sync or recovery.

<a id="settings"></a>

## Settings

Open **Settings** at the bottom of the manager's sidebar. Changes are saved as soon as you make them; press **Done** to close.

| Setting | Default | Notes |
| --- | --- | --- |
| **Site access** | Not granted | Optional permission to read the pages of your bookmarks for descriptions. **Grant access** / **Revoke access**. Revoke it for no background network traffic at all. |
| **Browser sign-in prompts** | Off | Optional permissions that let a saved login answer a browser sign-in pop-up. See [Browser sign-in prompts](#logins-httpauth). |
| **Saved logins** | Not set up | **Set up encrypted logins…** (you choose the key-derivation method), then **Lock now / Unlock…**, **Change passphrase or method…** and **Delete all saved logins…**. |
| **Auto-lock** | After 15 minutes idle | Only when the browser closes, or after 5, 15, 30 or 60 minutes without use. |
| **Encrypt the whole library** | Off | Also encrypts titles, addresses, notes, tags and workspace names. Needs an unlocked vault and [Pro](#pro). See [Encrypting the whole library](#logins-library). |
| **Lock saved logins when the computer’s screen locks** | On | Lock the vault and wipe a copied secret as soon as the operating system locks the screen. |
| **Clear copied secrets from the clipboard** | After 30 seconds | Never, or after 30 seconds, 1 or 2 minutes. Not applied to a copied username. |
| **Bookmark Bastion Pro** | Free version | Enter or remove a license key. See [Bookmark Bastion Pro](#pro). |
| **Theme** | Match system | Light, dark or follow the system. |
| **Updates** | | **Check for updates** asks GitHub whether a newer version exists. See [Updating](#install-update). |
| **Library clean-up** | | **Manage tags…** See [Library clean-up](#cleanup). |
| **Backup & transfer** | | **Export JSON**, **Import JSON…** and **Paste JSON…**. See [Backup, export and import](#backup). |
| **Automatic backups** | Off | Saves a copy of your library on a schedule. Needs [Pro](#pro). See [Automatic backups](#backup-auto). |
| **Start fresh** | | **Erase everything…** deletes every bookmark, workspace, note, saved login and setting from this browser, after you confirm, and starts again as if the extension was just installed. It can’t be undone, so export a backup first. |

The settings dialog also shows the version number you are running.

<a id="pro"></a>

## Bookmark Bastion Pro

The extension is free to use. **Pro** is an optional license that unlocks more.

| | Free | Pro |
| --- | --- | --- |
| Bookmarks, workspaces, folders, tags, drag and drop, search, the pop-up | Everything | Everything |
| Export and import (including your browser's bookmarks) | Everything | Everything |
| [Saved logins](#logins) | Up to **5** | No limit |
| [Several accounts on one bookmark](#logins-accounts) | One | Up to 20 |
| [Encrypting the whole library](#logins-library) | | Included |
| [Browser sign-in prompts](#logins-httpauth) | Not answered | Answered from a saved login |
| [Smartspaces](#smartspaces) | The default one | Create your own |
| [Importing browser history](#backup-history) | | Included |
| [Automatic backups](#backup-auto) | | Included |
| [Selecting several bookmarks](#selecting) and dragging the selection | | Included |
| [Scanning QR pictures](#saving-qr) | One picture at a time | Up to 10 at a time |

Without a license nothing is ever hidden or deleted: logins, smartspaces and settings you already have stay readable, usable and exportable (the exceptions are that browser sign-in prompts are not answered and that [encrypting the whole library](#logins-library) can't be turned on; a library that is already encrypted keeps working and can be turned off without a license). A control that needs Pro carries a **PRO** badge, and clicking it always says so, with an **Add license key** button that opens (or jumps to) this part of Settings.

- **Getting Pro.** Go to [ko-fi.com/doggbyte](https://ko-fi.com/doggbyte) and choose **$5 for a 1-year license** or **$10 for a lifetime license**. **In the Ko-fi note, write which license you want (1-year or lifetime) and the email address to send the key to.** Your license key (it starts with `BB1.`) is sent to that address within 24 hours. Pro includes support and free updates for the length of the license you choose. The same link is in **Settings → Bookmark Bastion Pro**, under the key box, and in every notice that says a feature needs Pro.
- **Upgrading from 1 year to lifetime.** Make another **$5** payment on Ko-fi: you only pay the difference, so the two payments add up to the $10 lifetime price. Write in the note that it is an upgrade, together with the activation key of your 1-year license and the email address to send the new key to.
- **Entering a key.** Open **Settings → Bookmark Bastion Pro**, paste the key (it starts with `BB1.`; spaces and line breaks from a copied key are ignored) and press **Activate** or Enter. A thank-you certificate opens with fireworks and confetti and their sound, which start gently, build up to a finale of many bursts at once over about a minute, and then let the last confetti fall (a soft chime and no animation if your system asks for reduced motion); press **Close**, **Esc** or click outside it to dismiss it at any time, which stops the show and the sound. The status line then says who the license is for and when it ends, if it ends.
- **Checked on your computer.** The key carries a digital signature that the extension checks itself. Nothing is sent anywhere, no account is needed, and Pro works without a network connection. A key that was changed, cut short or made for something else is refused with a message and is not saved.
- **A license with an end date** keeps working for 14 days after that date, so a renewal that is a little late costs nothing. After that the extension goes back to the free version; nothing you saved is deleted, and entering a renewed key turns Pro on again.
- **Removing it.** **Remove license…** turns Pro off. Your bookmarks, logins and settings are untouched.
- **Your other browsers.** The key is stored in the browser's synced extension storage, so it appears in your other browsers that are signed in to the same browser account (if that browser syncs extension data). It is not part of your library: **Export JSON** does not include it, and **Erase everything** does not remove it. Keep the key somewhere safe; you can enter it again at any time.

<a id="cleanup"></a>

## Library clean-up

**Settings → Library clean-up → Manage tags…** renames a tag on every bookmark that has it and can delete the bookmarks that carry all of, or any of, some tags. See [Renaming tags and removing bookmarks by tag](#tags-manage).

There is no separate duplicate finder: the same page (ignoring a `#fragment`, a trailing slash and host or scheme case) is only ever saved once. Saving, editing a web address, importing a file, your browser's bookmarks or its history all match what you already have instead of making a second copy. See [Duplicates](#duplicates).

<a id="backup"></a>

## Backup, export and import

<a id="backup-export"></a>

### Exporting

**Settings → Backup & transfer → Export JSON** saves your whole library as a file: bookmarks, descriptions, notes, tags, links between bookmarks, workspaces, folders and their icons, and your settings. If you have saved logins or locked notes you are asked whether to include them (still encrypted). See [Exporting and importing logins](#logins-backup).

To save only part of it, use **Export workspace** in a workspace's menu or **Export folder** in a folder's menu. The file has the same format, but holds just that workspace (or the bookmarks in that folder), and only their saved logins and locked notes can be included. Links to bookmarks outside the file are left out. **Merge**-importing it puts the bookmarks back into a workspace and folder of the same names; choosing **Replace** with such a file would replace your whole library with only that part.

<a id="backup-import"></a>

### Importing

Either choose a file with **Import JSON…**, or click **Paste JSON…**, paste the file's text into the box and press **Check and continue**. Both go through exactly the same checks and the same review step. Nothing changes until you press **Import**, and pasted text is cleared afterwards.

The review step shows what the file contains, lets you choose **Merge** or **Replace**, and asks for the passphrase if the file holds saved logins. It also says what *Merge* would do with your library: how many items are new and how many exact duplicates would be ignored.

<a id="backup-browser"></a>

### Importing your browser's bookmarks

The bookmarks you already keep in the browser can be brought in, and you choose how they are organised. A fresh install opens the manager and offers this once; if you skip it, use **Settings → Backup & transfer → Import browser bookmarks…** at any time.

The browser asks you to allow *reading your bookmarks* (the optional `bookmarks` permission). Your browser's bookmarks are only read: nothing in the browser is changed or deleted, and the permission is given back as soon as the dialog closes.

A *top-level folder* is a folder directly inside the browser's own containers (**Bookmarks bar**, **Other bookmarks**, **Mobile bookmarks**). Pick one of four ways to organise the import:

| Choice | What you get |
| --- | --- |
| **Workspaces with folders** | Each top-level folder becomes a workspace, and its sub-folders become that workspace's folders. Anything nested deeper is folded into its sub-folder. Bookmarks directly inside the top-level folder stay at the workspace's top level. |
| **A workspace per folder** | Each top-level folder becomes a workspace with everything nested under it inside, without folders. |
| **One “Imported Bookmarks” workspace** | A single workspace. Each top-level folder becomes a folder in it, with everything below that folder inside. |
| **Just add them, flat** | Every bookmark goes into *All Bookmarks* only. No workspaces or folders are made. |

- **Bookmarks that are not in a folder** go to a workspace named after where they were (such as *Bookmarks bar*), or to the top level of *Imported Bookmarks*, or only into *All Bookmarks* for the flat choice.
- **What to import** lists every top-level folder and container with its number of bookmarks. Untick what you do not want.
- **Keep folder names as tags** (off by default) tags each bookmark with the names of the folders the choice folds away, so that information is not lost.
- **Nothing is added twice.** A page you already have is not copied: the workspace refers to the bookmark you have, and your title and note are kept. A page that sits in several browser folders becomes one bookmark that appears in each place. Folders and workspaces are matched by name, so importing again changes nothing.
- A workspace holds at most 50 folders. If more would be needed, the extra folders' bookmarks go to the workspace's top level, tagged with the folder's name, and the dialog says so. Folders with no bookmarks in them are not created, and addresses that cannot be saved (such as bookmarklets) are skipped and counted.
- Before you press **Import** the dialog says what would happen to your library. Afterwards a report shows what was added.

<a id="backup-history"></a>

### Importing pages from your browser history

Pages you visited can be saved as bookmarks: **Settings → Backup & transfer → Import browser history…**. Your browser history is only read: nothing in it is changed or deleted, and nothing leaves the browser. The browser asks you to allow *reading your history* (the optional `history` permission) and its prompt may word that as "read and change", which is the browser's fixed text for this permission; Bookmark Bastion never writes to your history. The permission is given back as soon as the dialog closes.

> **Pro:** importing from your browser history is part of [Pro](#pro).

The next screen lists the pages from your history, newest first:

- **Show** picks the time range: the last 24 hours, 7 days, **30 days** (the default), 90 days or all time. At most the 5,000 most recent pages are listed; a note says so when the list is cut off, so choose a shorter range or filter to find others.
- **Filter** narrows the list to pages whose title or address contains your words.
- Tick the pages you want, or use **Select all** (it covers the pages shown, so filter first to select a group). The count shows how many are ticked.
- A page you already have as a bookmark is marked **Already saved** and is not ticked by *Select all*. If you tick one anyway it is reused, never copied or changed: it is only placed where you chose.
- **Import to** is **Unassigned** by default, so the bookmarks wait in *Unassigned* until you sort them. Choose any workspace (and one of its folders) instead, or **New workspace…** and give it a name; a name that is already taken is refused, so pick that workspace from the list.
- **Tag them “from-history”** (off by default) tags the new bookmarks so you can find them later. Pages you already have are left as they are.
- Before you press **Import** the screen says what would happen. Afterwards a report shows what was added and what was ignored because you already had it.

<a id="backup-auto"></a>

### Automatic backups

> **Pro:** automatic backups are part of [Pro](#pro). Backups already saved are never deleted if a license ends.

**Settings → Automatic backups** saves a copy of your whole library by itself, on a schedule, while the browser is open. Each copy is the same file **Export JSON** makes, so you restore one with **Import JSON…** like any other. Press **Enable backups…**: the browser asks to allow *downloads* (that is how a copy is saved), a first backup is made straight away, and the next ones follow on the schedule. **Disable backups** stops it and gives the permission back; the backups already saved stay where they are.

- **Back up every.** Days, hours and minutes, from 5 minutes to 30 days. The default is every 8 hours. If the browser was closed when one was due, it is made when the browser starts.
- **Folder.** A folder **inside your browser's download folder** (an extension can't write anywhere else by itself). The default is *Bookmark Bastion backups*. Use `/` for a folder inside a folder; the folder is created if it doesn't exist. Characters a computer would refuse in a name are dropped, and there is no way to point outside the download folder. To end up somewhere else, change the browser's own download folder, or make the backup folder a link to the place you want.
- **Compress each backup into a .zip file.** Off by default. The zip holds the same JSON file.
- **Include saved logins and locked notes.** On by default. They stay encrypted in the file, exactly as when you export with passwords, and you need your passphrase to bring them back. Turn it off for backups without any login information. The file name ends in `-with-logins` when logins are inside.
- **Skip a backup when nothing has changed since the last one.** Off by default, so a backup is always made at the set interval. When it is on, a backup that would be identical to the last one (apart from the time it was made) is skipped, and the status line says so. **Back up now** always saves a copy.
- **Keep the newest backups.** The default is 30; 0 keeps them all. Older backups are deleted, but **only files this extension saved itself**: nothing else in the folder is touched. A file you already moved or deleted is simply forgotten.
- **Back up now** saves one at once, whatever the schedule says.

The status line under the heading shows when the last backup was made, when the next one is due, and how many are kept. If your library is [encrypted](#logins-library) and locked when a backup is due, it **waits**: the backup is made as soon as you unlock. **Backup files are plain text, even when your library is encrypted** (only saved logins and locked notes stay encrypted inside them), so keep the backup folder somewhere safe. If the license ends or the downloads permission is taken away, backups pause and the status line says why.

<a id="backup-samples"></a>

### Starting from a sample library

While your library has no bookmarks at all, the empty screen (*All bookmarks*, or an empty workspace) has a **Start from a sample…** button next to **Add bookmark**. It opens a list of ready-made libraries for different kinds of work: developers, teachers, event planners, project managers, students, researchers and academics, designers, marketers, data analysts, IT admins and DevOps engineers, writers and content creators, freelancers and consultants, job seekers, journalists, small business owners and entrepreneurs, sales professionals, HR and recruiters, photographers and video creators, personal finance and home, and healthcare professionals. Each name is followed by the workspaces it would create.

Then choose what to add:

- **Workspaces, folders and the sample bookmarks** (the default) adds about 25 bookmarks with notes and a few tags, placed in their workspaces, so you can see how a library can look.
- **Just the workspaces and folders** adds the same workspaces and folders with no bookmarks in them, ready for your own. Every sample sorts a few of its workspaces into folders, each with its own icon.

Before you press **Add to my library** the dialog says how many workspaces, folders and bookmarks you will get. A sample is always *added* to your library, never a replacement, and nothing you already have is changed. Afterwards you can rename, delete or reorganise any of it like anything else you made. Samples contain no saved logins, and the same files are in the extension's `src/samples` folder if you would rather import one with **Import JSON…**.

<a id="backup-modes"></a>

### Merge or replace

**Merge** keeps everything you have. Bookmarks are matched by URL and workspaces by name (case-insensitive). Your existing notes and titles are never overwritten; tags are combined and missing workspace references are appended.

- **Exact duplicates are not imported.** A bookmark that matches one you already have in every aspect (the same page, title, note and tags) is ignored, and so is a workspace identical in every aspect. Importing a file you already imported, or your own export, changes nothing.
- Something that matches by URL or name but is **not identical** is merged without overwriting anything. If the file has tags, a note (where you had none), bookmarks or folders you do not have, they are added (*updated*). If it has nothing to add, yours is kept (*already in your library*).
- Folders in a matching workspace **merge by name**. Bookmarks that are new to that workspace take the file's places; bookmarks already in it keep the places they have.
- Importing into a bookmark you already have fills in a missing description.

**Replace** discards your current library (after a confirmation) and adopts the file, including its settings.

<a id="backup-report"></a>

### The import report

Afterwards a report lists, for bookmarks and for workspaces:

- how many were **imported as new**,
- how many **exact duplicates were ignored**,
- how many existing ones were **updated**,
- how many were **already in your library** with nothing to add,
- how many were **repeated inside the file** itself,
- and how many were **skipped as invalid** (such as an unsafe address).

It also lists the bookmark references and folders added and, for saved logins, how many were imported, already had one, or were skipped.

<a id="backup-safety"></a>

### What is checked before anything is imported

A file you import is treated as untrusted. The same checks apply to a file and to pasted text.

- **It is only ever read as data.** Nothing in it is run, evaluated or turned into markup. A title such as `<img onerror=…>` shows up literally.
- **It must be one of this extension's files**, and not from a newer, incompatible version. Anything else is refused with a message.
- **It must have the right structure.** If anything is wrong the whole file is refused and the message names the first problem, so a half-understood file is never partly imported.
- **Size limits:** at most 10 MB of text, 50,000 bookmarks and 500 workspaces. Titles, notes, names and tags are cut to their usual maximum lengths.
- **Addresses:** `javascript:`, `data:`, `vbscript:`, `blob:`, `filesystem:` and other script-capable or unknown schemes, unparseable addresses and addresses over 8,192 characters are skipped and counted. Accepted: `http`, `https`, `ftp`, `file`, `mailto`, `tel`, `about`, `chrome` and `brave`.
- **Ids cannot misbehave.** Any id that is not plain, or that is a name such as `__proto__`, is replaced with a fresh one.
- **Text is cleaned.** Control characters and invisible bidirectional-override characters are removed. Unknown settings and fields are ignored.
- **Encrypted logins** are accepted only if they have the exact expected shape, and can be opened only with the original passphrase.

<a id="backup-reset"></a>

### Starting over

Export a backup first, then remove and reload the extension, or import a file in **Replace** mode.

<a id="shortcuts"></a>

## Keyboard shortcuts and gestures

<a id="shortcuts-keys"></a>

### Keyboard

| Keys | What it does |
| --- | --- |
| <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>S</kbd> | Open the save pop-up for the current page (works from any page). |
| <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>M</kbd> | Open the manager. |
| <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>L</kbd> | Fill the saved login on the current page. |
| <kbd>/</kbd> | In the manager, jump to the search box. In this guide, jump to the guide search. |
| <kbd>Esc</kbd> | Clear the search box; close a dialog or menu. |
| <kbd>Ctrl</kbd>+<kbd>V</kbd> | In the manager, outside a text box: add the web address, or the QR code picture, on your clipboard. |
| <kbd>Enter</kbd> or <kbd>Space</kbd> on a workspace or folder row | Open it. |
| <kbd>Enter</kbd> or <kbd>,</kbd> in the tags field | Add the tag. |
| <kbd>Backspace</kbd> in an empty tags field | Remove the last tag. |

To change a shortcut, or if one does not work because another extension uses it, open your browser's shortcuts page (`chrome://extensions/shortcuts`, `edge://extensions/shortcuts` or `brave://extensions/shortcuts`).

<a id="shortcuts-mouse"></a>

### Mouse and touch

| Gesture | What it does |
| --- | --- |
| Click a card's title | Open the page. |
| <kbd>Ctrl</kbd>-click (or Cmd-click) a card's title | Open the page in a background tab. |
| Right-click a workspace or folder | Open its menu. |
| Right-click a workspace's title | Open the workspace menu. |
| Drag a card | Move, copy or reorder it. See [Drag and drop](#dnd). |
| Hold <kbd>Ctrl</kbd> or <kbd>Alt</kbd> while dropping | Copy instead of move, or also place in another folder. |
| Drag an address or link in | Save it. See [Drag an address in](#saving-drag). |

<a id="privacy"></a>

## Privacy and permissions

There is **no account, no analytics and no server**. Your bookmarks, notes and tags never leave your browser. Saved logins are encrypted on your device and never transmitted; they only leave the vault when *you* fill them into a matching page or choose to export them (still encrypted). Nothing is synced between devices.

The only network traffic the extension creates is the optional description lookup: a `GET` request to a bookmarked site (no cookies are sent) to read the page's description, and only if you grant site access; and, only when you press **Check for updates** in Settings, one request to GitHub asking for the newest release. Revoke the permission in **Settings → Site access** to stop even that.

<a id="permissions"></a>

### Permissions and why

| Permission | Why it is needed |
| --- | --- |
| `storage`, `unlimitedStorage` | Save your library on this computer, without a size cap, and keep a Pro license key in the browser's synced storage. |
| `tabs` | Read the current tab's address and title for the pop-up, and open bookmarks in tabs. |
| `contextMenus` | The right-click **Save to Bookmark Bastion** menu. |
| `alarms` | The vault's auto-lock, and clearing a copied secret from the clipboard after a delay. |
| `idle` | Learn that the computer's screen has locked, so saved logins lock with it. Nothing about your activity is read or kept. |
| `favicon` | Show site icons using the browser's own favicon cache. |
| `activeTab`, `scripting` | One-click autofill: when you click the toolbar button or press <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>L</kbd>, the extension may fill the login form on **that tab only**, for that moment. |
| `offscreen`, `clipboardWrite` | Wipe a copied secret from the clipboard after the delay in Settings, and hand an [automatic backup](#backup-auto) to the browser to save, through a hidden helper page. Nothing is read, sent or kept. |
| `downloads`, `downloads.ui` *(optional)* | Only while [automatic backups](#backup-auto) are on: save the backup files into your download folder (`downloads`) and keep the browser's download bubble quiet while it does (`downloads.ui`). The browser asks first, and both are given back when you turn backups off. Your existing downloads are never read or listed: only the files this extension saved itself are ever removed. |
| All sites *(optional)* | Only if you grant it: reading the pages of your bookmarks for their descriptions, and answering browser sign-in prompts if you turn those on. |
| `webRequest`, `webRequestAuthProvider` *(optional)* | Only if you turn on **Browser sign-in prompts**. |
| `history` *(optional)* | Only while you import pages from your browser history (**Settings → Backup & transfer**). The browser asks first, your history is only read and never changed, and the permission is given back when the dialog closes. |
| `bookmarks` *(optional)* | Only while you import your browser's bookmarks (once after installing, or from **Settings**). The browser asks first, the bookmarks are only read, and the permission is given back when the dialog closes. |
| `clipboardRead` *(optional)* | Only if you grant it, the first time you click **Paste URL**. It is never read in the background. |

<a id="data"></a>

### Where your data lives

Everything is in the browser's extension storage on your computer. Your library, the record of which pages were already asked for a description, and the encrypted vault are kept separately, so background work can never overwrite something you edited. The unlock key lives only in memory while the vault is unlocked. The storage format is versioned and upgraded automatically when needed.

<a id="troubleshooting"></a>

## Troubleshooting

<a id="ts-shortcut"></a>

### A keyboard shortcut does not work

Another extension may own it. Review shortcuts at `chrome://extensions/shortcuts` (or `edge://…` / `brave://…` in those browsers).

<a id="ts-internal"></a>

### A `chrome://`, `brave://` or `file://` bookmark will not open when clicked

The browser may block some internal pages for extensions. Copy the address into the address bar instead.

<a id="ts-forgot"></a>

### I forgot my saved-logins passphrase

There is no recovery, by design: the passphrase is the only way to decrypt them. Use **Settings → Saved logins → Delete all saved logins…** to clear the vault, then set up a new passphrase. Your bookmarks are unaffected. An export made *with* logins still needs the passphrase it was made with.

<a id="ts-nofill"></a>

### “Fill login” does not appear in the pop-up

It only appears when a bookmark with a saved login has the **exact same origin** as the current page (same `https://`, host and port). Edit the bookmark's URL if the site uses a different address for its sign-in page, or save another bookmark for it.

<a id="ts-notfilled"></a>

### The login was not filled

Some sites build their form late or inside unusual widgets. Open the sign-in form first, then click the toolbar button again. On pages that are not HTTPS, filling is intentionally blocked. You can always use the copy buttons in the bookmark's Edit dialog, or the key button on its card.

<a id="ts-fillkey"></a>

### The shortcut for filling did nothing

If the vault is locked, the shortcut shows a **LOCK** badge (and opens the pop-up where the browser supports it). Unlock it from the pop-up or the manager first.

<a id="ts-code"></a>

### A code is rejected by the site

Check that your computer's clock is right; time-based codes depend on it. Compare the code in the form with the one the site expects, and check the key type, digits and period if you typed an `otpauth://` link by hand.

<a id="ts-httpauth"></a>

### The browser sign-in pop-up still appears

Check that **Browser sign-in prompts** is **On** in Settings, that the bookmark has **Answer the browser’s sign-in pop-up on this site** ticked, that the address is https (or localhost) and matches the bookmark's origin, and that the vault is unlocked. The browser's pop-up also appears when the server refused the login once.

<a id="ts-sync"></a>

### My changes do not show up

The manager updates by itself. If a window looks out of date, reload it. If you have a packed and an unpacked copy of the extension, remember they are separate and do not share data.

<a id="ts-reset"></a>

### I want to start over

See [Starting over](#backup-reset).

<a id="about"></a>

## About

**Bookmark Bastion** was created by **DoggByte**: [doggbyte.com](https://doggbyte.com). Released under the MIT licence. Folder icons are Tabler Icons (MIT). QR pictures are read with jsQR (Apache-2.0), and QR codes are drawn with qrcode-generator (MIT), both included unmodified.

The version you are running is shown at the bottom of **Settings**.
