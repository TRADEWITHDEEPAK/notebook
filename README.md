# My Notebook

A free, OneNote-style notebook that runs in your browser and is hosted on GitHub Pages.
Notebooks, sections and pages; rich text, to-do checkboxes, tables, images, drawings, search,
optional password lock, and sync across devices through a private GitHub repo.

## Repo layout

```
notebook/                 <- public repo, served by GitHub Pages
├── index.html            the whole app (HTML + CSS + JS)
├── manifest.webmanifest  lets you "Add to Home Screen"
├── .nojekyll             tells GitHub Pages to serve files as-is
├── assets/
│   └── icon.svg          app icon
└── docs/
    └── data-repo-README.md   copy this into your private data repo
```

Your notes are NOT stored in this repo. They live in a second, private repo (`my-notes-data`) as `notes.json`.

## Setup (about 10 minutes)

1. Create a **public** repo named `notebook` and upload everything in this folder.
2. Settings → Pages → Source: *Deploy from a branch* → `main` / `(root)` → Save.
   Your app appears at `https://YOUR-NAME.github.io/notebook/`.
3. Create a **private** repo named `my-notes-data` (add a README so it is not empty).
4. Create a token: Settings → Developer settings → Personal access tokens → Fine-grained tokens.
   Repository access: only `my-notes-data`. Permissions → Contents: **Read and write**.
5. Open your site → **Sync** → enter `YOUR-NAME/my-notes-data` and the token → Save & sync.
   Repeat on each device.

## Features

- Navy and gold, four-column layout: Notebooks, Sections, Tabs, and the selected tab's content
- Search across a notebook
- Bold, italic, underline, strikethrough, headings, lists, to-dos, highlight
- Tables (insert, add row, add column, delete)
- Images (upload or paste; auto-resized; double-click an image to remove it)
- Drawing pad (pen, eraser, colors, touch and stylus)
- Password lock: notes are encrypted with AES-256 before saving and syncing
- Works offline once loaded; syncs when you reopen it online

## Good to know

- **Forgotten password = lost notes.** There is no reset. Keep a backup of your password.
- Images are shrunk to about 1000 px, but many photos make `notes.json` large and sync slower.
  Your browser keeps roughly 5 MB per site locally.
- If two devices edit at the same moment, the most recent save wins. Wait for "Synced ✓".
- Revert mistakes from the commit history of `my-notes-data`.
- Never commit your token anywhere.
