# Household config

**This file lives at `~/.mrs-doubtfire/config.md`** — your home directory, not
the repo. It is the first thing every skill reads and the only file that knows
anything about your actual family.

Windows: `C:\Users\<you>\.mrs-doubtfire\config.md`
Mac / Linux: `~/.mrs-doubtfire/config.md`

The `setup` skill writes this for you. Edit it by hand any time — it is plain
markdown on purpose, so you never need to ask Claude to change a fact about
your own household.

Anything marked **required** is needed for the basics to work. Everything else
degrades gracefully: a missing section means that feature stays quiet rather
than guessing.

---

## Data folder

**Required.** Where your family's actual data files live. Pick somewhere synced
so it survives a laptop change — Google Drive, Dropbox, iCloud, OneDrive.

```
data_folder: <absolute path>
```

Example (Windows, Google Drive): `G:\My Drive\Family\_Doubtfire`
Example (Mac, iCloud): `/Users/you/Library/Mobile Documents/com~apple~CloudDocs/Family/_Doubtfire`

Nothing in that folder is ever committed to git or sent anywhere.

---

## People

**Required.** Kids need a birthdate — ages get computed, never remembered.

| Role | Name | Birthdate | Notes |
|---|---|---|---|
| me | | | how you want to be addressed |
| partner | | | omit the row if not applicable |
| child | | YYYY-MM-DD | one row per child |

Anniversary: `YYYY-MM-DD`
Timezone: `America/New_York`
City: used for weather, venue lead times, and local registration rhythms

---

## Schools

One block per child. **The email domains matter most** — they are how school
mail gets found.

| Child | School | Type | Email domains |
|---|---|---|---|
| | | public / private / parochial / other | `school.org, district.gov` |

Type changes the deadline load. Private schools add re-enrollment contracts,
tuition schedules, and conference sign-ups that fill in hours. Public schools
add district calendars and lottery or choice deadlines.

---

## Mail

How school and family mail gets found.

```
connector: <which Gmail or mail connector is attached>
account: <the address that receives school mail>
flag_label: doubtfire
```

**The flag label is the escape hatch.** Create a label in Gmail with this name.
Anything you put it on gets picked up on the next run and treated as deliberate
— it outranks every keyword guess. Make a `<label>/done` sub-label too, and move
things there once handled.

Extra sender domains worth watching, beyond the school:

| Category | Domains or senders |
|---|---|
| medical | pediatrician, dentist, insurance |
| activities | camps, afterschool, sports, music |
| community | PTA, class parents, neighborhood lists |

---

## Task manager

Where commitments land. **Pick one.** If none, set `manager: none` and the brief
becomes read-only — it will tell you what to do and let you file it yourself.

```
manager: ticktick | todoist | reminders | asana | notion | none
```

Then map the routes. Names or IDs, whatever your tool uses. Leave a row blank to
send that category to the fallback.

| Route | Project / list |
|---|---|
| school | |
| medical | |
| travel | |
| social and gifts | |
| childcare and camp | |
| household | |
| shopping | |
| money | |
| fallback | |

```
tag: doubtfire
```

Every task gets this tag so you can filter or delete everything the skill made.

---

## Domains

Turn off what you do not want tracked. Off means genuinely silent, not quietly
running.

| Domain | On | Covers |
|---|---|---|
| school | yes | calendar, forms, deadlines, conferences |
| medical | yes | appointments, cadence, growth and sizes |
| travel | yes | trips, booking windows, passports |
| social | yes | parties, RSVPs, gifts, date nights |
| household | yes | camp, afterschool, seasonal, maintenance |
| special_ed | no | IEP / 504 / evaluation timelines |

---

## Travel posture

Only read when `travel` is on.

```
home_airports: <e.g. JFK, LGA, EWR>
party_size: <number flying together>
airline_loyalty: <status, or none>
passport_country: <for validity rules>
```

Party size matters more than people expect: award and cheap-fare inventory is
per-seat, and four seats together vanish well before one does.

---

## Weekly brief

```
day: Sunday
time: 08:00
artifact: yes
```

`artifact: yes` publishes a week-ahead page you can send to your partner.
`artifact: no` keeps the brief in chat only.

Sections, in order. Drop any you do not want.

| Section | On | What it holds |
|---|---|---|
| this_week | yes | the next 14 days, tactically |
| act_now | yes | booking windows crossing this week |
| slipping | yes | overdue by cadence, stated bluntly |
| decisions | yes | things needing a conversation, not a task |
| created | yes | what got written to the task manager |

```
max_findings: 8
```

More than eight and nothing gets done.

---

## Voice

How you want to be talked to.

```
style: concise and direct, no hedging
```

The default is short. If you would rather have warmth and context, say so here
and it will be respected.
