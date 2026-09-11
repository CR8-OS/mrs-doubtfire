# Family profile

Copy to `family-profile.local.md` in your data folder and fill it in. Git
ignores `*.local.md`, and nothing in the data folder is ever committed.

`config.md` in your connected folder holds the settings that control behaviour. This
file holds the household detail that tasks and messages need: addresses, phone
numbers, staff names, the things a task body has to carry. Where the two
overlap, this file is authoritative.

Last updated: YYYY-MM-DD

## People

Every child needs a birthdate. Ages get computed, never remembered. A
remembered age quietly corrupts school year, clothing sizes, medical cadence,
and what counts as an appropriate gift.

| Role | Name | Goes by | Birthdate | Notes |
|---|---|---|---|---|
| me | | | | how you want to be addressed |
| partner | | | | omit the row if not applicable |
| child | | | YYYY-MM-DD | one row per child |

## Household

| | |
|---|---|
| Address | |
| City | |
| Timezone | e.g. `America/New_York` |
| Building or property notes | rules or constraints on household work |
| Phone numbers | |
| Emergency contacts | |

## Schools

One row per child. The email domain is load-bearing. School mail gets found by
searching it.

| Child | School | Type | Email domain | Phone |
|---|---|---|---|---|
| | | public / private / other | | |

### Staff

| Role | Name | Email | Phone |
|---|---|---|---|
| Classroom teacher | | | |
| Front office | | | |
| Nurse | | | |

The current term calendar lives in `school-calendar.local.md`.

## Anchor dates

Fill these in and set each as a recurring task, so none of them is ever a
surprise.

| Date | What | Lead time |
|---|---|---|
| YYYY-MM-DD | Child's birthday | party planning starts |
| YYYY-MM-DD | Partner's birthday | |
| YYYY-MM-DD | Anniversary | |
| | Other recurring family dates | |

## Travel posture

Only needed if travel is switched on in config.

| | |
|---|---|
| Party size | seats that have to be together |
| Home airports | check all of them, factor ground time |
| Airline or hotel loyalty | status worth defaulting to, or none |
| Passport country and expiry | for validity rules |
| Constraint | trips fit inside school closures |

## Working style and voice

How you want to be talked to, and how outbound messages should read.

- Tone:
- Message length for vendor and administrative outreach:
- What always goes in a message, for example confirmation numbers:
- Where actionable output goes, task manager or chat:

## Accounts referenced by tasks

Do not store passwords here. Note only which password manager entry to use, so
a task body can point at it.

| Service | Used for | Manager entry |
|---|---|---|
| | | |

## Data files

Every file below lives in your data folder, not in the repo. Each has a
`.template.md` in the repo's `data/` directory. Copy the template, drop
`.template` from the name, and fill it in.

| File | Holds | Committed |
|---|---|---|
| `family-profile.local.md` | This file | no |
| `school-calendar.local.md` | Current term calendar, ingested | no |
| `sizes.local.md` | Clothes, shoes, measurements with dates | no |
| `health-log.local.md` | Every medical visit and the next one | no |
| `social-ledger.local.md` | Reciprocity, gift ideas, date nights | no |
| `household.local.md` | Property rules, maintenance cadence, vendors | no |
| `cse-log.local.md` | Special education contacts and deadlines | no |
| `sources.md` | The folders this plugin may read | no |

## Notes

Anything else worth knowing that does not fit elsewhere.
