# HOFAC — The House of All Faiths & Communities

Static website for The House of All Faiths & Communities, a Scottish
Charitable Incorporated Organisation (charity number **SC055598**).

## Structure

Single-file static site. `index.html` contains the markup, inline CSS and a
small hash router that serves five views from the one document:

| Route       | View        |
| ----------- | ----------- |
| `#/`        | Home        |
| `#/about`   | About       |
| `#/charter` | The Charter |
| `#/contact` | Contact     |
| `#/privacy` | Privacy     |

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

Cloudflare Pages, free tier. No build step — the repository root is published
as-is.
