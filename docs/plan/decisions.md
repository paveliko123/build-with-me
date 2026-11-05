# Decisions

D-1 to D-23 are in `devpost/checklist.md` (the hackathon build record). From D-24 on they are recorded here.

## Visibility plan (ST-5)

Draft under review: `Downloads\build-with-me-visibility-plan.md` (written in another chat, 2026-11-05).

- **D-24 Judging is over; the GitHub freeze is lifted (owner yes 2026-11-05).** Deny rules, the freeze
  note and the freeze push hook were removed and the identity push check restored. Launch prep no longer waits.
- **D-25 Visibility first (owner yes 2026-11-05, option A).** Show HN, Reddit, Claude Code plugin lists and one
  write-up; parent outreach shrinks to two or three people; real families are a bonus, not a target.
- A-1 Time budget: about 2–3 hours a week (owner OK 2026-11-05).
- A-2 overturned (owner 2026-11-05): the write-up stays, but no LinkedIn (owner's choice).
- **D-26 Keep the parent-tool framing in every post (owner yes 2026-11-05, option A).** Name the safety layers, never
  "kid-safe" or "guardrails" as a label. Owner's reason: downplay and surprise rather than overclaim; not selling
  anything, so credibility comes first.
- **D-27 Launch 0.1.2 as it is, tagged `v0.1.2`; open items listed as known limitations (owner yes 2026-11-05, option B).**
  No audit work before launch. Owner's reason: a free hobby plugin, not meant to be perfect.
- A-3 SECURITY.md describes the open ST-3 items in plain terms (what's affected, that it needs something already on the
  laptop or home network), without step-by-step detail; plus a line that it's a hobby project, not professionally audited.
- **D-28 Mac labeled untested; no separate clean-machine test (owner yes 2026-11-05, option A).** Badge
  "Windows · Mac untested", README text to match, the bug-report form asks for the OS. The 2026-10-23 install-video
  reinstall counts as the fresh-install check (Node.js was already present).
- **D-29 The kids' real apps may be shown (owner yes 2026-11-05, option B: "any/all of the built apps are ok to
  share").** No kids' names, faces or voices; no local club session.
- A-4 Before an app is shown, its words and pictures are checked for a kid's name, school or other personal detail.
- A-5 The Devpost video (https://youtu.be/DFgWYG4G0kE; local copy Downloads\BuildWithMe\Build With Me.mp4) is the
  plan's video as it is: 2:33 long, checked frame by frame 2026-11-05 (sound not checked). It shows the whole flow:
  pass, six steps, build, ship, parent home, report. No recut; the README links it. One slide (0:11) mentions the
  hackathon, which is fine as background.
- **D-30 Three independent researchers (owner instruction 2026-11-05):** the Claude researcher, Codex Terra
  (`gpt-6.1-terra`, live web search) and Gemini 3.8 Flash (`gemini-3.8-flash-high` through Antigravity's `agy`). The
  brief focuses on (1) bloggers and vloggers who clearly use a paid Claude plan and have kids of about 8–13, and
  (2) places to post that bring real interest without heavy scrutiny; few places, each worth the time.
- **D-31 Review round 1 on smaller models, as a trial (owner instruction 2026-11-05):** the Claude reviewer on Sonnet
  and Codex on Luna (`gpt-6-luna`), to see whether it saves usage. A one-off trial against the profile's "never the
  smallest Codex model"; the rule itself stays. Later rounds use the usual models.
- Owner wish 2026-11-05: strip the hackathon story (how and why it was built) from the repo where possible. Scope is
  card D-32. The MIT credit to Devpost's course skills stays (the license requires it).
- **D-32 Rename `devpost/` to `docs/design/` and remove the hackathon wording visitors see (owner yes 2026-11-05,
  option A).** README, demo page, SECURITY.md and code-comment paths; the required credit becomes one short line under
  Credits; the guide's internal name-mapping lines stay. Built with the README rewrite, in one pass.
- Owner yes 2026-11-05: start the rewrite now, at the ~12% job-total estimate, in peak hours.
- Owner yes 2026-11-05 ("you have access to my github - fix this"): public profile repo `paveliko123/paveliko123`
  created with the profile README (plan P-9). The owner set name and bio; picture and pin are the owner's clicks.
- Gemini Flash research merged into the plan 2026-11-05: dev.to write-up, r/SideProject, Khe Hy (all Gemini only,
  labeled Researched).
- **D-35 Repo renamed to `build-with-me` (owner instruction 2026-11-05).** Display name "Build With Me" in the README,
  demo page, plugin manifest, setup skill, slash-command text and design docs. Not changed (owner: not worth it): the
  in-app screens, and the old demo address (now 404; the demo lives at paveliko123.github.io/build-with-me/). Internal
  IDs `build-with-me-home` (marketplace) and the tablet certificate name stay.
- A-6 Outreach names live in a git-ignored file, `docs/plan/private/outreach-people.md`, since the repo is public.
