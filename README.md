# Web Scanner website

Source of [webscanner.onderbakir.com](https://webscanner.onderbakir.com): the website, guide, privacy policy, terms and support link for Web Scanner, a Chrome extension that finds broken links and checks a site's security basics.

The extension's own source code is not in this repository. Web Scanner 1.3 is not on the Chrome Web Store yet; the site says "Coming soon".

![Web Scanner security tab: grade C for www.example.com, findings sorted into "Fix these first" and "Then", with evidence for the selected finding](img/grade.webp)

## Web Scanner in short

- **Free:** link scans of up to 150 URLs each, every broken link with its page and link text, redirect chains, a security grade and the full issue list. Fixes are not included, apart from one sample finding from a demo scan.
- **Pro Lifetime:** a one-time payment of $9.99 through Lemon Squeezy. No URL limit, the evidence and fix for every finding (fix code for Nginx, Apache, Cloudflare, Next.js, Vite, Express and PHP), scan history with rescan comparison, client reports, CSV and JSON export. One license works in up to 5 browsers.
- Runs in Chrome 116 or newer. Scans run in the browser; there is no account, analytics or ads in the extension.

## Pages

| File | Live path | What it is |
| --- | --- | --- |
| `index.html` | `/` | Product page: how it works, pricing, privacy summary, FAQ |
| `guide.html` | `/guide` | User guide for 1.3: first scan, broken links, security grade, fixes and reports, license, troubleshooting |
| `changelog.html` | `/changelog` | Release notes for 1.2.0 and 1.3.0 |
| `privacy.html` | `/privacy` | Privacy policy of the extension and the website |
| `terms.html` | `/terms` | Terms of use, Free and Pro, refunds |
| `404.html` | any unknown path | Not-found page |

Other files: `style.css` (shared stylesheet), `icon.png`, `og.png` (social preview image), `img/` (screenshots on the home page) and `demo.mp4` (product demo video).

## Run locally

There is no build step. The site is plain HTML and CSS, so any static server works:

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000. Locally, pages keep their `.html` extension (for example `/guide.html`), and unknown paths do not show `404.html`; both are handled by Cloudflare Pages.

## Deploy

The site is hosted on Cloudflare Pages, connected to this repository. A push to `main` deploys to production at webscanner.onderbakir.com. There is no build command; the repository root is served as is. Pushes to other branches get preview deployments.

When you change `style.css`, raise the `?v=` value in the stylesheet link of every page, so browsers that cached the old file fetch the new one.

## Report a bug

Open an issue at [github.com/onder007/web-scanner/issues](https://github.com/onder007/web-scanner/issues), for the website or the extension. Questions about a Pro purchase or a refund: reply to your Lemon Squeezy receipt email.
