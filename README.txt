TEMPLE PILGRIM GUIDE - IMAGE FIXED BUILD

Open index.html in a browser.
Keep styles.css and the assets folder beside index.html.

Image architecture:
- Hero image is local: hero-temple.png (loads instantly, works offline).
  On load, the page silently swaps in a sharper 2400px remote version from
  Wikimedia Commons for large/high-DPI screens; if that request fails
  (no internet, blocked domain) the local image stays and nothing breaks.
- Collection/category cards use 24 distinct Wikimedia Commons image files via
  Special:FilePath URLs. All of them show a soft shimmer placeholder while
  loading and fall back to the local hero image if a remote file 404s.
- Individual temple detail records now show their category's themed image
  in the expanded card banner (sourcing a unique photo per temple isn't
  possible at 1,200+ records, so each shows the image for its collection).
- All collection images have an onerror fallback so a broken remote image
  does not show a broken-image glyph.

Fixed in this update:
- The hero background was pointing at "assets/hero-temple.png", a folder
  that doesn't exist in this build, so the hero rendered as a plain dark
  gradient with no photo. It now points at the real file, hero-temple.png,
  sitting next to index.html.
- Two category thumbnails (Shakti Peethas, Navagraha Temples) referenced
  Wikimedia filenames that don't exist and were silently falling back to
  the (also broken) hero image. Both now point at verified files.

The original temple database and application logic are preserved.
