# Agent Instructions

This repo documents what's installed on this system, where, and why.

## Files
- `INVENTORY.md` — current state only. What exists, where, why.
- `CHANGELOG.md` — dated timeline of changes. Never mix the two.
- This folder structure is supposed to be in `./system-docs/`

## Rules
- Update `INVENTORY.md` whenever software is installed, changed, or removed.
- Add a dated entry to `CHANGELOG.md` for the same event.
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

## Formatting
- Dates are ISO 8601 (`YYYY-MM-DD`), used as `###` headings in `CHANGELOG.md`.
  Add new dated entries at the bottom, in chronological order.
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
