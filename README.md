# Manga Splitter

Turn a folder of manga page images into neatly split chapters or a single volume, as **CBZ** or **EPUB** files, with metadata and covers added automatically.

![Windows](https://img.shields.io/badge/Windows-10%20%7C%2011-blue)

## Download

1. Open the **[latest release](https://github.com/9Bit3/MangaSplitter/releases/latest)**.
2. Under **Assets**, download **`MangaSplitter-Setup.exe`**.
   (Ignore the "Source code (zip)" and "Source code (tar.gz)" links - GitHub adds them to every release and they do not contain the app.)
3. Run the installer and follow the steps.

The installer puts Manga Splitter in your user folder (`%LocalAppData%\Programs\Manga Splitter`), so **no administrator rights are needed**. It adds a Start menu shortcut and can add a desktop shortcut.

### Windows warning ("Windows protected your PC")

The installer is not code-signed yet, so Windows SmartScreen may warn you the first time. Click **More info**, then **Run anyway**. If Windows 11's *Smart App Control* blocks it, you can turn that off temporarily under Windows Security > App & browser control.

## Requirements

- Windows 10 or 11 (64-bit)
- **[Tesseract OCR](https://github.com/UB-Mannheim/tesseract/wiki)** - needed only for automatic chapter detection ("Divide by Chapter"). Install the Windows build and, during setup, tick the extra languages you need (for example Japanese and Japanese vertical for raw manga). The default install location is detected automatically.
- An internet connection - only for the automatic metadata lookup and update checks.

Exporting a volume, or exporting chapters you marked by hand, works without Tesseract.

## Quick start

1. Open Manga Splitter and click **New session**.
2. Choose the folder with your page images (jpg, png, webp, gif or bmp - named so they sort in reading order), then give the session a name.
3. Your pages appear as thumbnails. Manga Splitter looks up the series online and fills in the metadata.
4. Pick what you want:
   - **Divide by Chapter** - scans the pages and finds where each chapter begins. (currently not perfect so review the results before exporting)
   - **Export Chapters** - exports using the chapter markers as they are now (no scan).
   - **Export as Volume** - exports everything as one file.
5. Choose **CBZ** or **EPUB** in the options row first. Tick **Right-to-left** for manga reading order.
6. Your session is saved automatically, so you can come back to it later from the main menu.

## Finding chapters

Automatic detection combines several clues: chapter title pages, "Chapter 12" style labels (including small ones in headers or footers), the chapter numbers counting upward in order, and page layout. Boxes show what it found:

| Box Color | Meaning |
|---|---|
| Blue | Chapter start |
| Teal | Bonus chapter (3.1, 3.5, ...) |
| Purple | Front thumbnail or Extras |
| Dashed amber with `?` | A ocr guess - please check it |

If you know how many chapters the volume has, set the **Chapters** box before scanning; it makes detection much more accurate. Pages before the first chapter title are treated as the **front thumbnail** (a setting lets you count them as part of chapter 1 instead). Pages after the last chapter that look like an afterword or bonus pages can become an **Extras** section.

### Fixing markers by hand

| Shortcut | Action |
|---|---|
| Double-click a page, or select it and press **Enter** | Mark or unmark a chapter start |
| **B** | Make the page a bonus chapter with a number like 3.1, 3.2 or 3.5 |
| **X** | Turn a marker into an Extras section |
| **Right-click** a page | More options |
| Double-click **page 1** | Front thumbnail on/off |

## Exported files

- Chapters are named like `Series - Ch001.cbz`, bonus chapters `Series - Ch003.5.cbz`, plus `Front thumbnail` and `Extras` files when present.
- **Metadata** (title, author, artist, genres, summary, year, volume, cover, link) is saved in the session and written into the exported files - `ComicInfo.xml` for CBZ, and standard book metadata with series information for EPUB. Use the **Metadata** page in a session to search again or edit anything by hand.

## Settings

Open **Settings** from the main menu or inside a session: session and export folders, default format and OCR language, metadata options, front thumbnail behavior, light or dark theme, UI scale, and update checks.

## Updating

Manga Splitter checks for new versions when it starts. When one is available, an **Update available** button appears in the main menu - click it and the app downloads the new installer, installs it and reopens. You can also check any time under **Settings > Updates**, or just download the newest `MangaSplitter-Setup.exe` from the releases page and run it over your existing install.

## Uninstalling

Open Windows **Settings > Apps > Installed apps**, find **Manga Splitter** and choose Uninstall. Your sessions and settings are kept in `%AppData%\MangaSplitter` so they survive a reinstall; delete that folder if you want them gone too.

## Help and community

Questions, bugs or ideas? Join the community Discord for app support: **[discord.gg/M6Rd9KngTZ](https://discord.gg/M6Rd9KngTZ)**

---

Made by **9Bit3**
