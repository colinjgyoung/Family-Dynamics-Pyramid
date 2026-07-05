# Family Dynamics — Character Pyramid

**Live app:** https://colinjgyoung.github.io/Family-Dynamics-Pyramid/

A single self-contained `index.html` — no build step, no dependencies except a Google Fonts CDN link. Implements the **Character Pyramid** facilitation exercise from the Family Dynamics deck: rank 6 of the 10 archetype cards into a 1-2-3 pyramid by drag-and-drop or tap-to-place, flip any card to see its back.

## Card content source

Front (phrase + archetype name) and back (Core Drive / Contribution / Tension / Growth Direction) copy is drawn from nnherit's own "Family Dynamics™ Character Map" document. A separate IP review flagged that some back-of-card text in an older spreadsheet source tracked a third-party Enneagram site too closely — this app does not use that source.

## Try it locally

Just open `index.html` in any browser — double-click the file, no server needed.

## Publish on GitHub Pages

This folder is a git repo, connected to `github.com/colinjgyoung/Family-Dynamics-Pyramid` and also addable in GitHub Desktop. To publish (one-time setup):

1. Push `index.html` (and this README) — via GitHub Desktop or `git push`, as usual.
2. On GitHub.com: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `master` / `(root)`** → Save.
3. GitHub builds the site (takes a minute) and serves it at the Live app link above.

No build step needed — the file is deployment-ready as-is.

## What's in this version

Merged from an earlier Replit prototype Colin built (PersonalityCardSelector):

- **Progress counter** ("X of 6 placed") always visible above the pyramid.
- **Adaptive instructions** — detects touch devices and swaps to tap-first phrasing.
- **Explicit selection banner** — when a card is picked up, a banner names it and states exactly what to do next, addressing a real UX bug from the Replit version (clicking a card felt like it should flip it, not enter placement mode).
- **"Copy my pyramid" button** — once all 6 slots are filled, copies a plain-text summary to the clipboard. Stands in for the Replit app's email/1-pager/"bonus challenge" sharing feature, which needed a backend that doesn't fit a static GitHub Pages file.

## Decisions made since the Cowork handoff

- **6-card pyramid, confirmed** — not the Replit app's top-3 mechanic.
- **Real card art, confirmed** — cards now use the actual printed card photography (in `cards/`, front + back per archetype), not the original flat-CSS design.
- **Lead capture — still open:** the Replit app's email-gated "1-pager breakdown" is a real, valuable feature but needs a backend — out of scope for a static GitHub Pages file. Could be added later via a form service (e.g. Formspree) if wanted.

## Known limits

- The real card back images use the printed cards' own "good moments / normal day / bad moments / others feel" copy, which has **not** been checked against `Family_Dynamics_Card_Copy_IP_Review.md` (in the main nnherit project folder) — that review only covers 2 of the 10 cards' *older spreadsheet* copy, a different text source. Used as-is per an explicit decision, not an oversight.
- Interaction logic (drag/tap-to-place, flip, reset, progress counter, copy-to-clipboard) has been click-tested in a live browser — working as expected.
