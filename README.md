# XR & Creative Portfolio

Static portfolio site with a bento-grid layout. Content and image paths are driven by `index_content.json`.

## Run locally

From the project root:

```bash
python -m http.server 8080
```

Then open **http://localhost:8080** (or **http://localhost:8080/index.html**).

---

## Image assets: folders and files

All card images live under the **`index images/`** folder. Paths in `index_content.json` are relative to the site root and must match the real folder and file names exactly.

### Folder naming

- **Use PascalCase** for folder names so they work on both Windows and Linux (e.g. Vercel).
  - Good: `Mars`, `Chapel`, `InsectInventory`, `XRAir`, `bloomcity`
  - Avoid: `mars`, `chapel` (lowercase can break on Linux if the JSON uses different case)
- **Stick to one convention.** Current convention: **PascalCase** (e.g. `Mars`, `Chapel`).
- The folder name does not need to match the card title; it just has to match the path in `index_content.json`.

### File naming

- **Use unique, descriptive names** to avoid build/cache issues and 404s:
  - Prefer: `mars-vr-01.png`, `mars-vr-02.png`, `chapel-vr-01.png`, etc.
  - Or: `projectslug-01.png`, `projectslug-02.png` (same idea).
- **Avoid generic names** like `1.png`, `2.png` unless you’re sure no other project uses the same names in the same build.
- Use **lowercase + numbers + hyphens** for filenames; end with `.png` or `.jpg` (or another format you reference in the JSON).

### Where paths go

- In **`index_content.json`**, each card can have:
  - **`src`** – main image (e.g. tile thumbnail).
  - **`slides`** – array of `{ "src": "path/to/image.png", "caption": "..." }` for the project slideshow.
- Paths are relative to the site root, e.g.:
  - `index images/Mars/mars-vr-01.png`
  - `index images/Chapel/chapel-vr-01.png`
- **Spaces** in paths (e.g. `index images`) are fine; the site encodes them when loading images.

### Checklist when adding or changing images

1. Create a folder under `index images/` with a **PascalCase** name (e.g. `MyProject`).
2. Add image files with **unique names** (e.g. `myproject-01.png`, `myproject-02.png`).
3. In `index_content.json`, find the card by number and set:
   - **`src`** to the main/thumbnail image path.
   - **`slides`** to the list of slide image paths and captions.
4. Commit and push. On Vercel, folder and file names are **case-sensitive**; they must match the JSON exactly.

---

## Card reference (index.html)

| Card | Description |
|------|-------------|
| 1 | Hero left – "Hey, this is Tan" (social links, CV) |
| 2 | Hero right – "Selected experiments & installations" |
| 3 | Large flagship – "Mixed Reality App to Read Air Quality" |
| 4 | About |
| 5 | "Interactive Timeline with AR features" |
| 6 | "Insect library in VR/MR" |
| 7 | "Learn about Mars in VR" |
| 8 | "VR Chapel" |
| 9 | "Workshops and Lectures" |
| 10 | Wide tile – "An interactive archive for XR design patterns" |
| 11 | Contact & Info |
| 12 | "Process and Insights" |

Use these numbers to edit the right entry in `index_content.json` when updating copy or image paths for a card.
