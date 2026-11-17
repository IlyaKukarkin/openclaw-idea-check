# Build Your AI Company (v2 — Decision-Layer Reframe)

**Tested:** 2026-11-17T09:41:00Z
**Submitted by:** Ilya
**Version:** v2. v1 (2026-11-17, 2.5/5) tested a data-centre town-builder. v2 reframes it as a **founder decision simulator**: pick which model to build, react to world events, spend on marketing, raise money, prepare the IPO. Satire-forward, "Game of Life" structure, free + ads, $5 ad-removal.

---

**Verdict**
Pivot required — but a much shorter pivot than v1. The reframe fixes the product: decisions about models, funding and IPO are a genuinely better game than placing cooling racks, and it matches the "Game of Life" structure you actually want. It does **not** fix differentiation, because "Game Dev Tycoon with AI instead of games" is the most obvious move in the genre and at least five teams made it in 2026 — two in the last two months. What's left is real but narrow: a **reputation-as-boss-fight mechanic**, satire good enough to be screenshotted by the industry it mocks, and premium web/PC pricing instead of ad-funded mobile.

**Scorecard**
| Area | Score | Read |
|---|---:|---|
| Pain intensity | 2/5 | Still entertainment, still discretionary. But the *desire* is stronger in v2: 2026's AI gold rush is a live cultural joke, and people enjoy playing the thing they're anxious about. |
| Buyer clarity | 3/5 | The player is now sharply identifiable: AI-curious professionals, founders, VCs, engineers — the crowd that reads AI news daily and shares screenshots. That's an addressable, high-sharing audience. The *payer* is still unresolved under the ad model. |
| Urgency | 1/5 | Zero. Nobody needs this today. Wishlist-and-forget. |
| Differentiation | 3/5 | Up from 2. The decision layer + satire voice is a real wedge — but five near-identical AI-founder sims shipped this year, and the loop is borrowed wholesale from Game Dev Tycoon. The wedge lives in *tone and one mechanic*, not in the theme. |
| Speed to validate | 5/5 | One run, 25 turns, 30 events, browser-only. A weekend to ugly, two weeks to testable. Cheapest kill-or-confirm in the whole database. |
| Founder advantage | 2/5 | Still no stated game-design, writing or UA track record. But if you can *write* — actual comedy, not puns — this becomes a 4/5 idea, because writing is the moat and it's the one thing an AI can't fake convincingly yet. |

**Core Assumption**
That the fun lives in **consequences, not the AI skin** — that players will replay to undo a choice they made ten turns earlier. If they don't, no theme, no joke deck and no Footbook-$100M moment saves it, because the loop is the product.

**Fatal Flaws**
| Risk | Severity | Why It Matters | Fast Test |
|---|---|---|---|
| Category is crowded and the loop is borrowed | 🔴 High | *Lab Tycoon: AI Startup Sim* (pick architecture, split compute between training and serving — App Store, ~1 week old), *AI Startup CEO* (iOS, Apr 2026), *GTM Simulator* (seed → IPO, browser), *Founder Sim* (funding → IPO, "AI-powered decisions"), *San Fran Sim* (garage → IPO, sarcastic narrator), *Startup Tycoon* (Play, Oct 2026, "no safe choices, only trade-offs"). Plus Game Dev Tycoon as the template everyone is copying, and a public r/tycoon thread from Jan 2026 proposing this exact game. A sixth entrant needs a reason to exist in one sentence. | Play the top three for 20 minutes. Find what players *complain about in reviews* — not what's missing, what's broken. If you can't name two complaints, you're building a twin, not a rival. |
| Writing is the product, and nobody budgets for it | 🔴 High | If you lean on satire, every screenshot is a writing test, and screenshots are your only distribution. "Funny events" delivered as a hand-written joke deck are consumed once and become a treadmill; mediocre jokes read as cheap parody ("Footbook") and the AI-industry audience you're targeting is the harshest audience on earth about exactly this. | Write 20 events. Show them to 20 people who work in or around AI. Count unsolicited laughs and asks to see more — not politeness, not "haha nice." If fewer than 6 produce a real laugh, the premise is weak and it's cheaper to learn now. |
| Ad-funded mobile still doesn't pay for this | 🟡 Medium | Unchanged from v1 and it's the quiet killer: niche Western audience, rewarded-ad ARPDAU in pennies, CPI in dollars. A $5 ad-removal is a 1–2% converter on a game that will realistically get hundreds to low thousands of installs. The math only works at a scale you have no path to. | Ship the free browser demo, then put a $5 pre-order on itch.io. Ten actual payments is the signal. Ten "this looks sick" replies is not. |

**Problem Reality**
- **Pain:** None — it's candy. But v2 has a better *desire* story: you're selling the fantasy of running the industry everyone is currently obsessed with and slightly suspicious of. That's a stronger pull than "run a data centre," and it's the same reason BitLife outsells serious life sims.
- **Early adopter:** AI-adjacent professionals — the people who read the model-release news the same day, argue about benchmarks, and have strong opinions about Sam Altman. They are on X, LinkedIn, Hacker News and r/tycoon. Small, loud, reachable, and they will share mockery of their own industry.
- **Vitamin or painkiller:** 🍬 Candy, unambiguously. Not a flaw for entertainment — but it means distribution and retention carry the whole business, and neither exists yet.

**Competition**
- **Current behavior:** Game Dev Tycoon / Kairosoft's Game Dev Story / Anime Studio Story for the loop; BitLife and Tuber Simulator for the choice-driven tone; San Fran Sim, GTM Simulator, Founder Sim, AI Startup CEO, Lab Tycoon, Startup Tycoon for the exact AI narrative. And for most of the audience, the actual alternative is *reading AI news and arguing on X* — which is free, social and endless.
- **Real enemy:** "I already played this." The genre's problem isn't scarcity, it's sameness — every one of those titles pitches the same "garage → IPO" arc with the same slippy metrics and the same po-faced tone. The enemy is the player's memory of the last one.
- **Differentiation needed:** One mechanic nobody else has (reputation), one voice nobody else can copy (writing), one distribution loop nobody else runs (screenshots of absurd outcomes in industry feeds). Theme alone is now a commodity.

**Design Spec — what makes this not a twin**
| Element | The move | Why it beats the field |
|---|---|---|
| **The Reputation Ledger** | A second currency alongside cash: legitimacy. Safety incidents, open-weights decisions, a model that says something unhinged during a demo, a copyright suit, a regulator labelling you "high-risk." It accrues interest, it can't be bought back with marketing, and it detonates at IPO. | Every competitor models money and users. None models the thing that actually kills AI companies in public. "Your reputation is the boss fight" is a claim no twin can make. |
| **Delayed consequences** | Every decision resolves 8–10 turns later. The player is always governed by a version of themselves who knew less. | The "one more turn" engine. Twins resolve choices instantly, which is why they feel like spreadsheets. |
| **State-driven satire** | Events generated from *your* state, not a fixed joke deck: you shipped an unaligned model → your safety lead gets poached → the regulator meeting goes badly → Footbook offers $100M for the person who caused it. | A joke deck is consumed once and then it's a treadmill. A generator compounds and never runs dry — and every screenshot is unique, which is the growth loop. |
| **Legibility layer** | Model choices expressed as personality, not architecture: "fast and cheap," "smart and slow," "uncensored and dangerous." Depth underneath, intuition on the surface. | "MoE vs dense" is unplayable for 99.9% of the market. Game Dev Tycoon works because "RPG" and "PlayStation" are already intuition. |

**First 10 Customers** *(for a game: first 10 payers, not first 10 players)*
1. Ship a 20-minute playable run to r/tycoon, r/incremental_games and a "Show HN" post with one honest line: *"I built a game where you run an AI lab and your own safety incidents come back to kill your IPO. Roast it."* Measure D1 return and screenshots posted by others, not upvotes.
2. Pre-sell a $5 itch.io "Founder Pack" (name in credits, early builds) before the game is finished. Ten payments = permission to keep building. Zero = the writing or the loop isn't there, and you learned it for free.
3. Sit with 10 AI-industry people, watch them play 15 minutes, and write down every moment they laugh and every moment they reach for their phone to screenshot. The laughs are the product; the screenshots are the marketing plan.

**MVP**
- **Build:** One run, 25 turns, five decision types (model, pricing, marketing, funding, hiring), 30 state-driven events, one reputation ledger, two endings (IPO or collapse). Browser only, ugly 2D, no art.
- **Cut:** Multiple pages, art, ads, IAP, mobile port, accounts, leaderboards, the full event library, the "$5 remove ads" tier.
- **2-week test:** 200+ real plays from Reddit/HN, instrumented. Pass = D1 ≥ 25% **and** ≥ 10 screenshots or shares posted by people who aren't you **and** ≥ 5 pre-orders. Fail on D1 < 15% → the loop is wrong; fail on shares → the writing is wrong. Those are different fixes, so measure them separately.

**Business model (revised)**
Free browser demo (the whole first run, no signup) → $8–12 premium web/PC for the full game with more decision branches and a live event pipeline. Ads and the $5 ad-removal are cut: they impose the mobile-scale problem on a product whose natural audience is desktop and whose natural asset is shareability.

**If it fails**
The salvageable piece is not the game — it's the **event engine**: a system that turns this week's AI news into a playable consequence. That has a second life as a B2B workshop tool (founder/VC trainings, "play the next 5 years of AI policy") or as a free public artefact that builds an audience for whatever you build next.
