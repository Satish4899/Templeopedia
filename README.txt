TEMPLE PILGRIM GUIDE - IMAGE FIXED BUILD

Open index.html in a browser.
Keep styles.css and the assets folder beside index.html.

Image architecture:
- Hero image is local: assets/hero-temple.png
- Collection/category cards use 24 distinct Wikimedia Commons image files via Special:FilePath URLs.
- Individual temple detail records intentionally have no image.
- All collection images have an onerror fallback so a broken remote image does not show a broken-image glyph.

The original temple database and application logic are preserved.
