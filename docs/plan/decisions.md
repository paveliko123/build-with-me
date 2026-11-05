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
  laptop or home network; corrected in review round 2: data-handling items are listed as such), without step-by-step detail; plus a line that it's a hobby project, not professionally audited.
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
- Gemini Flash research merged into the plan 2026-11-05: dev.to write-up, r/SideProject, one people lead (all Gemini only,
  labeled Researched).
- **D-35 Repo renamed to `build-with-me` (owner instruction 2026-11-05).** Display name "Build With Me" in the README,
  demo page, plugin manifest, setup skill, slash-command text and design docs. Not changed (owner: not worth it): the
  in-app screens, and the old demo address (now 404; the demo lives at paveliko123.github.io/build-with-me/). Internal
  IDs `build-with-me-home` (marketplace) and the tablet certificate name stay.
- A-6 Outreach names live in a git-ignored file, `docs/plan/private/outreach-people.md`, since the repo is public.
- A-7 Week 1 kept within A-1: the dev.to write-up moves to week 2, r/SideProject and people to week 3 (review round 1).
- A-8 SECURITY.md's known limitations list the eight ST-3 items one by one and the 13 low ST-4 items as one grouped line.
- A-9 The root `LICENSE` becomes plain MIT so GitHub shows "MIT"; Devpost's MIT notice stays in `app/skills/LICENSE`
  (next to the course skills it covers) and in the README credit line, which keeps D-32's credit.
- **D-33 Add one line to the README's 18+ note and the FAQ (owner yes 2026-11-05, option A):** "Anthropic may restrict
  accounts that show signs of use by someone under 18." Posts unchanged; Anthropic not asked first. Owner addition:
  all outreach is framed as "me helping my own kids"; each parent decides with their own evaluation and risk assessment.
- **D-34 Skip Show HN for now (owner yes 2026-11-05, option A; narrows D-25).** Revisit after real families have used
  it; then link the repo, not the mockup demo. Owner's view: the plugin is a structured approach, not free AI use for
  teens, which should calm objectors; the terms question is what would draw fire.
- **D-36 Trim the audit's open items (owner yes 2026-11-05, option B).** In `docs/design/security-audit.md`, the eight
  open medium items and the open low items get the same plain wording as SECURITY.md's known limitations: no file,
  line or step-by-step fix. Fixed items keep their detail. SECURITY.md keeps its link. Built in Phase 0 with P-4.
- **D-37 README heading "🛡️ How kids are kept safe" becomes "🛡️ Safety layers and their limits" (owner yes
  2026-11-05, option A; follows D-26).** Section heading and its contents-table link; the `#safety` anchor stays.
  Built in Phase 0 with P-2.
- **Owner yes 2026-11-05 on the whole visibility plan** (`docs/plan/visibility-plan.md`); Phase 0 is ST-6.
- P-10 done 2026-11-05: owner listened; the video has one AI voiceover and no kids' voices. P-8 checked done the same day.
- A-10 Phase 0 README uses the YouTube thumbnail in place of the GIF until the GIF exists; "See it" screenshots and the sample report wait for the assets step.
- A-11 The shipped build in app/dist stays the 0.1.2 build: an unread note in server/journey/ideaLibrary.json keeps its old devpost/ path rather than rebuilding for it.
- **D-38 Sample report = the real "My Coloring Book" report, renamed and trimmed (owner yes 2026-11-05, option A).** Kid renamed to a made-up name; full conversation removed; the "calms them down" lines and the "worth a chat" note reworded neutrally; the masked school flag kept; a top line says "Real report, names changed and shortened." Owner sees every changed line before it goes public. No GIF (video thumbnail stays). Screenshots of finished apps go ahead.
- **D-39 Anthropic directory form: answer "No" to "intended for people under 18" (owner yes 2026-11-05, option B).** Owner's
  reason: kids can't install or use it on their own; the parent is the subscriber, like a parent's Netflix account with a
  kids' profile. A note box, if any, says so (docs/plan/listings-week1.md).
- A-12 Directory listing icon: the existing 512 px app icon copied to .claude-plugin/icon.png (portal Validate 2026-11-05 warned "No icon"; the icon is fixed at first save or submit). Validate showed no size block (281 files, 9 MB, within limits); 20 policy holds are for a reviewer.
- A-13 plugin.json gets privacyPolicyUrl (README #privacy) and documentationUrl (README) for the directory listing; the portal had no privacy link and used the video as documentation. Terms of service left unset (MIT license). validate --strict passes.
- A-14 Directory "Listed on": Claude Code only; Cowork and the Claude apps unticked (it runs a local server for the home network; tested only in Claude Code).
- D-40 Compliance box 3 (no credential exfiltration, no code outside declared MCP servers): owner ticked all four boxes and went on, 2026-11-05 (option A: the plugin's own disclosed server is not hidden code; the 14 credential findings are keyword matches in comments, docs and an error pattern).
- A-15 Directory updates: "Scheduled check only" (about every 6 hours); no webhook secret in the repo settings. Can add push later.
- **D-41 Nerdy Parents Club: send a soft share, no project-wall ask (owner yes 2026-11-05, option B).** The wall and newsletter feature members who attend meetings; the owner's draft was ready, so no harm in sending a note that asks nothing.
