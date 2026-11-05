---
doc: visibility-plan
status: approved (owner yes 2026-11-05)
updated: 2026-11-05
step: ST-5
---

# Build With Me: Visibility Plan

Replaces the first draft (`Downloads\build-with-me-visibility-plan.md`, 2026-11-05), which was written without the
project's context. Decisions D-24 to D-37 and assumptions A-1 to A-9 are in `docs/plan/decisions.md`. The repo was
renamed 2026-11-05 (owner yes): `github.com/paveliko123/build-with-me`, demo `https://paveliko123.github.io/build-with-me/`.
In-app screens keep "Build With Me at Home".

## 1. Goal and limits

- **Goal (D-25):** GitHub visibility first: stars and a findable listing. A few real families trying it are a bonus,
  not a target (§7 tracks them as a signal only).
- **Time (A-1):** about 2–3 hours a week of the owner's time. Few places, each worth the time, not 20 posts for one
  click each.
- **Tone (D-26):** "an open-source Claude Code plugin for parents". Never "kid-safe", "guardrails" as a label, or
  any promise of safety. Name the actual layers instead: kids' sessions have no tools and can't reach your files, a
  separate Claude call checks messages both ways, and you get a report after every app. Understate; let people be
  pleasantly surprised.
- **Version (D-27):** launch 0.1.2 as it is, tagged `v0.1.2`. Open safety items are listed as known limitations.
- **Not used:** LinkedIn (A-2 overturned, owner's choice), paid promotion, Product Hunt.
- **Where it stands today (checked 2026-11-05):** 1 star, 0 forks, repo created 2026-10-07 with commits since.
  The repo has an About description and a website link (the new demo URL), but no topics, no releases and no issue
  forms; GitHub shows its license as "Other" (see P-1). The owner's profile has a name, bio, profile README and the
  pinned repo; its website link still holds the old demo URL (404) and the picture is not confirmed.

## 2. Phase 0: fix before any outreach

One pass on a short-lived branch, one test run, one commit series, merged when checks pass. Each item names how it
is checked.

| # | Item | Done when |
|---|---|---|
| P-1 | **Remove the hackathon story (D-32).** Rename `devpost/` to `docs/design/`; update the paths in code comments, README, SECURITY.md and `.gitignore`; drop the demo page's "modified Devpost…" bullet; shorten the README credit to one line under Credits. Make the root `LICENSE` plain MIT so GitHub recognizes it (A-9), with the Devpost notice kept in `app/skills/LICENSE` and the README credit line; keep the course skills themselves and the guide's internal name-mapping lines in `server/journey/prompt/wrapperLayer.ts` (kids never see them). | A search of tracked files outside `app/skills`, `app/dist/skills`, `LICENSE`, `server/journey/prompt/` (incl. the `safety.ts` check pattern, which must stay), `app/dist` (rebuilt from it), `docs/design/` and `docs/plan/` finds no "devpost" or "hackathon" except the README credit line and the comments that credit the course skills (`scripts/stamp-build.mjs:3`, `server/journey/skillsDir.ts:1`); the scripts' own write paths (`scripts/e1-isolation.ts`, `e2-speech.ts`, `idea-page.mjs`, `usage-experiment.ts`) point at `docs/design/`; `npm run typecheck`, `npm run test:guard` and `npm run build` pass (`npm test` doesn't exist). |
| P-2 | **README first screen (§3).** | At 1366×768 the first screen shows what it is, who it's for, and the GIF and demo link without scrolling (the rest of §3's first-screen list may sit just below). |
| P-3 | **Mac labeled untested (D-28).** Badge "Windows · Mac untested"; the "What you need" line matches. | Badge and text agree. |
| P-4 | **Known limitations (D-27, A-3).** SECURITY.md gets a short "Known limitations" list: the open review items in plain terms, in two groups: weaknesses, each with what it actually needs to matter (for example another program on the laptop, or someone on the home network), and how it handles data today (the kids' runs ignore the parent's telemetry opt-outs, the kid's nickname goes to the report writer, prompt files unused for a week are removed at the first Claude call after the server restarts); no step-by-step detail, plus "a hobby project, not professionally audited". It also says the safety check runs in the guide's conversation by default (audit line 54). | The list names every open ST-3 item from `docs/design/security-audit.md` without exploit steps; the 13 Low/Info ST-4 items get one grouped line (A-3 names only ST-3, D-27 says "open items"; default, owner may change). |
| P-5 | **Bug-report form.** `.github/ISSUE_TEMPLATE/bug.yml` with fields: Windows or Mac, Node.js version, Claude plan (Pro, Max, Ultra, Team, Enterprise, other or unsure), what happened, what you expected. Plus a short "idea" form and a `config.yml` that sends security reports to SECURITY.md. | A new issue on GitHub shows both forms and the security link. |
| P-6 | **Release `v0.1.2` (D-27).** After P-1 to P-5 and P-11 are merged, tag the Phase 0 merge commit (not `ca17c35`, the 0.1.2 build) with short notes: what it does, how to install, link to the limitations list. The version number stays 0.1.2, so installed copies don't receive Phase 0 changes. | The Releases page shows v0.1.2 and the notes' limitations link works. |
| P-7 | **Repo settings (owner clicks).** Website: set (new demo URL). Topics: `claude-code`, `claude-code-plugin`, `kids-coding`, `parents`, `local-first`, `plan-first`. Social preview image: 1280×640 from the video's closing card. | The repo page shows the link and topics; a shared link shows the picture. |
| P-8 | **GitHub profile (owner clicks, 5 minutes).** Name, bio, README and pin are done (decisions.md; seen 2026-11-05). Left: picture, and the website link changed to the new demo URL (the old one is 404). No employer or work email. | The profile shows the picture and a working website link. |
| P-9 | **Profile README.** Done 2026-11-05 (owner yes): public repo `paveliko123/paveliko123` with the §8 text. | The profile shows the README, with the new repo and demo URLs. |
| P-10 | **Listen to the whole video (D-29, A-5).** A-5 checked the frames but not the sound. Listen to all 2:33 for a kid's voice, name or school. | None found; if found, trim or replace the video before any outreach (it is already public on YouTube). |
| P-11 | **Plugin manifest.** Add `homepage` and `repository` to `.claude-plugin/plugin.json` (both missing); run `claude plugin validate --strict` (needed for the listings in §5.1). | Validation passes. |

## 3. README changes

Keep all the content; rebuild the first screen and move reference material lower. The exact new text is shown
before → after at build time.

**New first screen, in order:** icon, title and badges (Mac badge per P-3) → the current one-line description
(it already follows D-26) → the "nothing is sent to the developer" line → a 15–25 s GIF → "Try the 2-minute demo"
and "Watch the 2½-minute walkthrough" (the video, A-5) → the 18+ note plus the D-33 line (§9).

**New sections:**
- **See it:** three screenshots: a kid's step screen, the *My apps* shelf with real apps (D-29, A-4), the top of a
  parent report (made-up kid).
- **FAQ:** What leaves my computer? · How much of my plan does it use? · Does it work on Mac? (untested) · Is my
  kid allowed to use Claude? (the existing 18+ wording) · Can I check the code before installing? (the existing
  "have your own Claude check it" block).
- **Contributing:** how to report a bug (the P-5 forms), what help is welcome (Mac testing, translations, ideas).

**Moved:** "Safety layers and their limits" (D-37; was "How kids are kept safe") and "The parent report" move up, right after "What a kid does". "Forgot your
PIN", "Updating" and "Uninstalling" go under one collapsed **Help** heading.

**Dropped from the first draft:** the comparison table with hosted kids' tools. Its facts about other products
weren't checked, and it invites the "how is this different" debate the tone avoids.

## 4. Assets

| Asset | Source | Used in |
|---|---|---|
| Walkthrough video | The Devpost video as it is, https://youtu.be/DFgWYG4G0kE, 2:33 (A-5), after P-10. | README, the dev.to post, people and club messages, Reddit; not the listing forms |
| GIF, 15–25 s, under 10 MB | Cut from a fresh screen recording of the real app: pick a look → a picture card → build progress → the app opens. ScreenToGif (free, Windows) — its download needs the owner's yes. | README top, Reddit |
| 3 screenshots | Real app, same window size. Real kids' apps allowed (D-29); each checked for a kid's name, school or other personal detail first (A-4). | README "See it", listings |
| Sample parent report | A report from a made-up kid's session (like the 2026-10-23 "My Coloring Book" demo data), saved as `site/sample-report.html`, so it opens on the Pages site (a file under `docs/` would show as source). | README, people outreach |

## 5. Routes

Ranked by expected value per hour, lowest scrutiny first. Sources: three independent research runs on 2026-11-05
(Claude researcher, Codex Terra, Gemini Flash; D-30). Labels: **Verified** = a researcher opened the page;
**Researched** = a secondary source; **Estimate** = inference.

### 5.1 Listings (lasting, low scrutiny, about 15–30 minutes each)

1. **Anthropic's plugin directory / community marketplace.** Anthropic's docs now say to submit from the developer
   portal at claude.ai/directory/manage with a paid claude.ai plan, after `claude plugin validate --strict`
   (Verified: https://code.claude.com/docs/en/plugins/publish.md); the community marketplace repo
   (https://github.com/anthropics/claude-plugins-community) describes a security scan before approval (Verified).
   If approved, people can install through Anthropic's marketplace; check the real install command after approval.
   Submit after Phase 0 (P-11). It may be refused over the 18+ rule (Estimate); D-33: not asked first.
2. **awesome-claude-code** (https://github.com/hesreallyhim/awesome-claude-code, ~57k stars). Rules: web issue form
   filed by a person, repo at least 14 days old with commits after day one or 100+ stars, one plain line with no
   emoji, not addressed to the reader (Verified). The repo qualifies (created 2026-10-07). Its guide says a project
   that requires signup or payment is a blocker for review; this one needs a paid Claude plan, so a refusal is
   possible (Estimate).
3. **Plugin directories:** mods4claude (https://mods4claude.com/submit) and ClaudePluginHub
   (https://www.claudepluginhub.com/). Both take a public repo with `.claude-plugin/plugin.json`, which this repo
   has; both say they scan GitHub, and mods4claude reviews by hand, so listing isn't guaranteed (Verified). Traffic unknown (Estimate: small but lasting).

### 5.2 One write-up (lasting)

4. **A dev.to post**, "How my kids plan and build small apps with Claude Code, and the plugin I made for it"
   (A-2: the write-up stays; no LinkedIn). Open publishing, new accounts can post, a friendly developer culture with
   many developer parents (Researched, Gemini). About 2.5 hours once (capped, §7); it gives every later post and message a link
   with more depth than the README.

### 5.3 Communities (one post each, after the listings)

5. **r/ClaudeCode weekly showcase thread.** Explicitly welcomes projects: what was built, how Claude Code was used,
   a link, a lesson (Verified). Medium scrutiny (Estimate). About 20 minutes.
6. **Nerdy Parents Club** (Cambridge, MA): parents building with kids and Claude Code; its newsletter invites
   member projects for a "project wall" (Verified). Low scrutiny, small friendly audience. About 10 minutes.
7. **r/SideProject:** hobbyists sharing free side projects; relaxed self-promotion rules for original creators
   (Researched, Gemini only). Low scrutiny (Estimate). About 15 minutes.
8. **r/ClaudeAI, showcase flair** (size sources disagree, 130k to 1.3M; Gemini says an account needs about 50 karma, unconfirmed). Medium scrutiny: a similar dad-built kids' project
   drew friendly comments and an under-18 question (Verified, Codex). Optional, week 3, only if 5 to 7 went well.

Reddit posts go from the owner's own account; minimum account age or karma for r/ClaudeCode and r/SideProject wasn't confirmed, so check each sub's rules before posting.

Not chosen, to stay inside the time budget: the Claude Discord's `#project-showcase` channel (Researched, Gemini
only; medium scrutiny with staff present).

### 5.4 People (two or three, D-25)

Write only after reading their recent posts yourself; one personal line from that reading. No lead showed a paid
plan in words; Claude Code use implies one (Estimate). Maximum three people, one message each (D-25).

The people table, each person's evidence and route, and the "checked and dropped" names are in the local-only file
`docs/plan/private/outreach-people.md` (not tracked, because this repo is public).

### 5.5 Skip

- **Show HN (D-34, owner yes 2026-11-05; narrows D-25):** an HN thread about a teen's suspended Claude account shows
  the terms question dominating (Verified, Codex). High scrutiny. Revisit only after real families have used it; if
  it happens, link the repo, not the mockup demo (the rules want something people can try, not a landing page).
- **Product Hunt:** hosted-product audience; a terminal install fits poorly (Estimate).
- **r/ChatGPTCoding self-promotion thread:** allowed, but a broad audience with no fit evidence (Verified, Codex).
- **A local club session (D-29):** the owner's decision. (Writing to the Nerdy Parents Club newsletter, route 6, is different.)

## 6. Messages

- Frame every message and post as "me helping my own kids"; each parent decides for their own family, with their
  own evaluation and risk assessment (D-33). Never a recommendation that other parents do it.
- Under 120 words, one ask, feedback not promotion. Plain words; describe what a kid and a parent see.
- Only claims the README supports; no "kid-safe" (D-26). Real links only: repo, demo, video, sample report.
- Communities: one follow-up reply after 7 days at most. People: one message each, no follow-up (§5.4).
- Never name someone's kids.

**Template** (people and the Nerdy Parents Club):

```text
Subject: A Claude Code plugin for parents, built for the kitchen-table sessions you write about

Hi <name>,

I read <specific post>: <one honest sentence about what stuck with you>.

I made a free, open-source Claude Code plugin for doing this with my own kids at home.
My kids talk with a guide through six steps (start, idea, design, plan, build, ship) on my
laptop or a tablet, under my own Claude plan. Their sessions can't touch my files, a
separate Claude call checks what's said both ways, and I get a report after each app.
Whether it fits another family is each parent's call.

2½-minute walkthrough: https://youtu.be/DFgWYG4G0kE
Browser demo: https://paveliko123.github.io/build-with-me/
Repo: https://github.com/paveliko123/build-with-me

If you try it once, I'd love to hear where it falls short. Blunt is fine.

Pavel
```

**Reddit post outline:** title "I built a Claude Code plugin so my kids can plan and build small apps on my account
while I supervise" → what it is (two lines) → the GIF → what my kids made (two real apps, D-29) → how Claude Code is
used (no tools for kids' sessions, a separate safety check, a report) → the 18+ note in one line → links → "feedback
welcome, especially from Mac users".

## 7. Timeline and measures

| When | Work | Owner hours |
|---|---|---|
| Week 0 | Phase 0 (Claude builds P-1 to P-6 and P-11; owner does P-7, the rest of P-8 and P-10 (listening, 3 min); P-9 is done; the GIF recording and screenshots) | 2–3 |
| Week 1 | Listings 1–3 | 1–1.5 |
| Week 2 | The dev.to write-up, capped at 2.5 hours (A-7); Nerdy Parents Club | 2.5–3 |
| Week 3 | r/ClaudeCode showcase; r/SideProject; one or two people; optional r/ClaudeAI; fix what testers hit | 2–3 |
| Week 4 | Review the numbers; keep, change or stop | 0.5 |

Every Friday, write down from Insights → Traffic (it keeps only 14 days): stars, unique visitors, top referrers,
installs reported, issues opened by others.

| Signal | Week 4 target (a guess, adjust after week 2) | If it misses |
|---|---|---|
| Stars | 25 | Many visitors but few stars: the first screen isn't working. |
| Referrers | Know which route sent people | Drop the weakest route. |
| Families who tried it | No target, a signal only | Ask any who tried it where the install stuck. |
| Issues from others | 1 | None means no installs, not no bugs. |

## 8. Profile README draft (P-9)

```markdown
Hi, I'm Pavel 👋

A parent who builds small open-source tools with Claude Code in my spare time.

**[Build With Me](https://github.com/paveliko123/build-with-me)**: a Claude Code
plugin for parents. My kids plan and build their own small apps with an AI guide, on my computer
and my Claude account, while I supervise.
[Browser demo](https://paveliko123.github.io/build-with-me/) ·
[2½-minute walkthrough](https://youtu.be/DFgWYG4G0kE)

Issues and ideas are welcome.
```

Bio (160 characters max), as set: "Parent and hobby builder. I make small open-source tools with Claude Code, like
"Build With Me" for families."

## 9. Risks and open questions

- **The 18+ rule and the owner's own account.** Anthropic's consumer terms require users to be 18+, and its
  age-assurance help page says accounts may be restricted on signs of use by a minor (Verified, Codex:
  https://www.anthropic.com/legal/consumer-terms ;
  https://support.claude.com/en/articles/15171100-age-assurance-on-claude). The README already says letting kids
  use it is the parent's decision. **D-33 (owner yes 2026-11-05):** the README's 18+ note and the FAQ get one line,
  "Anthropic may restrict accounts that show signs of use by someone under 18." Posts stay as they are; Anthropic
  isn't asked first.
- **Open cards before build:** none (D-36 and D-37 answered 2026-11-05).
- **Small audience:** a paid plan, the Claude Code command-line tool and a terminal. Fine for stars; don't judge
  success by mainstream reach.
- **Real examples skew younger:** most parents found build with kids of 5–7, not 8–13 (Verified, two researchers).
  The under-13 picture-card path matters more than the teen path in posts.
- **Similar tools exist** (at least a commercial kids' Claude Code camp; Researched, Claude researcher). If asked, answer in
  one line: free, runs on your computer under your own plan, with a report after every app.
- **Support load:** the bug form (P-5) collects OS, Node.js version and plan up front.
- **Listing review:** Anthropic's marketplace may decline it; awesome-claude-code reviews are best effort.

## Change Log

- 2026-11-05: first draft from the owner's interview (D-24 to D-32) and three research runs.
- 2026-11-05: review round 1 fixes: repo rename; people moved to a local-only file; P-10, P-11 added; P-1, P-2, P-4 to P-8 corrected; unsourced tool names dropped.
- 2026-11-05: planning review, 3 rounds (round 1 Sonnet + Codex Luna as the D-31 trial, flag checker; round 2
  Sonnet + Codex Sol change check; round 3 Codex Sol change check). Fixes: privacy (people list moved to a local file,
  P-10 video sound check), Anthropic directory steps (P-11), P-1 checks, P-4 data-handling wording, schedule.
- 2026-11-05: owner yes on the whole plan (after D-36 and D-37).
