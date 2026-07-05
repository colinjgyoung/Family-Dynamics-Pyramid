# Family Dynamics — Character Pyramid

A single self-contained `index.html` — no build step, no dependencies except a Google Fonts CDN link. Implements the **Character Pyramid** facilitation exercise from the Family Dynamics deck: rank 6 of the 10 archetype cards into a 1-2-3 pyramid by drag-and-drop or tap-to-place, flip any card to see its back.

## Card content source

Front (phrase + archetype name) and back (Core Drive / Contribution / Tension / Growth Direction) copy is drawn from nnherit's own "Family Dynamics™ Character Map" document. A separate IP review flagged that some back-of-card text in an older spreadsheet source tracked a third-party Enneagram site too closely — this app does not use that source.

## Try it locally

Just open `index.html` in any browser — double-click the file, no server needed.

## Publish on GitHub Pages

This folder is already a git repo connected to GitHub Desktop. To publish:

1. Commit and push `index.html` (and this README) via GitHub Desktop as usual.
2. On GitHub.com: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: main / (root)** → Save.
3. GitHub gives you a URL shortly after, typically `https://<your-username>.github.io/<repo-name>/`.

No build step needed — the file is deployment-ready as-is.

## What's in this version

Merged from an earlier Replit prototype Colin built (PersonalityCardSelector):

- **Progress counter** ("X of 6 placed") always visible above the pyramid.
- **Adaptive instructions** — detects touch devices and swaps to tap-first phrasing.
- **Explicit selection banner** — when a card is picked up, a banner names it and states exactly what to do next, addressing a real UX bug from the Replit version (clicking a card felt like it should flip it, not enter placement mode).
- **"Copy my pyramid" button** — once all 6 slots are filled, copies a plain-text summary to the clipboard. Stands in for the Replit app's email/1-pager/"bonus challenge" sharing feature, which needed a backend that doesn't fit a static GitHub Pages file.

## Open decisions not resolved here

- **3 cards vs 6 cards:** the Replit app has people pick their **top 3** favourite cards. This build follows the documented 6-card "Character Pyramid" exercise from the facilitator material and brand-decisions.md. Worth confirming which mechanic nnherit wants live.
- **Flat design vs real card art:** this build uses a lightweight CSS card design; the Replit app used the actual printed card images. Can swap in real art later if wanted.
- **Lead capture:** the Replit app's email-gated "1-pager breakdown" is a real, valuable feature but needs a backend — out of scope for a static GitHub Pages file. Could be added later via a form service (e.g. Formspree) if wanted.

## Known limits

- Only 2 of the 10 cards' original spreadsheet copy could be checked for IP risk against a third-party source — see the nnherit project's `Family_Dynamics_Card_Copy_IP_Review.md` for details before sourcing any *other* back-of-card text.
- Interaction logic was traced by hand rather than tested in a live browser — worth a quick click-through before sharing widely.
