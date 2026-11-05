---
doc: progress
updated: 2026-10-29
---

# Progress

<!--
Two levels: a ## phase is a week or more; a - [ ] step is half a day to a day.
Marks: [x] done · [>] in progress · [ ] open · [!] blocked · [-] deferred (not counted).
The popup shows a started step with nothing running as paused (‖).
After a name, `·`-separated and all optional, in any order:
  what it covers · est 4h | 1d | 2w · est 30m · est 1.9% · started YYYY-MM-DD HH:MM · after S6, S4 B-3 · needs you: <what> · YYYY-MM-DD → YYYY-MM-DD · blocked: reason
est 4h | 1d | 2w is effort (an hour is an eighth of a day) and weights the bars and the forecast; est 30m is Claude's
working time and est 1.9% the share of the 5-hour window, both from the approved estimate table. started takes a
24-hour Eastern time after the date where it is known.
A step's name is plain words a reader understands, an ID first (APK7 Trip sharing and offline maps; a step with no ID of its own gets the next ST-n, never reused, and a D-, A- or F-number is a reference, not an ID); lists
of IDs go after it as a · part. Task items name a step by its ID or by words of its name in a [tag]. On the Task tools,
give tasks that run side by side the same blockedBy (the task they wait for); other tasks run in list order.
A checkbox indented two spaces under a step is one of its parts (a sub-step): list three to eight when the step starts
and tick each as it is done; the popup draws them as the running step's bar. A part that is one of these stages takes
its name, and a step lists only the stages it has: Draft, Review round 1 to Review round 3 (each with its fixes),
Your yes, Build live, Checks, Merge. Parts that can run on their own are separate steps (S8a, S8c) instead; finished
steps keep their names.
A step that comes after another names it: `after S6`, or `after S4 B-3` for part of a step. One that needs the owner
before it can start or go on says `needs you: <what>`; delete that field once the owner has approved it or done it.
A job that runs more than about 5 minutes writes its count to docs/plan/.live/<job>.json, or to the root-key folder in a project without docs/plan/ (Long jobs, ~/.claude/CLAUDE.md).
A phase is done when all its steps are; give a phase `started` and `est` for its day count and forecast.
A phase may say how its work is split across sessions as free text, for example `sessions: one per slice` (session-guide).
The plan-progress mod reads this file (the band and `/progress`); keep it current with the work.
-->

<!-- Released 0.1.2 (ca17c35, owner yes D-22, 2026-10-26). Build record: devpost\checklist.md. D-numbers in this repo are its own (D-1 to D-24; D-24 2026-11-05: judging over, freeze lifted), not the setup's. -->

## Judging · the GitHub repo stays as submitted
- [x] ST-1 Lift the GitHub freeze after judging · 2026-10-26 → 2026-11-05 · owner yes 2026-11-05 (D-24: judging over)
  - [x] Identity hook back, deny rules and the freeze section removed
  - [x] Local branch pushed and merged <!-- C:\APPS\LearnAIBasics-Local\.claude\CLAUDE.md (freeze, owner yes 2026-10-26, D-23); its pre-push hook -->

## Visibility · GitHub stars and real families
- [x] ST-5 Visibility plan · 2026-11-05 → 2026-11-05 · owner yes 2026-11-05 · draft: Downloads\build-with-me-visibility-plan.md
  - [x] Evaluate the draft against the repo
  - [x] Interview (D-24 to D-29)
  - [x] Check the Devpost video (A-5)
  - [x] Research people and places: Claude, Codex Terra, Gemini Flash (D-30)
  - [x] Draft the revised plan
  - [x] Review round 1 to Review round 3
  - [x] Owner cards D-24 to D-37
  - [x] Your yes
- [>] ST-6 Phase 0: repo ready for outreach (P-1 to P-6, P-11, D-36, D-37) · est 20m · est 3.2% · started 2026-11-05 13:44 · owner go-ahead 2026-11-05 13:44
  - [x] Builder brief
  - [x] Build live: hackathon removal, README, Mac badge, limitations, audit trim, forms, manifest
  - [x] Review round 1 (Opus reviewer: 9 minor, fixed in 6531b31)
  - [x] Checks: typecheck, guard tests, build, plugin validate --strict
  - [!] Your yes on the wording · needs you: read .tmp/phase0/wording.md, say yes
  - [ ] Merge, tag and release v0.1.2
- [>] ST-7 Your clicks: repo settings (P-7), profile (P-8), video sound (P-10) · started 2026-11-05 13:40
  - [x] P-8 Profile: picture, website link, pin (checked 2026-11-05)
  - [x] P-10 Video sound: one AI voiceover, no kids (owner 2026-11-05)
  - [x] P-7 Repo website link and six topics (topics set 2026-11-05, owner "set them")
  - [!] P-7 Social preview image · needs you: upload it (image made in ST-6)

## Checks of 0.1.2 on the real app
- [ ] ST-2 Your checks on the laptop: the guide's first spoken letter after a restart (D-9), a change list built by itself when a build ends (D-16), the app name pre-filled at Ship (D-14), signing in to Claude again with the button · needs you: try the four on the laptop <!-- devpost\checklist.md:351, :374, :425 -->

## Hardening · open security-audit items
- [ ] ST-3 Safety review round 2, priority 3: a second secret for the parent cookie, tablet setup as a POST, unlocking in a browser with a kid's pass, a trace on PIN reset, telemetry opt-outs for kids' runs, README disclosures, app emojis checked, starter ideas · released after ST-1 <!-- devpost\security-audit.md:54; devpost\spec.md:406 -->
- [ ] ST-4 Low and Info hardening · A4, C1, C2, C4, C5b, C7b, C7c, C8, I2, I3, I5, I7, I8 · released after ST-1 <!-- devpost\security-audit.md:55 -->

<!-- Ideas, not planned: sharing outside the home, a more natural voice, the behind-the-scenes learning session (devpost\prd.md:313-317); email or text alerts, a pause button, per-kid daily budgets (prd.md:319-322); the thumbnail's look (checklist.md:345-347). -->
