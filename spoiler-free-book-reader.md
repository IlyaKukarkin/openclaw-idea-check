# Spoiler-Free Book Reader

**Tested:** 2026-11-15T09:05Z
**Submitted by:** Ilya
**Addendum:** [Monetization & pipeline](spoiler-free-book-reader-monetization.md)

---

**Original input:** "Book reader with characters list, facts, characters maybe portrait also. I was reading the book with many characters and I was forgetting some of them and what they have done in previous chapters. I was thinking to create a book reader app where I can tap on the character name and go to his profile. On profile I can see what I've already read, so no spoilers. First it can be the phone app and later I can actually do app for the e-readers."

---

## Verdict

**Pivot required.**

The pain is real — you felt it yourself, and that's the best signal you have. But you picked the wrong layer: the reader app is the one part you can't win, because your customers' books and habits are locked inside Kindle/Apple/Kobo, and Amazon's X-Ray already does the feature for free. Keep the insight, drop the reader: sell spoiler-safe character recall as a companion or plugin into one niche where the pain is acute.

## Scorecard

| Area | Score | Read |
|---|---:|---|
| Pain intensity | 3/5 | Real "who is this again?" moment — sharp for ensemble fantasy, long series, Russian classics. Episodic, interrupts flow, doesn't block it. |
| Buyer clarity | 2/5 | Easy to find the readers, hard to find the payer. Readers pay for books and store subscriptions, not tools around books. |
| Urgency | 2/5 | Workaround costs seconds: Google, wiki, skim back, X-Ray, or just push through. Nothing forces a switch today. |
| Differentiation | 2/5 | Kindle X-Ray, KOReader + LLM plugin, CharacterViz, Story Who already exist. Portraits are cosmetic, not a moat. |
| Speed to validate | 4/5 | You can hand-build three guides and post them in r/Fantasy this week. No code needed to learn the truth. |
| Founder advantage | 2/5 | You're the user, which helps discovery. No content rights, no distribution, no e-reader platform access. |

**Average: 2.5/5**

## Core Assumption

Readers will move their reading — and their library — into a third-party app to get spoiler-safe character recall.

The version actually worth testing: *readers will use a companion next to their current reader.* Same pain, no app switch.

## Fatal Flaws

| Risk | Severity | Why It Matters | Fast Test |
|---|---|---|---|
| Content access is closed | High | A third-party reader only opens DRM-free EPUBs. Kindle and Apple Books won't load, and Kobo's store won't either. The heavy readers with big libraries can't bring their books; the ones who can are already running KOReader/Calibre. | Ask 20 target readers what app they read in and whether their files are DRM-free. If under 30% could load a book in your app, the reader path is dead. |
| The feature already ships, free | High | Kindle X-Ray does exactly this: tap a character, get mentions and context capped at your position. KOReader has a free LLM plugin that profiles only text up to your page. CharacterViz and Story Who already publish bookmark-gated character guides. You'd be asking people to change readers for something they already have. | Give 10 readers a web prototype for one book. Track whether they actually do their reading inside it for a week. Opinions don't count. |
| It's a data-ops business, not a software business | Medium | Every book needs accurate, chapter-gated profiles. One hallucinated death or mis-gated spoiler = uninstall and a 1-star review, and trust doesn't come back. Authors and publishers won't hand you text, so coverage is either manual or piracy-shaped. | Hand-build guides for 3 books, log hours and errors, and have a real reader hunt for spoilers. If it's over ~4 hours per book, the catalog can't grow. |

## Problem Reality

- **Pain:** Real and specific — ensemble casts, week-long gaps between sessions, translated names that all sound alike, book 4 of a series after a year away. It's a genuine flow-breaker at the moment of confusion.
- **Early adopter:** Heavy genre readers (epic fantasy, LitRPG, 600+ page series), classics readers, people reading two or three books at once, and second-language readers.
- **Vitamin or painkiller:** Vitamin with painkiller moments. People seek a fix occasionally, but the free workaround is "good enough", and nobody pays monthly to upgrade "good enough" to "slightly better".

## Competition

- **Current behavior:** Google the name and risk a spoiler, skim back a chapter, ask a friend, search the Fandom wiki (spoiler roulette), tap X-Ray, or just keep reading confused.
- **Real enemy:** The reader app they already own, plus the habit of tolerating confusion. Amazon owns the store and the reading surface; you can't out-distribute the default.
- **Differentiation needed:** Not "character profiles" — trust. Verifiable spoiler-safety with citations and chapter gates, coverage of books people actually read (CharacterViz already owns public-domain classics), and zero-friction access: a plugin or companion, not an app switch.

## First 10 Customers

1. Pick one acute niche and live in it: Malazan/ASOIAF re-readers on r/Malazan and r/Fantasy, or Russian-language readers of long classics in Telegram/VK book chats — a market with genuinely hard names and no good local X-Ray equivalent.
2. Hand-build spoiler-free guides for the three books that niche complains about most, publish them as free web pages, and post them where those readers are. Track repeat visits to the same guide — that's the real need signal.
3. DM ten self-published series authors with 5+ books and offer a free spoiler-safe character page for their series. They own the audience, they care about reader retention, and some already pay for assets like this.

## MVP

- **Build:** A web companion, no reader UI. Pick a book, set your chapter, get spoiler-gated character cards with citations to the passage each fact comes from. Five books, deep, in one niche.
- **Cut:** The reader itself, the store and library, AI portraits (expensive, divisive, and readers already have their own mental image), e-reader apps, social features, and any pretence of all-book coverage.
- **2-week test:** Launch five curated books into one community. Measure 100+ visitors, 30% setting a chapter, 10 people returning for a second session, and 3 saying they'd pay or 1 actually paying. If people won't adopt a free companion, they will never switch readers.

## Pivot Path

1. **Companion/plugin, not a reader.** KOReader plugin or standalone web app for DRM-free and public-domain readers. Free distribution, no app-store fight, and it sits where the pain is.
2. **Author-side B2B.** Spoiler-safe character pages as a retention asset for self-published series authors — a buyer with money and an audience, not a browser with an opinion.
3. **One language, one genre.** Russian-language long-form fiction or LitRPG in a specific community: less competition, sharper pain, and a founder advantage a generic English app can't copy.

## Notes on the build order

Phone first, e-readers later sounds sensible but inverts the difficulty. Kindle is closed to third-party apps, Kobo has no app platform, and "e-reader app" in practice means Android e-ink devices (Boox, PocketBook) — a small, technical, sideloading audience. If that audience is the goal, a KOReader plugin reaches them on day one; a phone reader app reaches nobody who needs it.
