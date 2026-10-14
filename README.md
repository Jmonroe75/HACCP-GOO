# NR Appeal Review

A single-page tool for reviewing USDA-FSIS Noncompliance Records (FSIS Form 5400-4) and deciding whether an appeal is worth filing.

Upload an NR PDF (or paste its text), state the grounds you're considering, and add any facts the NR doesn't show. The tool returns:

- The record fields (record number, date, establishment, regulations, inspector, associated NRs)
- Each cited regulation, what it requires, and whether it's contestable
- A straight verdict on your proposed grounds
- Stronger grounds, each rated and with what it depends on
- Enforcement risks (linked NRs, NOIE exposure under 9 CFR 500.4)
- Clerical errors on the record
- A recommendation and a draft appeal letter with placeholders for your records
- A before-sending checklist

The analysis is done by Claude through the Anthropic API, using your own API key.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app: HTML, CSS and JavaScript in one file. No build step. |
| `README.md` | This file. |
| `.gitignore` | Keeps NR PDFs and local notes out of the repo. |

## Put it on GitHub

1. Create a new repository on github.com (for example `nr-appeal-review`).
2. Click **Add file → Upload files**, drag in `index.html`, `README.md` and `.gitignore`, and commit.
3. To host it as a web page: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, choose `main` and `/ (root)`, and save.
4. After a minute the page is live at `https://<your-username>.github.io/nr-appeal-review/`.

You can also skip hosting and just open `index.html` in a browser from your computer.

## API key

1. Create a key at [console.anthropic.com](https://console.anthropic.com) (API usage is billed separately from a Claude.ai subscription).
2. In the app, open **API settings**, paste the key, and pick a model.
3. Tick **Remember key on this device** only on a computer you trust. The key is stored in that browser's local storage and sent only to `api.anthropic.com`.

**Never put your API key in any file in this repository.** Each person who uses the hosted page enters their own key.

## Privacy

- The NR you upload goes from your browser directly to the Anthropic API. GitHub only serves the page; it never sees your NRs or your key.
- Past reviews are saved in your browser's local storage only.
- Don't commit real NRs, SSOP records or reviews to the repo. NRs name inspectors and plant personnel. The `.gitignore` excludes PDFs as a safeguard.
- A public repository is visible to anyone. GitHub Pages on a private repository requires a paid GitHub plan.

## Limits

This tool gives a regulatory assessment to inform your decision. It is not legal advice. Confirm appeal timing and channel with your Frontline Supervisor, and check every draft letter against your own records before sending.
