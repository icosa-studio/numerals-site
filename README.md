# numerals.io

Static site served by GitHub Pages at **https://numerals.io** (`CNAME`). No build step: what is in `main` is what ships.

| Path | What |
|---|---|
| `/` | Redirects to Discbreaker's Steam page (`index.html`, until the site has a homepage) |
| `/discbreaker/press` | Discbreaker press kit: trailer, downloads, fact sheet, images |
| anything else | `404.html`, the same redirect to Steam |

## Updating the press kit

`discbreaker/press/` is generated, never edited by hand. Its source is in the Discbreaker repo
(`marketing/press_kit/`: `press_kit.json` copy, `press_kit.css` + `web.css` look, `press_kit.py` build):

```bash
# from the Discbreaker repo root
python3 -I marketing/press_kit/press_kit.py --preview --web ~/Projects/numerals-site/discbreaker/press
cd ~/Projects/numerals-site && git add -A && git commit -m "Press kit: <what changed>" && git push
```

Pages redeploys within a minute of the push.

## DNS (GoDaddy, ns51/52.domaincontrol.com)

- `@` A: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
- `www` CNAME: icosa-studio.github.io
- MX (Google Workspace) and the rest: untouched
