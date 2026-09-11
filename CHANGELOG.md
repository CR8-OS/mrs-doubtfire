# Changelog

## 2.0.0 — 2026-09-08

Genericized for any household, and made public.

Everything specific to one family moved out of the skills and into a config file
the user owns. The skills now carry doctrine only, which is what was worth
sharing in the first place.

### Added

- **`setup` skill.** Six-question onboarding that writes
  `config.md` in your connected folder and scaffolds the data folder. Infers where it
  can — reads mail to propose the school domain rather than asking for it — and
  ends by proving the connection works rather than by claiming it does.
- **`reference/week-ahead-artifact.md`.** Spec and template for a published
  weekly page: the coming seven days as a grid, plus what is closing, what is
  due, and what the school memo actually said. Built for the partner who was not
  part of the conversation. Opt-in through config, republished to a stable URL
  each week.
- **`reference/task-routing.md`.** Replaces the TickTick-specific routing file.
  Eight logical routes that map to whatever the household uses, and `none` as a
  first-class option where the brief reports instead of writing.
- **MIT license.**

### Changed

- **Config lives at `config.md` in your connected folder**, a fixed path, so skills can
  find it before they know anything else. It points at the data folder, which
  can be anywhere.
- **Multiple children supported** across school, medical, sizes, and social.
  Previously assumed one.
- **Public and private schools both handled.** Private adds re-enrollment
  contracts and tuition schedules; public adds district calendars and lottery or
  choice deadlines. Previously private only.
- **Single parents supported.** Anniversary and partner sections are gated on a
  partner existing rather than assumed.
- **Travel is party-size driven** rather than assuming three people, one airline
  status, and three specific airports.
- **Housing type drives household work.** Rental, co-op, condo, and house each
  constrain different things. Previously assumed a co-op.
- **Special education is off by default** and gated on config. Statutory
  mechanics kept, jurisdiction made a variable with an instruction to verify
  local timelines by search rather than asserting them.
- **Mail is connector-agnostic.** The flag-label pattern survives intact: a
  hand-applied label outranks every keyword guess, and is the escape hatch for
  everything the category searches miss.
- Cross-platform paths throughout. No more Windows drive letters.

### Removed

- All personal data: names, addresses, school, birthdates, drive letters, mail
  addresses, and every hardcoded task-manager project ID.
- `reference/ticktick-routing.md`, replaced by `task-routing.md`.
- `data/family-profile.md`, folded into the template.

### Kept deliberately

The parts that were expensive to learn, which is most of the value:

- Work backwards from the deadline, never forward from today
- Surface the second-order task
- Never invent a fact about the family, and say plainly when data is stale
- Say the uncomfortable part, with a number and a date
- Half days look like school days on a calendar
- Book the next appointment before leaving the current one
- Buy the next size up when the current one is within a half size of tight
- The 48-hour RSVP rule
- Book the sitter first, then decide what to do
- An empty mail search of the wrong inbox reads exactly like an all-clear

## 1.1.0 — 2026-08-28

Added the data-sources reference, the source registry pattern, and flagged-mail
handling. Wired the weekly brief to check hand-flagged mail before running any
keyword scan.

## 1.0.0 — 2026-08-27

Initial build. Router skill, five domain sub-skills, weekly brief, lead-time and
task-chain references, data templates.

Original idea by Sam Dolgin.
