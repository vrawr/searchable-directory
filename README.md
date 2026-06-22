# Searchable Directory

A self-contained, embeddable directory widget. One HTML file, no server, no build step, no dependencies. Type to search in real time, filter by two dimensions, and copy a field with one click. It works on mobile and desktop and drops straight into Google Sites, Notion, an iframe, or GitHub Pages.

The live demo is **The Modern Work Stack** — 50 software tools professionals use, filterable by category and pricing. Swap one array and it becomes any directory you want: a vendor list, a team roster, a resource library, an FAQ, a tool catalog.

## Try it

Open `index.html` in any browser. That's the whole setup.

## Make it your own

Everything you'd change lives at the top of the `<script>` block in `index.html`.

**1. Edit `CONFIG`** for the title, subtitle, and labels:

```js
var CONFIG = {
  title:    "The Modern Work Stack",
  subtitle: "50 software tools professionals actually use…",
  filter1All: "All categories",   // the "show everything" option for filter 1
  filter2All: "All pricing",      // the "show everything" option for filter 2
  linkLabel: "Site",
  noteLabel: "Best for",
  tagOrder: ["Free","Freemium","Paid"]  // optional ordering for filter 2
};
```

**2. Replace `DATA`** with your own records. Each card is one object:

```js
{
  title:    "Name shown in bold",        // required
  category: "Primary group",             // feeds filter 1
  tag:      "Secondary group",           // feeds filter 2 (price, region, status…)
  desc:     "One-line description",       // under the title
  link:     "example.com",                // no https:// needed
  note:     "Highlighted line at bottom"  // the callout
}
```

All fields except `title` are optional — leave one blank and that part of the card simply doesn't render. The two dropdowns populate themselves from whatever `category` and `tag` values you use, so you never touch the filter code.

## Coming from a spreadsheet

If your data lives in a CSV or sheet, you don't have to retype it. Each row becomes one object using the column-to-field mapping above. Ask your tool of choice (or paste the CSV into a chat) to convert it into the `DATA` array, then drop it in.

## Embedding

- **Google Sites:** Insert → Embed → Embed code, and paste the contents of `index.html`.
- **Anywhere with an iframe:** host the file (GitHub Pages works well) and point an `<iframe>` at it.
- **Notion:** host it, then paste the URL and choose "Embed."

## Why it's built this way

No backend means nothing to maintain, nothing to break, and no data leaves the file. That's the tradeoff: edits happen in the file, not a live database. For a directory that changes a few times a month, that's a feature, not a limitation.

## License

MIT — use it, fork it, ship it.
