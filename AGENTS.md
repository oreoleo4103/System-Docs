# Agent Instructions

This repo documents what's installed on this system, where, and why.

## Files
- `INVENTORY.md` — current state only. What exists, where, why.
- `CHANGELOG.md` — dated timeline of changes. Never mix the two.
- Location: `~/System-Docs/`.

## Scope
Document any change to the system an admin would need to know about to
rebuild or debug it:
- Packages and applications, regardless of install method (apt, snap,
  flatpak, pip, npm, cargo, binaries, AppImages, built from source).
- Services and scheduled jobs: systemd units, timers, cron jobs.
- Containers and VMs.
- Network config: firewall rules, open ports, VPNs, DNS, static IPs.
- System-level config changes: files under `/etc`, kernel parameters,
  drivers, users and groups, mounts.

Out of scope: project-local dependencies inside a repo's own
environment (venvs, `node_modules`), and changes to user dotfiles
that do not affect system behavior.

## Rules
- Never run git commands inside `~/System-Docs/`. The repo exists only
  to distribute this file and the folder structure; `INVENTORY.md` and
  `CHANGELOG.md` stay local. Git use elsewhere on the system is
  unaffected.
- Update `INVENTORY.md` whenever software is installed, changed, or removed.
- Add a dated entry to `CHANGELOG.md` for the same event.
- Read `INVENTORY.md` before installing anything. If it does not match
  the actual system, correct it and log the correction in
  `CHANGELOG.md`.
- Never record secrets: passwords, tokens, API keys, private keys,
  or credentials of any kind. Note only where they are stored.
- No timestamps in `INVENTORY.md`.
- No example commands anywhere in either file.
- No parenthetical asides in `INVENTORY.md`. If a reason matters, make it clear through the
  description itself or a reference to a related entry, not a `(...)` note. They are allowed however in `CHANGELOG.md` if they are kept brief and only made when necessary.
- Keep everything as compact as possible.
- Wrap lines in `INVENTORY.md` so none exceed 100 characters.
- `INVENTORY.md` is organized into topical sections, with each piece of
  software as a subsection. Never remove an existing section. Only add a new
  section when a piece of software genuinely does not fit any existing one —
  this should be a rare exception, not a fallback. Keep `INVENTORY.md` brief.
- If the `INVENTORY.md` and/or the `CHANGELOG.md` file is/are missing, create them.

## Formatting
- Dates are ISO 8601 (`YYYY-MM-DD`), used as `###` headings in
  `CHANGELOG.md`. One heading per date: if today's heading exists,
  append to it. Add new dates at the bottom, in chronological order.
- `INVENTORY.md` sections are `##` headings (System, Networking, Monitoring,
  Applications, Security, ...); each piece of software is a `###` subsection
  named after it, matching the package/service name.
- Backtick anything a reader would look up or type verbatim: service/unit
  names, file and directory paths, hostnames, domains, IP addresses, container
  names. Leave ports and version numbers as plain text.

## Voice
- `INVENTORY.md`: terse fragments, not full sentences — "Installed via the
  official apt repo." not "It was installed via the official apt repo."
  Present tense, describing current state only, never how it got that way.
- `CHANGELOG.md`: full sentences, past tense, one bullet per distinct action.
  Sub-steps of the same task can share a bullet, separated by commas or
  periods, rather than splitting into multiple bullets.
- No first person. No hedging, filler, or marketing language.
