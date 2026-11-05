---
doc: visibility-plan
status: draft, under planning review
updated: 2026-11-05
step: ST-5
---

# Build With Me at Home: Visibility Plan

Replaces the first draft (`Downloads\build-with-me-visibility-plan.md`, 2026-11-05), which was written without the
project's context. Decisions D-24 to D-32 and assumptions A-1 to A-5 are in `docs/plan/decisions.md`.

## 1. Goal and limits

- **Goal (D-25):** GitHub visibility first: stars and a findable listing. A few real families trying it are a bonus,
  not a target.
- **Time (A-1):** about 2–3 hours a week of the owner's time. Few places, each worth the time, not 20 posts for one
  click each.
- **Tone (D-26):** "an open-source Claude Code plugin for parents". Never "kid-safe", "guardrails" as a label, or
  any promise of safety. Name the actual layers instead: kids' sessions have no tools and can't reach your files, a
  separate Claude call checks messages both ways, and you get a report after every app. Understate; let people be
  pleasantly surprised.
- **Version (D-27):** launch 0.1.2 as it is, tagged `v0.1.2`. Open safety items are listed as known limitations.
- **Not used:** LinkedIn (A-2 overturned: the owner's LinkedIn is biopharma-focused), paid promotion, Product Hunt.
- **Where it stands today (checked 2026-11-05):** 1 star, 0 forks, repo created 2026-10-07 with commits since.
  The repo has an About description but no website link, no topics, no releases and no issue forms. The owner's
  GitHub profile is empty (no name, bio, picture or profile README).

## 2. Phase 0: fix before any outreach

One pass on a short-lived branch, one test run, one commit series, merged when checks pass. Each item names how it
is checked.

| # | Item | Done when |
|---|---|---|
| P-1 | **Remove the hackathon story (D-32).** Rename `devpost/` to `docs/design/`; update the paths in code comments, README, SECURITY.md and `.gitignore`; drop the demo page's "modified Devpost…" bullet; shorten the README credit to one line under Credits. Keep the MIT notices in `LICENSE` and `app/skills/LICENSE`, the course skills themselves, and the guide's internal name-mapping lines in `server/journey/prompt/wrapperLayer.ts` (kids never see them). | A search of tracked files outside `app/skills`, `app/dist/skills`, `LICENSE`, the prompt files and `docs/design/` finds no "devpost" or "hackathon"; `npm test` and the build pass. |
| P-2 | **README first screen (§3).** | The first screen (no scrolling at 1366×768) shows what it is, who it's for, the GIF and the demo link. |
| P-3 | **Mac labeled untested (D-28).** Badge "Windows · Mac untested"; the "What you need" line matches. | Badge and text agree. |
| P-4 | **Known limitations (D-27, A-3).** SECURITY.md gets a short "Known limitations" list: the open review items in plain terms (what's affected, that each needs something already on the laptop or home network), no step-by-step detail, plus "a hobby project, not professionally audited". | The list names every open item from `docs/design/security-audit.md` (ST-3, ST-4) without exploit steps. |
| P-5 | **Bug-report form.** `.github/ISSUE_TEMPLATE/bug.yml` with fields: Windows or Mac, Node.js version, Claude plan (Pro, Max), what happened, what you expected. Plus a short "idea" form. | A new issue on GitHub shows both forms. |
| P-6 | **Release `v0.1.2` (D-27).** Tag the current release commit with short notes: what it does, how to install, known limitations link. | The Releases page shows v0.1.2. |
| P-7 | **Repo settings (owner clicks).** Website: the demo page. Topics: `claude-code`, `claude-code-plugin`, `kids-coding`, `parents`, `local-first`, `plan-first`. Social preview image: 1280×640 from the video's closing card. | The repo page shows the link and topics; a shared link shows the picture. |
| P-8 | **GitHub profile (owner clicks, 5 minutes).** Name (first name is enough), bio, picture, the demo page as website, pin the repo. No employer or work email. | The profile shows all five. |
| P-9 | **Profile README** (owner yes needed: it creates a public repo `paveliko123/paveliko123`). Draft in §8. | The profile shows the README. |

## 3. README changes

Keep all the content; rebuild the first screen and move reference material lower. The exact new text is shown
before → after at build time.

**New first screen, in order:** icon, title and badges (Mac badge per P-3) → the current one-line description
(it already follows D-26) → the "nothing is sent to the developer" line → a 15–25 s GIF → "Try the 2-minute demo"
and "Watch the 2½-minute walkthrough" (the video, A-5) → the 18+ note, unchanged.

**New sections:**
- **See it:** three screenshots: a kid's step screen, the *My apps* shelf with real apps (D-29, A-4), the top of a
  parent report (made-up kid).
- **FAQ:** What leaves my computer? · How much of my plan does it use? · Does it work on Mac? (untested) · Is my
  kid allowed to use Claude? (the existing 18+ wording) · Can I check the code before installing? (the existing
  "have your own Claude check it" block).
- **Contributing:** how to report a bug (the P-5 forms), what help is welcome (Mac testing, translations, ideas).

**Moved:** "How kids are kept safe" and "The parent report" move up, right after "What a kid does". "Forgot your
PIN", "Updating" and "Uninstalling" go under one collapsed **Help** heading.

**Dropped from the first draft:** the comparison table with hosted kids' tools. Its facts about other products
weren't checked, and it invites the "how is this different" debate the tone avoids.

## 4. Assets

| Asset | Source | Used in |
|---|---|---|
| Walkthrough video | The Devpost video as it is, https://youtu.be/DFgWYG4G0kE, 2:33 (A-5). | README, every post |
| GIF, 15–25 s, under 10 MB | Cut from a fresh screen recording of the real app: pick a look → a picture card → build progress → the app opens. ScreenToGif (free, Windows) — its download needs the owner's yes. | README top, Reddit |
| 3 screenshots | Real app, same window size. Real kids' apps allowed (D-29); each checked for a kid's name, school or other personal detail first (A-4). | README "See it", listings |
| Sample parent report | A report from a made-up kid's session (like the 2026-10-23 "My Coloring Book" demo data), saved as `docs/sample-report.html`. | README, people outreach |

## 5. Routes

Ranked by expected value per hour, lowest scrutiny first. Sources: three independent research runs on 2026-11-05
(Claude researcher, Codex Terra, Gemini Flash; D-30). Labels: **Verified** = a researcher opened the page;
**Researched** = a secondary source; **Estimate** = inference.

### 5.1 Listings (lasting, low scrutiny, about 15–30 minutes each)

1. **Anthropic's community plugin marketplace.** Submission form linked from
   https://github.com/anthropics/claude-plugins-community; reviewed with a security scan before approval
   (Verified). Being listed lets anyone install with Anthropic's own marketplace command. Submit after Phase 0.
   It may be refused over the 18+ rule (Estimate); a refusal costs only the 20 minutes.
2. **awesome-claude-code** (https://github.com/hesreallyhim/awesome-claude-code, ~57k stars). Rules: web issue form
   filed by a person, repo at least 14 days old with commits after day one or 100+ stars, one plain line
   (Verified). The repo qualifies (created 2026-10-07).
3. **Plugin directories:** mods4claude (https://mods4claude.com/submit) and ClaudePluginHub
   (https://www.claudepluginhub.com/). Both take a public repo with `.claude-plugin/plugin.json`, which this repo
   has; both also scan GitHub (Verified). Traffic unknown (Estimate: small but lasting).

### 5.2 Communities (one post each, after the listings)

4. **r/ClaudeCode weekly showcase thread.** Explicitly welcomes projects: what was built, how Claude Code was used,
   a link, a lesson (Verified). Medium scrutiny (Estimate). About 20 minutes.
5. **Nerdy Parents Club** (Cambridge, MA): parents building with kids and Claude Code; its newsletter invites
   member projects for a "project wall" (Verified). Low scrutiny, small friendly audience. About 10 minutes.
6. **r/ClaudeAI, showcase flair** (~1.3M members, Researched). Medium scrutiny: a similar dad-built kids' project
   drew friendly comments and an under-18 question (Verified, Codex). Optional, week 3, only if 4 and 5 went well.

### 5.3 People (two or three, D-25)

Write only after reading their recent posts yourself; one personal line from that reading. No lead showed a paid
plan in words; Claude Code use implies one (Estimate).

| Person | Evidence (Verified unless marked) | Route |
|---|---|---|
| Nate Aune, Nerdy Parents Club | Builds games with "Claude Code and Godot"; son 11; kit "designed for Claude Code" | Reply to the newsletter (same message as route 5) |
| Daniel Bower | July 2026 post: building a game with his 8-year-old in Claude Code | No invited contact found; skip unless one appears |
| Necati Demir | Nov 2025 post: his 8-year-old built 30 games with Claude Code | Email on his contact page, framed for professional enquiries: one short note at most |

Checked and dropped: Lars Moelleken (uses Google AI Studio, not Claude), "Mei Park" (wrong name; Diana Park's kid is
3), "Aidan Marcus" (blog real, surname and contact unconfirmed), Sergej Epp (LinkedIn only, teens), Peter Yang and
Maryrose Cook (kids about 7, no contact route; Yang's audience is product people), Felix Rieseberg (Anthropic
employee; the "parents send videos" quote unverified; no cold message).

### 5.4 Skip

- **Show HN:** the rules require something people can try, not a landing page (Verified); the browser demo is a
  mockup, and an HN thread about a teen's suspended Claude account shows the age issue dominating (Verified, Codex).
  High scrutiny. Revisit only after real families have used it.
- **Product Hunt:** hosted-product audience; a terminal install fits poorly (Estimate).
- **r/ChatGPTCoding self-promotion thread:** allowed, but a broad audience with no fit evidence (Verified, Codex).
- **A local club session (D-29):** outside the time budget.

## 6. Messages

- Under 120 words, one ask, feedback not promotion. Plain words; describe what a kid and a parent see.
- Only claims the README supports; no "kid-safe" (D-26). Real links only: repo, demo, video, sample report.
- One follow-up after 7 days at most.
- Never name someone's kids.

**Template** (people and the Nerdy Parents Club):

```text
Subject: A Claude Code plugin for parents, built for the kitchen-table sessions you write about

Hi <name>,

I read <specific post>: <one honest sentence about what stuck with you>.

I built a free, open-source Claude Code plugin for parents doing the same thing at home.
Your kid talks with a guide through six steps (idea, design, plan, build, ship) on your
laptop or a tablet, under your own Claude plan. Their sessions can't touch your files, a
separate Claude call checks what's said both ways, and you get a report after each app.

2½-minute walkthrough: https://youtu.be/DFgWYG4G0kE
Browser demo: https://paveliko123.github.io/build-with-me-at-home/
Repo: https://github.com/paveliko123/build-with-me-at-home

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
| Week 0 | Phase 0 (Claude builds P-1 to P-6; owner does P-7 to P-9, the GIF recording and screenshots) | 2–3 |
| Week 1 | Listings 1–3 | 1–2 |
| Week 2 | r/ClaudeCode showcase; Nerdy Parents Club; one person | 2 |
| Week 3 | Optional r/ClaudeAI; one more person; fix what testers hit | 2–3 |
| Week 4 | Review the numbers; keep, change or stop | 0.5 |

Every Friday, write down from Insights → Traffic (it keeps only 14 days): stars, unique visitors, top referrers,
installs reported, issues opened by others.

| Signal | Week 4 target (a guess, adjust after week 2) | If it misses |
|---|---|---|
| Stars | 25 | Many visitors but few stars: the first screen isn't working. |
| Referrers | Know which route sent people | Drop the weakest route. |
| Families who tried it | 2 | Ask one of them where the install stuck. |
| Issues from others | 1 | None means no installs, not no bugs. |

## 8. Profile README draft (P-9)

```markdown
Hi, I'm Pavel 👋

A parent who builds small open-source tools with Claude Code in my spare time.

**[Build With Me at Home](https://github.com/paveliko123/build-with-me-at-home)**: a Claude Code
plugin for parents. My kids plan and build their own small apps with an AI guide, on my computer
and my Claude account, while I supervise.
[Browser demo](https://paveliko123.github.io/build-with-me-at-home/) ·
[2½-minute walkthrough](https://youtu.be/DFgWYG4G0kE)

Issues and ideas are welcome.
```

Bio (160 characters max): "Parent and hobby builder. I make small open-source tools with Claude Code, like Build
With Me at Home for families."

## 9. Risks and open questions

- **The 18+ rule and the owner's own account.** Anthropic's consumer terms require users to be 18+, and its
  age-assurance help page says accounts may be restricted on signs of use by a minor (Verified, Codex:
  https://www.anthropic.com/legal/consumer-terms ;
  https://support.claude.com/en/articles/15171100-age-assurance-on-claude). The README already says letting kids
  use it is the parent's decision; it doesn't say a parent's account could be restricted. **Card D-33:** add that
  line to the README's 18+ note and the FAQ, or not.
- **Small audience:** a paid plan, the Claude Code command-line tool and a terminal. Fine for stars; don't judge
  success by mainstream reach.
- **Real examples skew younger:** most parents found build with kids of 5–7, not 8–13 (Verified, two researchers).
  The under-13 picture-card path matters more than the teen path in posts.
- **Similar tools exist** (KidCode, VibeBoy, a commercial kids' Claude Code camp; Researched). If asked, answer in
  one line: free, runs on your computer under your own plan, with a report after every app.
- **Support load:** the bug form (P-5) collects OS, Node.js version and plan up front.
- **Listing review:** Anthropic's marketplace may decline it; awesome-claude-code reviews are best effort.

## Change Log

- 2026-11-05: first draft from the owner's interview (D-24 to D-32) and three research runs.
