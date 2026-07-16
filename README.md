# Family Dynamics — Character Pyramid

**Live app:** https://colinjgyoung.github.io/Family-Dynamics-Pyramid/

A single self-contained `index.html` — no build step; external dependencies are a Google Fonts CDN link and html2pdf.js (lazy-loaded from cdnjs only when a PDF is requested, with a no-CDN print fallback). Implements the **Character Pyramid** facilitation exercise from the Family Dynamics deck: rank 6 of the 10 archetype cards into a 1-2-3 pyramid, flip any card to read its back, and download a personal 1-page PDF profile of your mix.

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

- **Personal 1-pager (PDF)** — once all 6 slots are filled, a primary "Download my 1-pager (PDF)" button generates a designed A4 profile (`my-family-dynamics-pyramid.pdf`) via html2pdf.js from cdnjs: lead pattern with its good-day/under-pressure arrows, a "Working with you" interpersonal snapshot, the lower ranks, the unchosen cards, one interplay insight, and a reflection question. All copy and rules come from the nnherit project's `2026-07-15-pyramid-profile-content-model.md` and `2026-07-15-pyramid-profile-logic.md` (R7 cluster rule excluded from v1; profile requires all 6 cards placed). A secondary "or print this page" action prints the same profile DOM and doubles as the fallback if the CDN is blocked.
- **Early finish** — after placing 3 cards, a "No more cards match me — finish with N" button completes the exercise with a partial pyramid (summary + copy only; the 1-pager needs all 6).
- **Real card art** — optimized WebP scans of the printed cards (fronts and backs) in `cards/`, shown large in a scannable tray; click/tap a card to flip it, use its Choose button to place it.
- **Progress counter** ("X of 6 placed") always visible above the pyramid.
- **Adaptive instructions** — detects touch devices and swaps to tap-first phrasing.
- **Selection banner** — fixed to the bottom of the viewport while a card is chosen, naming it and the next step.
- **Keyboard accessible** — Tab/Enter/Esc drive the whole exercise; focus survives re-renders.
- **"Copy my pyramid" button** — tertiary action; copies a plain-text summary to the clipboard.

## Decisions made since the Cowork handoff

- **6-card pyramid, confirmed** — not the Replit app's top-3 mechanic.
- **Real card art, confirmed** — cards now use the actual printed card photography (in `cards/`, front + back per archetype), not the original flat-CSS design.
- **Lead capture — still open:** the Replit app's email-gated "1-pager breakdown" is a real, valuable feature but needs a backend — out of scope for a static GitHub Pages file. Could be added later via a form service (e.g. Formspree) if wanted.

## Known limits

- The real card back images use the printed cards' own "good moments / normal day / bad moments / others feel" copy, which has **not** been checked against `Family_Dynamics_Card_Copy_IP_Review.md` (in the main nnherit project folder) — that review only covers 2 of the 10 cards' *older spreadsheet* copy, a different text source. Used as-is per an explicit decision, not an oversight.
- Interaction logic (drag/tap-to-place, flip, reset, progress counter, copy-to-clipboard) has been click-tested in a live browser — working as expected.
