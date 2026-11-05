# Security

Build With Me runs on a family's own computer and handles kids' conversations, so security reports are very welcome.

## Reporting a problem

Please email **paveliko@gmail.com** with what you found and how to reproduce it. Please don't open a public issue for a security problem. This is a small open-source project kept up in spare time: you'll get an answer as soon as possible, usually within a week.

Only the latest version is supported.

## What's in scope

- The parent gate: the PIN, and the Parent area being reachable only on the laptop itself.
- Passes: one device per pass, time limits, and the spending caps per pass.
- What a kid's app can do: apps run in a sealed-off frame with no network access.
- The home network: what tablets and other devices on the Wi-Fi can reach (ports 4747 and 4748), and the home certificate.
- The sealed-off Claude Code runs: kids' text never reaching your own Claude settings, memory or files, and personal details being masked.
- Kids' data staying on the computer (see "Privacy" in the README).

## Out of scope

- Someone who already controls the computer or the parent's user account.
- The Claude models' own behavior, beyond the app's safety checks; report those to Anthropic.

## Known limitations

Build With Me is a hobby project and has not been professionally audited. These are the open items from its own reviews, in plain words, and what each one needs before it matters.

**Weaknesses**

- **The parent sign-in isn't tied to one port.** The browser sends it to other web pages on the same laptop's `localhost` address too. It matters only if another program is already running on the laptop and serving pages there.
- **Opening tablet setup uses a plain page address, not a button press.** It only works from an unlocked Parent area on the laptop, and it opens the setup window for 15 minutes. While that window is open, devices on the home network can see the setup page and the certificate.
- **Unlocking the Parent area in a browser that also holds a kid's pass doesn't keep the two apart.** It matters only if a kid uses that browser on the laptop while the Parent area is unlocked. The Parent area locks itself after 15 idle minutes.
- **Resetting the PIN leaves no record, and the PIN page names the reset command.** Resetting needs someone who can already run Claude Code as you on the laptop.
- **The emoji a kid can pick as an app's icon comes from the guide's reply and isn't run through the safety check.** It is only checked for being a single emoji.
- **A few of the guide's built-in starter ideas invite personal details** (a "page about me", a mood tracker, a family recipe card). The masking and the safety check still apply.

**How it handles data today**

- Kids' runs ignore your Claude telemetry opt-outs. The kids' Claude sessions run sealed off from your own Claude settings, so those settings don't carry over.
- The kid's nickname goes to the report writer (Claude) with the conversation, so the report can name them.
- The safety check runs inside the guide's own conversation by default (as a fork of the guide's call), not in a fresh conversation of its own.
- Prompt files that include the kids' approved plans are removed once they have gone unused for a week. The removal runs at the first Claude call after the server restarts, so they can stay longer if it isn't restarted.
- Updating the plugin restarts a running server at the next start, even in the middle of a build.
- Uninstalling the plugin while Build With Me is running doesn't stop the running server. Close its window first.
- The server's health page answers requests from any website, though it says only that the server is up and which build it is.

13 smaller hardening items are tracked in the audit.

The project's own security review, with what was fixed, is in [docs/design/security-audit.md](docs/design/security-audit.md).
