# assets/

Everything in this folder is referenced by the site. Drop files in, keep the
filenames, and the pages update automatically — no code changes needed.

## Brand / logo files

All of these are derived from `logo-source.jpg` (your original artwork). They
are already wired into every page — you should not need to touch them.

| File | Where it appears |
| --- | --- |
| `logo-badge.svg` | Navbar mark on all 5 pages; also the browser tab icon |
| `logo-mark.svg` | Footer mark (bare gold emblem, no tile) |
| `logo-mark.png` | 600px gold emblem on transparent — for print or slides |
| `logo-lockup.png` | Full logo with wordmark and tagline |
| `favicon.ico` / `favicon-32.png` | Browser tab icon |
| `favicon-180.png` | Apple touch icon (iPhone/iPad home screen) |
| `og-image.png` | Preview picture when a link is shared on social media |
| `logo-source.jpg` | Your original file, kept for reference |

The vector versions (`.svg`) stay sharp at any size. The raster favicons use a
solid silhouette rather than the outline artwork, because the logo's thin
lines fill in and blur below about 48px — the silhouette still reads clearly
at 16px.

### If you ever change the logo

Replace `logo-source.jpg` and regenerate the derived files. Keep every
filename identical and nothing else needs updating.

## Files the site expects

| File | Where it appears | Recommended size |
| --- | --- | --- |
| `qris-code.png` | Donate page — Local Donations (QRIS) card | 976 × 976, square, white background |
| `img/hero-yogyakarta.jpg` | Home page — hero feature image | 1200 × 1500, portrait |
| `img/yogyakarta-2.jpg` | Home page — Yogyakarta campaign card | 1200 × 900, landscape |
| `img/manado-1.jpg` | Home page — Manado campaign card | 1200 × 900, landscape |
| `img/yogyakarta-1.jpg`, `img/yogyakarta-3.jpg` | Extra Yogyakarta shots, not currently placed | 1200 × 900 |
| `img/unassigned-learning-session.jpg` | Unused spare photo — see note below | — |

## Folders that are not part of the site

Two folders hold files kept on purpose but never loaded by any page:

- `_source/` — your original QRIS artwork, before cleanup. Reference copy only.
- `_unused/` — the old illustrated QRIS placeholder, superseded by the real code.

Neither is referenced by the HTML, so you can delete either folder safely once
you are sure you no longer want the originals. Keep the total size in mind if
you deploy the whole project directory as-is.

## Replacing the QRIS image

`assets/qris-code.png` is a **live, scannable QRIS code** for Open Pages. It is a
clean re-render of your original artwork: the red crop-marquee lines along its
left, right and bottom edges were removed, the modules were snapped to a perfect
53 × 53 grid, and a proper 4-module white quiet zone was added around the code.
It decodes to the same payload as your original, and was verified to still scan
at **96 px wide** — the site displays it at 250 px, so it has plenty of margin.

Your untouched original is kept at `_source/qris-artwork-original.png` (2.7 MB,
with the red lines still on it). It is not used by any page.

**If the QRIS code ever changes**, export the new one at any size with a white
background and save it over `assets/qris-code.png`, keeping the filename. A
square image with a white background crops cleanest. Do not crop tighter than a
few modules of white space around the code — scanners need that quiet zone.

## Adding or swapping campaign photos

Every image slot in the HTML is wrapped in a comment that reads
`<!-- REPLACE WITH YOUR PHOTO -->`. To use a real photo, replace the whole
placeholder block inside that comment with a normal `<img>`, for example:

```html
<!-- REPLACE WITH YOUR PHOTO: Tuban, SD Pusaka kit handover (recommended 1200x900). -->
<figure class="photo photo--4x3">
  <img src="assets/img/tuban-1.jpg" alt="Students at SD Pusaka holding their new stationery kits."
       width="1200" height="900" loading="lazy">
</figure>
```

Two columns in the home page gallery currently show illustrated placeholders
rather than photos, because no matching photo exists yet:

- **Surabaya — Jumat Berkah** (meal distribution)
- **Tuban — SD Pusaka** (stationery kits)

Add those photos when you have them: save the file here, then swap the
`<div class="ill-frame">` block for an `<img>` as shown above.

## About `img/unassigned-learning-session.jpg`

This is a genuine campaign photo (children at low tables holding red and pink
bags over worksheets), but it could not be matched to a specific campaign — no
banner identifies the location. It is kept here unused rather than published
with a guess attached. Once you confirm which visit it belongs to, drop it into
that campaign card using the pattern above.

## Photo guidance

- Keep files under ~400 KB each so pages stay fast on mobile data.
- Landscape shots crop best in the gallery cards (4:3).
- The home page hero uses a portrait crop (4:5), so pick a tall or vertical
  photo, or expect the top and bottom to be trimmed.
- Always write a real `alt` description — it is what screen readers announce
  and what shows if an image ever fails to load.
