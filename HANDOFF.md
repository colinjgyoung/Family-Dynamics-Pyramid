# Handoff — Family Dynamics Character Pyramid

Context for picking this up in Claude Code. Written 2026-07-01 after building this in Cowork mode (Anthropic's browser/file assistant) — see that for full history if needed, but this note should be self-contained.

## What this is

A single-file, no-build web app (`index.html`, inline CSS/JS) implementing the **Character Pyramid** facilitation exercise for nnherit's **Family Dynamics deck** (10 behavioural archetype cards). Users rank 6 of the 10 cards into a 1-2-3 pyramid (top choice / 2nd+3rd / 4th-6th) by drag-and-drop or tap-to-place, and can flip any card to see Core Drive / Contribution / Tension / Growth Direction on the back.

Deployment target: GitHub Pages, deployed straight from this repo (`main` branch, root). No build step — `index.html` is the whole app.

## Current state

- `index.html` — the app. Working end to end per manual code trace (tray → pyramid placement, swapping, flip, reset, progress counter, "copy my pyramid" clipboard summary). **Not yet verified in a live browser** — local file:// access was blocked in the prior session's sandboxed Chrome extension, so this needs a real click-through before treating it as done.
- `README.md` — deployment steps + a summary of what was merged in from a prior Replit prototype.
- Card data (all 10 archetypes, front phrase + back copy) is hardcoded in a `CARDS` array at the top of the `<script>` block — easiest place to edit copy or add cards.

## Two open decisions — flag these to Colin before assuming either direction

1. **6-card pyramid vs 3-card "top picks"**: this build follows the documented "Character Pyramid" exercise (rank 6 of 10, 1-2-3 layout) from nnherit's facilitator material. Colin has an older Replit prototype ("PersonalityCardSelector") that instead has people pick their **top 3** favourite cards with a simpler UI. Not reconciled — could be two different exercises, or a scope simplification worth adopting.
2. **Flat CSS card design vs real printed card art**: this build uses a lightweight original CSS design (colour-block cards, no images) per an earlier explicit decision. The Replit prototype used the actual printed card JPGs (found in Colin's Google Drive, in a folder called "Character Cards 2024 - jpgs", 10 colours × front/back). Swapping in real art is possible later but wasn't done here by design.

## Known gaps / next steps

- **No live browser test yet** — do this first. Check: drag from tray to slot, tap-to-place fallback, swap logic when tapping a filled slot while another card is selected, flip button on both tray and placed cards, reset button, progress counter, "copy my pyramid" clipboard button.
- **Lead capture feature not built**: the Replit prototype had an email-gated "1-pager breakdown" of results plus a "bonus challenge" to share with a colleague — this needed a Postgres backend + email sending, which doesn't fit a static GitHub Pages file. Current stand-in is a no-backend "copy to clipboard" button. If Colin wants real lead capture, that requires either a small serverless function (e.g. a Cloudflare Worker or Vercel function) or a third-party form service (Formspree, Getform) — a genuine scope change from "static site," worth a conscious decision, not a silent addition.
- **Mobile testing**: adaptive instructions (tap-first phrasing on touch devices) and touch-friendly tap-to-place were built in, but not tested on an actual touch device.

## IP note — read before touching card back-copy

A separate review (`Family_Dynamics_Card_Copy_IP_Review.md`, in the main nnherit project folder under `04_PRODUCTS_AND_PLAYFUL_OBJECTS`, not in this repo) found that an older spreadsheet source for 2 of the 10 cards' back-of-card text tracked crystalknows.com (a third-party Enneagram site) closely enough to be a plagiarism risk. This app's card copy uses a different, original source instead — nnherit's own "Family Dynamics™ Character Map" document (Core Drive / Contribution / Tension / Growth Direction per archetype, already baked into the `CARDS` array in `index.html`). Don't pull card copy from any other spreadsheet/source without checking it against that review first.

## Brand/voice reference (if adding any new UI copy)

nnherit's brand and voice rules live in the main nnherit project folder (`00_CLAUDE_AND_CONTEXT/brand-decisions.md` and `voice-and-style.md`) — not duplicated here. Key facts already baked into this app: official product name is "Family Dynamics deck" (not "Character Cards"), the 10 archetypes are The Driver / Stabiliser / Initiator / Standard Setter / Controller / Integrator / Catalyst / Supporter / Strategist / Steward, and brand colours are yellow `#F3D600` / black / white with Source Sans Pro — already used in this app's shell styling (cards keep their own individual colours).

## Working style Colin prefers

Concise, direct, minimal unnecessary explanation. Flag assumptions and open questions rather than silently deciding. State uncertainty rather than presenting guesses as settled fact.
