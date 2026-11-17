# Build Your AI Company (Mobile/Web Game)

**Tested:** 2026-11-17T09:05:00Z
**Submitted by:** Ilya
**Concept:** 2D town-builder where the town is an AI company — offices, data centres, cooling, power. Manage compute, cashflow and uptime. Random encounters replicate real live events. Choice-driven, "YouTube creator game" style. Free with ads, $5 to remove ads. "Game of Life"-like.

---

**Verdict**
Pivot required — as a business model, not as a concept. The idea is *already shipped*: at least five "AI data centre tycoon" games exist on itch.io, Google Play and the App Store as of November 2026, so the theme is not a moat, it's a race someone already finished. Ad-funded mobile for a niche tech theme is a coin-flip with brutal odds. The genuinely valuable asset here is the **real-event deck + ops depth**, and that is worth more as a premium PC/web game — or as a B2B training simulation sold to data-centre and cloud operators.

**Scorecard**
| Area | Score | Read |
|---|---:|---|
| Pain intensity | 2/5 | It's entertainment. Nobody is in pain; they are bored. Discretionary spend competes with free YouTube, TikTok and 10,000 free idle games. |
| Buyer clarity | 3/5 | The *player* is identifiable (25–45, tech-curious, tycoon/incremental fan, r/incremental_games, r/homelab). The *payer* is not: "watches ads" is not a buyer, and $5 ad-removal buyers are 1–2% of installs at best. |
| Urgency | 1/5 | Zero. No deadline, no loss, no forced behaviour change. Games are wishlist-and-forget purchases. |
| Differentiation | 2/5 | The exact concept — garages → GPU farms, power + cooling + uptime — is already live on three stores under three almost identical names. Theme is now table stakes, not an edge. |
| Speed to validate | 5/5 | A one-loop browser build is a week of work, and itch.io + Reddit give free, measurable distribution. This is the idea's one real strength: cheap to kill or confirm. |
| Founder advantage | 2/5 | No stated game-design, art, live-ops or UA experience. Mild edge from low local dev cost and genuine AI-infra interest — that's a hobby advantage, not a business one. |

**Core Assumption**
That the AI-infra theme plus a real-event deck makes an idle/tycoon loop fun enough to hold players past day 7 — because with no retention, there is no ad inventory and no $5 conversion, and with no differentiation, there is no cheap acquisition.

**Fatal Flaws**
| Risk | Severity | Why It Matters | Fast Test |
|---|---|---|---|
| The idea is already on the market — five times | 🔴 High | "AI Data Center Tycoon" (browser, itch.io), "Idle Data Center Tycoon" (Google Play), "Data Center Tycoon" (Play + dctycoon.net), "Compute Tycoon: Idle Simulator" (App Store), "Idle Datacenter" (itch.io leaderboard build). All do racks → GPUs → power/cooling → idle income. Shipping a sixth with the same hook means competing on art, retention and UA budget — the three things you don't have. | Play all five for 20 minutes each. Write down the two things each does badly. If you can't find two that *players complain about in reviews*, you have no wedge. |
| Ad-funded mobile economics on a niche theme | 🔴 High | Ballpark industry numbers (verify before betting): rewarded-ad ARPDAU ~$0.01–0.05 for a niche Western-skewing audience, CPI ~$0.30–1.50. You cannot buy a user for $0.50 and earn $0.03/day. Organic discovery on Play/App Store is effectively zero without UA or an existing audience. $5 ad-removal converts maybe 1–2% of installs — that's revenue for a game with 50k+ installs, not 500. | Spend $100 on two 15-second gameplay clips (TikTok/Reddit). Track install → D1 return. If D1 < 25% at ~$1 CPI, the model is dead before you write the second screen. |
| Scope is 10× the pitch | 🟡 Medium | "Multiple pages", real-time resource balancing, an event deck, art, save systems, mobile port, ad SDKs, IAP, balancing — that's 3–6 months solo, plus a permanent content treadmill to keep "real live events" current. Event decks are *content*, not retention; players finish them. | Build the single loop in 7 days: buy rack → assign workload → hit power/cooling wall → outage event → tick. If it isn't fun ugly, art won't save it. |

**Problem Reality**
- **Pain:** None — and that's fine, but it changes the metric. Entertainment is bought on *desire* and *retention*, not pain relief. The framework's usual pain tests don't apply; the honest test is "did 25% of players come back tomorrow without being reminded?"
- **Early adopter:** The AI/ops-curious tycoon player — r/incremental_games, r/homelab, r/DataHole, Hacker News, data-centre and SRE meme accounts. Small, loud, reachable, and *extremely* sensitive to fake-looking simulation. They will forgive bad art and punish wrong physics.
- **Vitamin or painkiller:** 🍬 Candy. Pure discretionary fun. That is not a flaw in entertainment — but it means distribution and retention replace pain as the moat, and both are things you'd have to build from zero.

**Competition**
- **Current behavior:** Free idle/tycoon games — the five AI/DC tycoons above, plus genre incumbents: AdVenture Capitalist, Idle Miner Tycoon, Kairosoft's Game Dev Story / Anime Studio Story, PewDiePie's Tuber Simulator, BitLife. On PC: Game Dev Tycoon, Startup Company. And the biggest competitor of all: watching a 20-minute Linus Tech Tips data-centre video for free.
- **Real enemy:** The player's thumb. "Meh, I'll play something else" — plus AI-theme fatigue, which is arriving fast. Every month you spend building is a month the novelty decays.
- **Differentiation needed:** Simulation *credibility* the incumbents lack — PUE, thermal throttling, spot pricing, capacity contracts, cascading outages — plus a news-driven event deck that makes each run feel current. Shareable failure moments ("I melted my DC chasing a benchmark") are the marketing; the game has to manufacture them.

**First 10 Customers** *(for a game, these are first 10 payers, not first 10 users)*
1. Ship a free browser slice and post it to r/incremental_games + r/homelab with one line: "I built an AI datacenter tycoon where the cooling bill is the boss fight. Roast my loop." Measure plays, D1 return, and comment sentiment — not upvotes.
2. Pre-sell a $5 "Founder Pack" on itch.io (name in credits + early builds) before the game is finished. Ten actual payments is the only signal that matters; ten "this looks cool" replies is not.
3. Recruit 10 playtesters from an SRE/DevOps Discord and watch them play 15 minutes in silence. Where they get confused is your roadmap; where they get bored is your death sentence.

**MVP**
- **Build:** One screen, one loop — buy rack → assign workload → power/cooling budget → one random event → cash/compute tick. Ugly 2D, browser only, no art.
- **Cut:** Multiple pages, meta-progression, art, ads, IAP, accounts, mobile port, leaderboards, the full event deck. Keep exactly one event type.
- **2-week test:** Live browser build, 100+ real plays from Reddit/HN, instrumented. Pass = D1 return ≥ 25% *and* ≥ 5 people unprompted asking "when's the next build?" Fail = D1 < 15% → the loop isn't fun; stop, don't add art.

**Pivot paths (ranked)**
| Path | What it is | Why it's better | Risk |
|---|---|---|---|
| **A. Premium PC/web sim** | $8–12 on Steam/itch.io, deeper ops simulation, news-driven event deck, no ads | Tycoon buyers pay upfront, no CPI math, no live-ops treadmill, Steam page is a real distribution channel. Small but real revenue; portfolio asset. | Steam visibility is its own lottery; needs 6+ months of depth to justify price. |
| **B. B2B serious game** | Training/sales-enablement simulation sold to data-centre operators, cloud and energy vendors (L&D budgets) | Real pain, real budgets, real ACV — teaches PUE tradeoffs, capacity planning, incident response. Procurement is slow but the money exists. | Sales cycle, credibility, and you'd need a design partner before building. |
| **C. Attention play** | Free web game as lead-gen for an AI-infra newsletter/community | Monetizes the audience, not the game; cheap to run; builds a distribution asset you can reuse | Needs writing cadence and an audience you don't have yet. |

**Recommendation**
Don't build the mobile ad-funded version. Build the 7-day ugly slice, put it in front of r/incremental_games, and decide on evidence. If the loop holds, go path A. If you want actual revenue rather than pocket money, take path B and find one data-centre operator willing to co-design — that conversation is also the fastest way to learn whether the simulation is credible.
