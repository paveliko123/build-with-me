# Week 1 listings (ST-9, plan §5.1)

Drafts for the owner's yes. The owner submits every form from their own account. Field labels are quoted as each
site shows them (researched 2026-11-05).

## 1. Anthropic plugin directory

Where: claude.ai/directory/manage → "Submit new" → "Plugin bundle" (needs a paid claude.ai plan and GitHub connected
on claude.ai). The listing text is read from `plugin.json` and the README, so there is nothing to write for it.

- "Repository": `https://github.com/paveliko123/build-with-me`
- "Plugin path (optional)": leave empty
- "Branch or tag (optional)": leave empty (main, so README fixes reach the listing)
- Press "Validate" first and stop there; the result decides whether a fix is needed (see Risks).

"Data handling" answers:

- Reads or stores personal data: **Yes.** Kids' first names or nicknames, their chats with the guide, the apps they
  build and the parent's reports, all stored only on the parent's computer.
- Sends data to services other than its connectors: **Yes.** Kids' chats go to Anthropic through the parent's own
  Claude Code. In Chrome and Edge, the guide's voice and read-aloud use the browser's online voices. Setup downloads
  packages from npm and a speech model from Hugging Face, with nothing about the family attached. Nothing goes to the
  developer; no analytics.
- How long data is kept: until the parent deletes it. Prompt files are removed after a week unused. The README's
  Uninstalling section removes everything.
- Intended for people under 18: **see card D-39.**
- Privacy link, if asked: `https://github.com/paveliko123/build-with-me#privacy`

"Compliance": confirm the contact email (paveliko@gmail.com) and read the four acknowledgements before ticking.
"Review and submit": keep "GitHub push webhook".

Risks:
- Two shipped files are over the directory's 256 KiB file limit: `app/dist/server/main.mjs` (523 KiB) and
  `app/dist/web/assets/index-DkPaYVGQ.js` (499 KiB). `app/assets/icon.ico` will be held for a reviewer. If Validate
  blocks on size, that becomes its own card (a rebuild and a new release).
- It may be refused over the 18+ rule (plan §5.1, Estimate).

## 2. awesome-claude-code

Where: https://github.com/hesreallyhim/awesome-claude-code → Issues → New issue → "Recommend a Resource". Signed in
as paveliko123; a person must submit it, one resource per issue.

- "Display Name": `Build With Me`
- "Category": `Documentation, Knowledge & Learning`
- "Link": `https://github.com/paveliko123/build-with-me`
- "Author Name": `paveliko123`
- "Author Link": `https://github.com/paveliko123`
- "Description":
  > A local Claude Code plugin for a parent to supervise their own kids as they plan and build small web apps, using timed passes, a plan-first guide and a parent report after each app.
- "Checklist": tick the five required boxes after checking each is true; leave the trap box unticked (read every
  label before ticking).

## 3. mods4claude

Where: https://mods4claude.com/submit

- "GitHub repository URL": `https://github.com/paveliko123/build-with-me`
- "Mod name (as in your plugin.json)": `build-with-me`
- "Where does it show up? (optional)": `Commands`
- "Short description (optional)": the same line as awesome-claude-code above
- "Your GitHub handle (optional)": `paveliko123`
- "Your X handle (optional)" and "Your email (optional)": leave empty
- Leave "Leave this empty" empty; tick the box that you wrote the mod; "Send for review".

## 4. ClaudePluginHub

https://www.claudepluginhub.com/ says a public repo with `.claude-plugin/plugin.json` plus "a URL submission" gets
listed, but no submit page was found (`/submit` is 404, and the site refused Claude's browser). Owner: look for a
"Submit" link on the site; if there is none, skip it. Listing on it isn't checked yet.
