# How we work

Every piece of work in this organization, in every repository, new ones included, goes through one board: **Design to app** (organization project 5). If it isn't on the board, it isn't planned.

## One card per piece of work

- A feature, a piece of server work, or a small fix is **one issue**, however many commits it takes.
- Open it with one of the issue forms (**Feature**, **Server work**, **Small fix**). The form puts the card on the board for you.
- Every card has a **checklist**: one line per behaviour someone can test by using the app, such as "Turn PayPal off: a sign-up link opened afterwards no longer shows PayPal."
- Server work that a screen waits on gets its own card, linked both ways, so a feature waiting on the API shows as waiting.

## The columns

| Column | What it means | Who moves it |
|---|---|---|
| Designed | Ready to build, nobody has started. Ranked in the order the business needs it. | Opened by whoever writes the card |
| Scheduled | This week's work, assigned. From here the design does not change; new ideas become a new card. | The CTO, each Monday |
| In progress | Being built. | The developer |
| Needs Eric's call | Built differently from the design, or it overlaps something already built. | The developer, or whoever spots it |
| In staging | Merged into `staging`. Its checklist gets checked. | The developer |
| Accepted | Every checklist line ticked on staging, and Eric has signed it off. Lines that fail become new cards. | Eric only |

## Pull requests

Every pull request says which card it implements and what it does differently. The template has the lines:

- `Implements #<card>`
- **Built differently from the design**, and why, or "Nothing"
- **Not in this PR**: checklist lines left for later
- **Server work**: what it needs from the API, and whether that is live

You build it your way. The point is that the differences are visible before they ship, not discovered after.

## How the board is run

1. **The order changes on Mondays only.** Between Mondays a new card goes to the bottom of Designed unless it is marked urgent.
2. **A change to a card is always a comment**, not only an edit, so everyone watching it is told. A card in Scheduled or In progress never changes; the change becomes a follow-up card.
3. **Small fixes get their own card**, so a short fix to something already live does not wait behind a large feature.
4. **Each Monday we look at two numbers:** cards accepted that week and cards added. If added keeps beating accepted, we decide what not to build.

## Starting a new repository

Nothing to set up. This file, the pull request template and the issue forms apply to every repository in the organization automatically, unless the repository has its own. Open your first card with a form and it lands on the board.

## What does not change

You still build, review, merge and release the way the team does now. Branch and deployment rules stay with the CTO.
