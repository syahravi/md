# Markdown editor

A distraction-free Markdown editor with LaTeX math and instant preview, in the browser. Live at https://md.syahravi.id.

- Write on the left, see the result on the right: no delay while typing, no flickering when math is on the page.
- Landing page = working page: the first page you open is the editor, with no welcome screen or login.
- Your text stays in the browser (localStorage). Nothing is uploaded. The only third-party request is MathJax from cdnjs.
- Save as `.md`, open a `.md` file (or drop one on the page), print or save as PDF.
- Light by default, with a dark mode toggle. The preview can use Computer Modern for a LaTeX look.

## Shortcuts

| Keys | Action |
|---|---|
| Ctrl + D | Switch view: split, preview only, editor only |
| Ctrl + P | Print or save as PDF |
| Ctrl + S | Save the source as a .md file |
| Ctrl + Shift + O | Open a .md file |
| Ctrl + Shift + L | LaTeX on or off |
| Ctrl + Shift + D | Dark mode on or off |
| Ctrl + Shift + R | Serif (Computer Modern) or sans-serif preview |
| Ctrl + Shift + H | Help |

All of these are also buttons in the header. `\pagebreak` in the text starts a new page when printing.

## Development

No build step. Open `index.html`, or serve the folder:

```
npx wrangler dev
```

Deploy is Cloudflare Workers static assets (`wrangler.jsonc`, custom domain `md.syahravi.id`). Files that are not part of the site are listed in `.assetsignore`.

## Brand

`tokens.css` is copied from the syahravi.id repo without the "Trusted Partner" block. Change tokens there, then copy again. `styles.css` only uses those tokens. Fonts (Bricolage Grotesque, Hanken Grotesk, IBM Plex Mono) are self-hosted in `fonts/`. `scripts/og-image.html` renders `og-image.png`; the render command is in the file.

## Credits

Uses [Pagedown](https://code.google.com/archive/p/pagedown/), [Pagedown Extra](https://github.com/jmcmanus/pagedown-extra), [MathJax](https://www.mathjax.org/), [jQuery](https://jquery.com/), StackOverflow's [editor code](https://gist.github.com/gdalgas/a652bce3a173ddc59f66), and the [Computer Modern](http://cm-unicode.sourceforge.net/) font.

Some of these libraries have been slightly modified (a few lines of code) to make them work together, which is why they are included in this repo.
