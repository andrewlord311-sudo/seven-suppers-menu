# seven-suppers-menu

The published output of [Seven Suppers](https://github.com/andrewlord311-sudo/seven-suppers) —
the week's meal plan, as a page Laura can open on her phone.

**Live:** https://andrewlord311-sudo.github.io/seven-suppers-menu/

## Why it is a separate repo

Seven Suppers is private: it holds family preferences, household details and a
Tesco session. This repo is public, because GitHub Pages needs it to be, and it
contains **only the rendered menu HTML** — nothing else from that project ever
lands here.

That separation is the point. Keep it: no config, no preferences, no session
data, no shopping basket.

## How pages get here

`npx seven-suppers publish` renders the current week and pushes it. `index.html`
is the stable entry point Laura has bookmarked; dated files like
`week-2026-07-20.html` are the individual weeks.

The requirement that shaped all of it: a plain link, no app, no login, no
account.
