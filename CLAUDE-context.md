# Context for Claude -- seven-suppers-menu

_Copied from Claude's memory on Andrew's Mac, 26 September 2026, by `vault-tools/sync-claude-context.py`. Don't edit by hand -- it's regenerated._

## About Andrew

Andrew Lord builds a portfolio of small personal projects, one GitHub repo each
(on his Mac they live in `~/Projects/<repo>`). He is technically fluent: give
concrete detail (file:line, what the code actually does), not just summaries.
His Obsidian vault "Andrew Second Brain" is the durable home for plans; the
private repo `andrew-second-brain` mirrors it (see "Working in the cloud").

**Commit and push without asking** -- he has authorised it durably. Stop only
for a genuine content problem (a secret or someone's personal data about to be
committed), and report that as a finding.

Friendly, not too verbose. Laura (wife), Clara (7) and Felix (4): anything
built for Laura must work as a plain phone link, no accounts or apps.

## Working in the cloud (Claude Code on the web)

This file is copied from the memory Claude keeps on Andrew's Mac, so a cloud
session starts with the same context. The Mac copy may be newer -- the date
is above. In the cloud, as opposed to on the Mac:

- **No Mac-only things:** no launchd jobs, no iCloud Drive, no `~/.secrets`,
  no local Telegram pollers, no Homebrew tools that aren't installed by the
  environment's setup script. Code that runs on the Mac on a schedule can be
  *edited* here, but it won't run until the Mac pulls the change.
- **The vault:** `andrew-second-brain` (a separate private repo) is the Second
  Brain vault. Edits pushed there reach iCloud and Obsidian when the Mac next
  syncs (vault-tools/commit-second-brain.py pulls before it pushes). The Lord
  Family vault is the private repo `the-lord-family/obsidian-vault`.
- **Always commit and push** before the session ends: the Mac and the other
  sessions only see what's on GitHub.

## Memory: project-seven-suppers

Seven Suppers: a weekly meal-planning agent for Andrew's family of 4 that plans 7 evening meals (high protein, lower fat, variety, value, cross-meal ingredient efficiency), publishes a menu + recipe artifact, and will eventually build the Tesco basket via the Basketeer SDK/MCP (https://github.com/tobyandrews1985/basketeer — unofficial, checkout stays human).

Status (2026-07-19): Phase 1 delivered; Phase 2 live — Basketeer installed in `~/Projects/seven-suppers/` (Node via Homebrew), MCP server registered in `~/Projects/.mcp.json`, Tesco session harvested (~30-day expiry, re-run `npx basketeer login` inside tmux — needs a TTY — when it lapses; session at `~/.basketeer/session.json`, chmod 600). Week 1 basket loaded live: 23 lines, £44.18. CLI: `npx basketeer search|product|nutrition|basket|slots|orders|checkout`. Rate limit 1 req/s; searches can misfire (a "3 pack peppers" query returned tea towels) — sanity-check titles before adding. Design doc artifact: https://claude.ai/code/artifact/899f0326-e7cc-46c4-8db5-59c80527230e · Week 1 menu artifact (20–26 Jul): https://claude.ai/code/artifact/27205308-abbf-478d-8fdd-a1c2e059c5cd

Family documents live in the [[reference-obsidian-vault]] under `Claude Projects/Seven Suppers/` (vault reorg 2026-08-07 moved them from root-level `Seven Suppers/`; CLI config.json dataDir and the Desktop launcher were re-pointed 2026-08-08 — the launcher now reads dataDir from config.json, so future moves only need the one config edit). Newer docs since: Favourites.md, Household.md (per-day headcount/time overrides), Andrew's tastes.md + `Solo week YYYY-MM-DD.md` (solo mode), occasions feature (feast/brunch/posh-dinner) and a web control panel added to the repo; provider switched to Gemini (openai-compatible endpoint, key in gitignored config.json): Preferences.md (starter draft, Andrew to edit ✏️ items), Store cupboard.md, Recipe sites.md, Votes.md, plus one `Week of YYYY-MM-DD.md` per week. Read Preferences + Store cupboard + Votes before planning any week. Andrew originally wanted preferences on Google Docs — vault is the interim home.

Family sharing (2026-07-20): wife (non-IT-literate) views the menu at the stable public URL https://andrewlord311-sudo.github.io/seven-suppers-menu/ — public repo `seven-suppers-menu` (local clone `~/Projects/seven-suppers-menu/`), updated by `npx seven-suppers publish` (new CLI command; `publishDir` in config.json). Only rendered menu HTML is published — never family docs/config/Tesco session. Her votes flow through Andrew (tell him / shared note → `vote` command). Andrew confirmed public menu is fine; his concern was Tesco account access, which the static page can't touch.

Weekly rhythm: plan Saturday, family reviews/swaps Sunday, shop, cook, vote nightly (scores out of 5 → Votes.md; new recipes' votes count double). Sunday roast is deliberately oversized to seed next Monday's meal + stock. Phase 3 = per-person taste profiles, seasonal rotation.

Solo mode (2026-08-07): Laura away 11–18 Aug, so there's now `Andrew's tastes.md` in the vault — Andrew's *personal* profile for cooking-for-one (Korean/SE Asian heat, North African, curries, proper chilli; loves the family vetoes — mushrooms, chillies, frozen peas, unusual pulses; wants more noodles/lentils/pulses; protein rules relaxed; only veto is offal; competent cook, wants a mix of 40-min and 15-min nights). An 8-day solo menu is **drafted and awaiting his review at the weekend** — artifact https://claude.ai/code/artifact/2f506bba-6439-4588-b27c-bee785b492e7, vault note `Solo week 2026-08-11.md`. Not yet priced or basketed. Two open questions before shopping: which unticked cupboard items he actually has (gochujang, harissa, preserved lemons, soy, sesame oil, fish sauce, basmati, eggs, parmesan), and what perishables are in the fridge on 11 Aug. Note the cupboard file's ticks are ambiguous (owned vs stocktake progress) — asked twice, never resolved.

Standalone version (2026-07-20): private repo https://github.com/andrewlord311-sudo/seven-suppers (local clone `~/Projects/seven-suppers/`) — Node CLI, LLM-agnostic (`--provider anthropic|openai --model … --base-url …`; Anthropic via official SDK, anything OpenAI-compatible incl. Ollama via fetch). Commands: `plan`, `basket show|load`, `vote`, `login`. `config.json` (gitignored) points dataDir at the vault's Seven Suppers folder. LLM path untested — no ANTHROPIC_API_KEY on the machine yet; everything else (render, basket, vote) smoke-tested. Claude Code + Basketeer MCP remains the conversational interface.

Feature backlog (2026-07-21): `~/Projects/Incoming/Supper planner to do.md` — see [[project-incoming-idea-inbox]] — lists variable meal count/any start day, recipe favouriting + free-text style prompts, a website-collection feature, a who's-eating/time-available table, a "wow" complex-recipe option, scanning Tesco offers for recipe inspiration (pairs with the Basketeer integration above), low/mid/high budget switch, a multi-person "Feast" mode with 3 options, and a Saturday brunch button (3 options). Not yet prioritized into phases.
