# Transfer inventory

Prepared Nov 16, 2026, when the project was moved out of a Claude chat into GitHub.

## Where the project came from

- The work happened in a single Claude chat, **not inside a Claude Project**. There were no project instructions, no project knowledge files and no uploaded files to transfer.
- Sources inspected: the chat itself and the working files the app was built from.

## Transferred

| Repo path | Source | Notes |
|---|---|---|
| `index.html` | Final app file (`lookthrough.html` in the chat workspace) | Copied unchanged except for the file name. It was published under `index.html`, so the name matches. |
| `docs/concept.md` | Product idea, positioning, business model and stress tests discussed in the chat | Written up from the conversation. Contains no new features. |
| `docs/methodology.md` | Scoring logic in `index.html` | Documents the code as it is. |
| `docs/data-sources.md` | `FUNDS` data and source links in `index.html`, plus search results from the chat | Marks which figures are derived or estimated. |
| `README.md`, `.gitignore` | New | Repository scaffolding. |

## Not transferred

| Item | Why |
|---|---|
| Version 1 of the app (fictional funds, sample data) | Overwritten in the workspace by the real-fund version. The earlier version exists only in the Claude artifact's version history and can't be exported from here. It was superseded anyway. |
| The published Claude artifact page | Hosted by Claude and private to its owner. The repo contains the same file. Share or retire the artifact separately. |
| The chat transcript | Not exportable as a file from here. `docs/concept.md` covers the decisions in it. |
| Full text of web pages used for research | Third-party content. Only links and the specific figures used are included. |

## Secrets and private data check

- `index.html` was scanned for API keys, tokens, passwords and email addresses. **None found.** The app calls no APIs and needs no credentials.
- The only external requests are Google Fonts stylesheets and font files.
- No personal information about team members is included.
