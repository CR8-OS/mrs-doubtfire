# Mrs. Doubtfire

A Claude plugin that keeps track of the family logistics that fall through.

School deadlines. The dentist nobody has booked in fourteen months. Camp
registration that opens and closes in a week. Flights that should have been
booked two months ago and now cost four hundred dollars more. The birthday party
you RSVP'd to and forgot to buy a gift for.

None of it is hard. All of it is invisible until it is late.

Once a week this tells you what is coming, what is about to get expensive, and
what you are already behind on. It writes the actions into whatever task manager
you already use, and it can publish a page showing the week ahead that you can
send to your partner.

---

## What it actually does

**Works backwards from deadlines.** Nothing gets scheduled on the day it is due.
Every obligation gets a lead time, and the task lands on the date when acting is
still cheap. Camp registration goes on the calendar in December, not March.

**Surfaces the second task.** A party invitation is not one thing, it is four:
RSVP, gift, ride, and a calendar block so nothing else lands there. Most family
failures live in items two through four.

**Tells you the uncomfortable part.** If a registration window closed, it says
so. If fares are climbing, it says by how much. If you have been sitting on
something for three weeks, it names it.

**Never invents a fact about your family.** Sizes, dates, provider names, past
appointments — these come from your files or from you. If something is missing
or stale, it says so and asks. A confidently wrong shoe size is worse than no
shoe size, because you will act on it.

---

## Setup

Install the plugin, then say **"set up Mrs. Doubtfire"**.

Six questions, about two minutes:

1. Where your data should live (a synced folder — Drive, Dropbox, iCloud)
2. Who is in the household, and the kids' birthdates
3. Which school, and what address it emails from
4. What you use to track tasks — or nothing, which works fine
5. Which domains to track
6. When you want the weekly brief

That writes `~/.mrs-doubtfire/config.md`. It is plain markdown and you can edit
it by hand any time, which is the point — you should never have to ask an AI to
change a fact about your own family.

### Then do these three things

**Make a Gmail label called `doubtfire`**, plus a `doubtfire/done` sub-label.
Anything you label gets picked up on the next run and treated as deliberate. It
is how everything the keyword searches miss still gets caught. Thirty seconds,
and it is the single highest-leverage thing here.

**Feed it your school calendar.** Forward the PDF, paste the dates, whatever.
Closures, coverage gaps, trip windows, and all the deadline math depend on it.

**Fill in the last dentist and doctor visit.** Two dates. It cannot tell you
something is overdue until it knows when it last happened.

---

## The domains

Turn off anything you do not want. Off means silent.

| Domain | Covers |
|---|---|
| **School** | Calendar ingestion, forms, deadlines, conferences, re-enrollment |
| **Medical** | Appointment cadence, overdue checks, growth and clothing sizes |
| **Travel** | Trips, booking windows, passports, the school-calendar boundary |
| **Social** | Parties, RSVPs, gifts, reciprocity, date nights |
| **Household** | Camp and afterschool registration, seasonal work, maintenance |
| **Special education** | IEP, 504, evaluation timelines. Off by default. |

---

## What you need

**Required:** Claude, and a folder to keep data in.

**Strongly recommended:** a mail connector. Most of what this finds arrives by
email, and without it you are typing things in by hand.

**Optional but good:** a calendar connector, so it knows whether you are
actually free before proposing a date. A task manager, so commitments land
somewhere durable. Pick `none` and the brief simply reports instead of writing.

It degrades honestly. Anything not connected gets named, along with what that
costs you, rather than silently producing a thinner answer.

---

## Where your data lives

**Nothing personal is in this repo, and nothing personal is sent anywhere.**

Skill logic lives here, on GitHub, versioned. Your family's actual data lives in
the folder you chose during setup — school calendar, sizes, medical dates,
reciprocity ledger. Those files are yours, they stay on your machine and your
own cloud drive, and they are gitignored.

The one deliberate exception is the week-ahead page, which is a hosted artifact
so you can send it to your partner. It is opt-in, it is private until you share
it, and it carries schedule information only — no addresses, no phone numbers,
no medical detail beyond the fact of an appointment.

---

## Structure

```
skills/
  setup/              first-run onboarding, writes your config
  mrs-doubtfire/      the router and the operating doctrine
  school-ops/         calendar ingestion, deadlines, conferences, IEP
  health-growth/      medical cadence, sizes, seasonal buying
  travel-planner/     booking windows, passports, trip logistics
  social-calendar/    parties, gifts, reciprocity, date nights
  household-seasonal/ camp, afterschool, seasonal, maintenance
  weekly-brief/       the recurring scan and the week-ahead page

reference/
  lead-times.md            how far ahead everything has to happen
  task-chains.md           the second-order tasks
  task-routing.md          where commitments land, and what a good task looks like
  data-sources.md          reading files and mail safely
  week-ahead-artifact.md   the weekly page: spec and template

data/
  config.template.md       the household config
  *.template.md            scaffolds copied into your folder at setup
```

The two files worth reading if you want to understand the thing:
`reference/lead-times.md` and `reference/task-chains.md`. They are the accumulated
answer to "how far ahead does this actually need to happen", and they are useful
even if you never install this.

---

## Making it yours

Everything here is markdown. Open a skill and edit it.

The lead times are a starting point, not gospel — venue booking windows and camp
registration dates vary a lot by city, and if yours are different, change the
table. The task chains are the same: if your family has a step that always gets
missed, add it.

Pull requests welcome, particularly for lead times in other cities and school
systems, and for task managers not yet supported.

---

## A note on the name

Named after the film, affectionately. No affiliation with anyone who owns
anything related to it.

The character got the job done by being competent and slightly relentless rather
than by being nice about it, which is roughly the design brief.

---

MIT licensed. Use it, fork it, change it.
