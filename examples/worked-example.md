# Worked example

A fictional project run through the skill, so you can see what comes out. Everything below is invented. Your plan will be built from your own answers.

## Intake (what the user said)

- **What:** a book called *The Four-Day Standup* on running small remote engineering teams. First-time author, Maya Okafor. Manuscript is done and edited.
- **For:** engineering managers at companies of 20 to 200 people.
- **Stage:** built, not launched. Publication date is 10 weeks away.
- **Has:** newsletter of 400 people, 1,200 LinkedIn followers, about 15 engineering leaders she knows personally, one friendly podcast host, a $1,500 budget, 6 hours a week, a Claude agent that can research and draft but cannot send email.
- **Success:** 1,000 copies sold in the first 90 days.
- **Tried:** a few LinkedIn posts, which got little response.
- **No-go:** no paid ads, no cold DMs to strangers.

## PLAN.md (condensed)

### Verdict
Almost ready. The book exists and the audience is clear, but there is no way to reach buyers directly beyond 400 people, no named first 100, and no launch date plan. Stage 1 (quiet build, 30 days), then a 10-day launch window, then sustain.

### Scorecard

| # | Check | Result | Evidence |
|---|-------|--------|----------|
| 1 | Job | Pass | Helps managers cut standup time and keep a team aligned; she has a before/after test from her own team |
| 2 | Position | Fix | Subtitle mixes management, agile and remote work. Pick one category |
| 3 | Audience | Fix | "Engineering managers" is named, but no list of the first 100 |
| 4 | Assets | Missing | No written inventory |
| 5 | List | Fix | 400 subscribers, no reason to join beyond her posts |
| 6 | Word of mouth | Missing | Moment not identified |
| 7 | Champions | Fix | 15 friends, none targeted for reach |
| 8 | Launch window | Missing | Date exists, no plan |
| 9 | Long game | Fix | No next piece of work planned |
| 10 | Packaging | Pass | Title and cover tested well with 5 managers |

Gating items: position (2), first 100 (3) and the list (5).

### Position (DRAFT)
- One sentence: *The Four-Day Standup* is a short practical guide that helps engineering managers at 20 to 200 person companies replace daily standups with a four-day rhythm their remote teams actually follow.
- Category: management book for engineering managers (not agile theory, not remote-work philosophy).

### First-100 spec
Sheet columns: name, role and company, why them, where found, warm path, status. Sources: Maya's 15 contacts, engineering leaders who comment on posts about standups, speakers at three engineering-management meetups, authors of the five most-read engineering-management newsletters.

### Timeline (Stage 1, days 1 to 30)

| Days | Move | Owner | Done when |
|------|------|-------|-----------|
| 1-2 | Write the one sentence, paragraph and page; draft the launch announcement | Maya, agent critiques | Maya approves all three |
| 3 | Call-to-arms form to the newsletter and her 15 contacts; build the asset sheet | Maya sends, agent drafts | Form live, sheet has at least 25 rows |
| 7 | First-100 sheet with sources and warm paths | Agent researches, Maya reviews | 100 rows, 40 with a warm path |
| 10 | Back-of-book and website sign-up for a free "standup audit" checklist | Maya | Sign-up live, tested |
| 14 | 10 conversations with target readers: would you read it, who else should I talk to | Maya | 10 held, notes logged |
| 20 | 10 tailored gifts for the least-besieged champions (engineering directors and newsletter authors, not famous names), plus early copies to the next 30 | Maya, agent drafts notes | Gifts sent, no ask attached |
| 25 | Record two podcast guest spots and write three articles from chapters | Maya | Banked, scheduled |
| 28 | Go/no-go gate | Maya | See below |

**Gate (defaults, change as needed):** 100-row sheet, at least 150 new list subscribers, 10 early readers committed to post a review in launch week, one-pager approved. If it fails, extend Stage 1 by two weeks.

### Launch window (days 31 to 40)
Day 31 announce to the list and post; days 31 to 33 podcast episodes and articles go live together; day 32 early readers post reviews; days 33 to 38 outreach to engineering newsletters and a small local meetup talk; day 40 thank-you note to everyone who helped, with the next chapter's sample.

### Three ideas to test
1. **Standup audit gift.** A free one-page audit that tells a manager how many hours their team loses to standups. Cheapest test: send it to 10 managers and ask what number they got.
2. **Newsletter swap.** Offer one newsletter author an exclusive excerpt for their readers in exchange for a recommendation.
3. **A stand.** "Most daily standups are a status meeting in disguise." Take a clear position in one article; it gives reporters and newsletters something to react to.

### Not doing
Paid ads (nothing is moving yet), cold DMs (her rule), a book trailer (low return for this audience), more LinkedIn posting for its own sake.

### Weekly scoreboard
Rows in the first-100 sheet, rows with warm paths, conversations held, new subscribers, gifts sent, early readers committed, articles banked.

### Decisions needed
- [ ] Which one category does the book sit in?
- [ ] Will she run a launch-week giveaway of the audit tool?
- [ ] Is the publication date fixed?

## AGENT_PROMPTS.md (condensed)

### Master prompt
You are helping Maya Okafor launch *The Four-Day Standup*, a short practical guide that helps engineering managers at 20 to 200 person companies replace daily standups with a four-day rhythm their remote teams follow. The book publishes in 10 weeks. Success is 1,000 copies in 90 days. We are in Stage 1 (quiet build, 30 days), then a 10-day launch window. Maya has a 400-person newsletter, 1,200 LinkedIn followers, about 15 engineering-leader contacts, 6 hours a week and a $1,500 budget. No paid ads and no cold messages to strangers.

Rules: never send, post, publish or pay for anything without Maya's explicit approval; only draft. Personalise everything from real research and cite the source for every fact about a person. Do not invent facts, quotes, reviews or numbers. Only add people to the list with consent. Keep `tracker.csv` with every contact, draft and status. Stop at the day-28 gate and report. Ask one question at a time if blocked.

### Workstream 3: First-100 research
**Goal:** a verified sheet of 100 engineering managers and leaders who are a good fit for the book.
**Inputs:** Maya's 15 contacts (`contacts.csv`), the three meetup speaker pages she names, and the five engineering-management newsletters she reads.
**Steps:** (1) read `contacts.csv`; (2) search the meetup speaker pages and newsletters for managers at companies of 20 to 200 people; (3) for each candidate record name, role, company, why them in one line, source URL and any warm path to Maya; (4) skip anyone you cannot verify; (5) flag the 40 best warm paths.
**Output:** `first100.csv`.
**Done when:** 100 verified rows, each with a source URL.
**Stop and ask if:** fewer than 60 candidates can be verified from the named sources.

### Workstream 5: Champions and gifts
**Goal:** a tailored no-ask gift idea and note for each of 10 champions.
**Inputs:** `first100.csv`, filtered to directors and newsletter authors with reach.
**Steps:** (1) choose 10 people least likely to be pitched by other authors; (2) for each, read their recent posts or articles; (3) propose one gift tied to something they care about (an early copy with a marked chapter, the audit run on their own published practice); (4) draft a three-sentence note with no request.
**Output:** `champions.md`.
**Done when:** 10 entries, each with a cited source for what they care about.
**Stop and ask if:** any gift costs more than $40.

Other prompts for this project follow the same shape: position pass, inventory and call to arms, list capture, content bank, press and partners, launch window, weekly report.
