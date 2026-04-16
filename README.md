# testleft-tools

Standalone SDET tools built for [testleft.co.uk](https://testleft.co.uk).

Each tool is a single self-contained HTML file — no framework, no build step, no dependencies.
All tools run 100% client-side. No data is ever sent to a server.

---

## Tools

| Tool | File | Status | URL |
|------|------|--------|-----|
| JSONPath Explorer | `tools/json-tool.html` | ✅ Live | [testleft.co.uk/tools/json-tool.html](https://testleft.co.uk/tools/json-tool.html) |
| JSON Diff | `tools/json-diff.html` | 🚧 Coming soon | [testleft.co.uk/tools/json-diff.html](https://testleft.co.uk/tools/json-diff.html) |

---

## Stack

- Vanilla HTML / CSS / JavaScript
- No framework, no npm, no build step
- Fonts: Inter + JetBrains Mono (Google Fonts)
- Each tool is a single `.html` file

## Design tokens

| Token | Value | Usage |
|-------|-------|-------|
| Background | `#f0f1f2` | Page background |
| White | `#ffffff` | Cards |
| Teal | `#00b4b4` | Accent, buttons, highlights |
| Navy | `#1a2a3a` | Headings, nav |
| Text muted | `#6b7280` | Subtitles, labels |

---

## Deployment

Pushing to `master` automatically deploys all files in `tools/` to `testleft.co.uk/tools/`
via the GitHub Actions workflow in `.github/workflows/deploy.yml`.

### Setup

1. Go to **Settings → Secrets and variables → Actions** in this repo
2. Add the following secrets:

| Secret | Value |
|--------|-------|
| `FTP_USER` | Your Krystal FTP username (found in cPanel → FTP Accounts) |
| `FTP_PASS` | Your Krystal FTP password |

### How it works

- Only triggers when files inside `tools/` change
- Deploys only changed files (not the whole repo)
- Excludes `.git`, `.github`, `.idea` and `README.md`

---

## Adding a new tool

1. Create `tools/your-tool-name.html`
2. Follow the existing design pattern (nav, page header, security badge, card, footer)
3. Push to `master` — GitHub Actions deploys it automatically
4. Add a row to the table above

---

## Local development

Open any `.html` file directly in your browser — no server needed.

In IntelliJ: right-click the file → **Open In → Browser**.
