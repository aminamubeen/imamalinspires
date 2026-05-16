# Imam Ali Quotes Website

A beautiful, static mood-based quote browser featuring sayings from Imam Ali AS (Nahj al-Balagha).

---

## Features

- **Mood-based browsing** — find a quote that matches how you feel
- **Category filtering** — browse by topic (patience, wisdom, leadership, etc.)
- **Search** — quickly find quotes by keyword
- **Responsive design** — works on mobile, tablet, and desktop
- **No backend required** — pure HTML, CSS, and JavaScript

---

## File Structure

```
website/
├── index.html       # homepage with mood cards
├── all_quotes.html  # searchable quote archive
├── about.html       # about Imam Ali and Nahj al-Balagha
├── style.css        # all styling
├── quotes.json      # quote dataset (single source of truth)
└── README.md        # this file
```

---

## How to Use

### View the Website

Just open `index.html` in a browser. There's no build step or server needed.

```bash
# macOS
open index.html

# Linux
xdg-open index.html

# Or just drag the file into your browser
```

### Host Online

To share with others, deploy to any static host:

- **GitHub Pages** — push this folder to a repo, enable Pages in settings
- **Netlify** — connect your repo, auto-deploys on push
- **Vercel** — similar to Netlify, very fast
- **Any web server** — just copy the files to your hosting

---

## Customization

### Change Quote Data

Edit `quotes.json`. Each quote must have:

```json
{
  "text": "The quote text",
  "saying_ref": "Sermon 45",
  "category": "patience",
  "used": false
}
```

**Fields:**
- `text` (required) — the quote
- `saying_ref` — where it's from (e.g., sermon number, letter)
- `category` — topic for filtering (lowercase, e.g., "patience", "wisdom", "leadership")
- `used` — set to `true` to hide it (keeps it in the dataset but removes from display)

### Change Colors & Fonts

Open `style.css` and update the CSS variables at the top:

```css
:root {
  --serif: "Georgia", serif;           /* quote text font */
  --sans: "Segoe UI", sans-serif;      /* headings & UI */
  --ink: #2c2c2c;                      /* text color */
  --paper: #f5f3f0;                    /* background */
  --accent: #d4a574;                   /* highlights */
  /* ... more colors ... */
}
```

### Change the Mood Cards

Edit the mood cards section in `index.html`. Each card links to `all_quotes.html?category=categoryname`.

```html
<article class="mood-card" onclick="window.location='all_quotes.html?category=patience'">
  <h3>Seeking Calm</h3>
  <p>Quotes about patience, peace & acceptance</p>
</article>
```

### Add New Pages

Create a new `.html` file and follow the same structure as `index.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Your Page Title</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <!-- Your content here -->
  <script src="quotes.json"></script>  <!-- if you need quote data -->
</body>
</html>
```

---

## Structure & Navigation

### index.html
The landing page with mood-based cards. Each card filters quotes by category.

### all_quotes.html
The quote archive with:
- Full searchable quote list
- Category filtering via chips
- Keyword search
- Quote count & empty state

### about.html
Information about Imam Ali and the Nahj al-Balagha collection.

---

## Browser Support

Works on all modern browsers:
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

---

## Tips

- **Search performance** — quotes are filtered in-browser (fast)
- **SEO** — static HTML means good search engine indexing
- **Analytics** — add Google Analytics or Plausible if desired
- **Offline** — works fully offline once loaded
- **Share** — direct links work: `index.html?category=wisdom`

---

## Adding More Quotes

1. Edit `quotes.json` and add new quote objects
2. Refresh your browser — changes load instantly
3. No rebuild needed

---

## License & Attribution

All quotes are from **Nahj al-Balagha** (The Peak of Eloquence), sayings of Imam Ali ibn Abi Talib.

---

## Questions?

Check the quote dataset format in `quotes.json` or review the HTML/CSS for customization examples.
