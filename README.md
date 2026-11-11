# austin-miller-reporting

GOAL reporting for **Austin J. Miller Insurance**, deployed as a static site on Vercel.

## Contents

| Path | Page |
| --- | --- |
| `index.html` | Report hub (links to every report) |
| `reports/oh-auto-campaign-configuration.html` | OH Auto Campaign Configuration |
| `reports/oh-home-campaign-configuration.html` | OH Home Campaign Configuration |

Homepage: generated hub (--index hub). Each report is a single self-contained HTML file. The only
external request is the Inter webfont from Google Fonts. There is no build step and
there are no dependencies.

## Deploying on Vercel

`vercel.json` serves the repo root as a static site (`framework: null`,
`outputDirectory: "."`, `cleanUrls: true`), so `/reports/<name>` works without the
`.html` extension. The Vercel project is connected to this repo: every push to `main`
publishes to production, and every other branch or PR gets its own preview URL.

Search engines are blocked with an `X-Robots-Tag: noindex` header and `robots.txt`
because these are client reports.

## Adding another report

Put the new HTML file in `reports/` with a lowercase, hyphenated name, add a link
to it from `index.html`, then commit and push.

## Previewing locally

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```
