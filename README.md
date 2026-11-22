# HOFAC — The House of All Faiths & Communities

Static website for The House of All Faiths & Communities, a Scottish
Charitable Incorporated Organisation (charity number **SC055598**).

## Structure

Single-file static site. `index.html` contains the markup, inline CSS and a
small hash router that serves twelve views from the one document:

| Route           | View                |
| --------------- | ------------------- |
| `#/`            | Home                |
| `#/house`       | The House, overview |
| `#/about`       | About               |
| `#/executive`   | Executive Committee |
| `#/trustees`    | Trustees            |
| `#/advisors`    | Advisors            |
| `#/ambassadors` | Peace Ambassadors   |
| `#/founder`     | Founder             |
| `#/declaration` | The Declaration     |
| `#/apply`       | Apply to join       |
| `#/contact`     | Contact             |
| `#/privacy`     | Privacy             |

An unknown route falls back to Home. To add a view, add a `<main id="...">`
block and put the same id in the `pages` array at the foot of `index.html`.

Images, logos and the Declaration PDF live in `assets/`.

### Third-party services

- **Google Fonts** serves the typeface.
- **Tally** hosts the membership application form embedded on the Apply view.
- The contact form sends nothing itself: it opens the visitor's own email
  application with a message addressed to info@hofac.org.

These are described on the Privacy view; keep the two in step.

## Brand

| Colour | Hex       |
| ------ | --------- |
| Blue   | `#222D65` |
| Red    | `#CE202F` |
| Yellow | `#FFCE02` |

Typeface: Public Sans (Google Fonts).

### Logo usage

- Artwork must not be redrawn, recoloured, rotated or stretched.
- On blue backgrounds use only the white version.
- Below 32px use the small-use version.
- Keep roughly the height of the crown as clear space around every lockup.

## Deployment

Cloudflare Workers static assets, configured in `wrangler.jsonc`. There is no
build step: the repository root is uploaded as the site.

Because the root is the site, every file in it is public unless it is listed
in `.assetsignore`. That file keeps `.git`, this README and the Wrangler
config off the live site. Add any new non-public file to it.

## Local preview

Requires Node.js. From this directory:

```sh
npx wrangler dev
```

Then open http://localhost:8787. This serves the site exactly as Cloudflare
will, including the `.assetsignore` exclusions.
