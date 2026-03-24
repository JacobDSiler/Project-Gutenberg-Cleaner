# Gutenberg Text Cleaner

A browser-based tool for fetching, cleaning, and splitting Project Gutenberg books into individual chapters — ready for republishing.

## Features

- **Fetch directly** from any Project Gutenberg URL (works on GitHub Pages)
- **Paste fallback** for running locally or when fetch is blocked
- **Auto-detects chapters** — Chapter I, PART II, ACT III, Prologue, etc.
- **Preview** each chapter in a readable reader pane
- **Export individual chapters** as `.txt` or `.rtf` (rich text, with bold headings)
- **Export all chapters** at once
- Strips Gutenberg header, footer, license notices, and "Produced by" credits
- Dark mode support

## Setup on GitHub Pages (recommended)

Hosting on GitHub Pages gives you HTTPS, which allows the tool to fetch text files directly from gutenberg.org without any CORS issues.

1. [Create a new GitHub repository](https://github.com/new) — name it anything you like (e.g. `gutenberg-cleaner`)
2. Upload `index.html` to the repository root
3. Go to **Settings → Pages**
4. Under **Source**, select `Deploy from a branch`, choose `main`, folder `/root`
5. Click **Save** — your site will be live at `https://yourusername.github.io/gutenberg-cleaner/`

That's it. The tool will now fetch books directly from any Gutenberg URL you paste in.

## Running locally

Open `index.html` directly in your browser. The fetch feature will be blocked by browser CORS policy when running from a `file://` URL, but the **paste workflow** works perfectly:

1. Enter your book URL — the tool resolves it to the correct `.txt` file link
2. Click **"Open plain-text file"** to open the raw text in a new tab
3. Select all (Ctrl+A / Cmd+A), copy
4. Paste into the text area and click **Clean & Split Chapters**

## Supported URL formats

All of these work:

```
https://www.gutenberg.org/ebooks/84
https://www.gutenberg.org/cache/epub/84/
https://www.gutenberg.org/files/84/84-0.txt
84
```

## Chapter detection

The tool recognises headings like:

- `CHAPTER I` / `Chapter 1` / `Chapter One`
- `PART II` / `Part Two`
- `BOOK III`
- `ACT I` / `SCENE II`
- `PROLOGUE` / `EPILOGUE` / `INTRODUCTION` / `PREFACE`

Headings must appear on their own line, preceded and followed by blank lines (standard Gutenberg formatting).

## Export formats

| Format | Description |
|--------|-------------|
| `.txt` | Plain text with chapter title and a rule line |
| `.rtf` | Rich Text Format — opens in Word, LibreOffice, Pages, etc. Chapter heading is bold. Optional book title header. |

Files are named automatically: `01-chapter-i.txt`, `02-chapter-ii.rtf`, etc.

## Gutenberg redistribution

When republishing a cleaned Gutenberg text, you must:

1. Add your own new copyright notice or foreword
2. Not present it as the original Gutenberg edition
3. Follow the [Project Gutenberg License](https://www.gutenberg.org/policy/license.html)

This tool handles the cleaning step. Adding your content is up to you.

## License

MIT — use freely, modify as needed.
