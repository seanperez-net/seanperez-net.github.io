# seanperez-net.github.io

GitHub Pages user site: https://seanperez-net.github.io

Two files, `index.html` and `style.css`, served straight from the `main` branch. No build step,
no framework, no dependencies. `.nojekyll` tells GitHub Pages to skip Jekyll and serve the files as is.

## What is in the `<head>`

`index.html` is commented section by section: search (title, description, canonical, robots),
loading hints (`preconnect`, `dns-prefetch`, `preload`), link previews (Open Graph, X card),
icons and the web manifest, schema.org structured data, and speculation rules. The last two are
`<script>` data blocks the browser reads but never runs: the page still has no JavaScript.

Also here: `robots.txt`, `sitemap.xml`, `404.html` (GitHub Pages serves it for missing addresses).

## Images

| File                   | Size       | Used for                        | Made from                 |
| ---------------------- | ---------- | ------------------------------- | ------------------------- |
| `og-image.png`         | 1200 x 630 | Link previews                   | `og-image.svg`            |
| `favicon.svg`          | any        | Browser tab (light and dark)    | written by hand           |
| `apple-touch-icon.png` | 180 x 180  | iOS home screen                 | `icon-512.png`, resized   |
| `icon-192.png`, `icon-512.png` | 192, 512 | Web manifest (Android)    | a square of the same mark |

Social sites do not accept SVG, so `og-image.svg` is rendered to PNG with headless Chrome:

```sh
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless=new \
  --hide-scrollbars --force-device-scale-factor=1 --window-size=1200,630 \
  --screenshot="$PWD/og-image.png" "file://$PWD/og-image.svg"
```

Change the title or the colours in the SVG, run it again, and commit both files.
