# Vastu Notes — Landing Page Setup

## 1. Add your payment link
Open `index.html`, scroll near the bottom to the `<script>` section, and edit:

```js
const PAYMENT_LINK  = "PASTE_PAYMENT_LINK_HERE";
```

Replace with your real payment link. Every "Buy Now / अभी खरीदें" button (hero, offer section, sticky mobile bar, final CTA) uses this one variable — no need to edit them individually.

## 2. Change the countdown expiry date
Same `<script>` section:

```js
const OFFER_END_DATE = "2026-09-30T23:59:59+05:30";
```

Change the date/time (format: `YYYY-MM-DDTHH:MM:SS+05:30` for IST). The timer recalculates from this fixed date on every page load, so it won't reset when visitors refresh.

## 3. Add your images
Place these files inside `assets/images/`:

| File | Used for |
|---|---|
| `book-cover.jpg` | Hero book cover showcase |
| `vastu-table.png` | *(optional — currently a CSS-built golden table is used instead; only needed if you want to swap to a real image)* |
| `rashi-wheel.png` | *(optional — the wheel is built with CSS/HTML so it animates without an image)* |
| `preview-1.jpg` | Book preview gallery, image 1 |
| `preview-2.jpg` | Book preview gallery, image 2 |
| `preview-3.jpg` | Book preview gallery, image 3 |

Until you add a file, that spot shows a clean gold-bordered placeholder with the expected filename — the layout never breaks.

## 4. Add your demo PDF
Place your file at:

```
assets/pdf/demo.pdf
```

Every "Demo PDF" button opens this file in a new tab automatically.

## 5. File structure
```
index.html
assets/
  images/
    book-cover.jpg
    vastu-table.png
    rashi-wheel.png
    preview-1.jpg
    preview-2.jpg
    preview-3.jpg
  pdf/
    demo.pdf
```

Just drop matching files into these folders — no HTML/CSS edits needed.

## 6. Editable copy
Section 10 (FAQ) has one answer marked "(Editable: ...)" for the post-payment delivery process — update it once you know your exact delivery flow (email, WhatsApp, Google Drive link, etc.).

## 7. Testing locally
Since the page uses relative asset paths, open it through a local server rather than double-clicking the file (some browsers block relative file loads under `file://`). Easiest options:
- VS Code "Live Server" extension, or
- `python3 -m http.server` from this folder, then visit `http://localhost:8000`
