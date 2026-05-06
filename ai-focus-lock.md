# AI Focus Lock

**Tested:** 2026-05-05T17:16:00Z
**Submitted by:** Ilya

---

# AI Focus Lock — Full Pressure Test

**Mode:** Full (deep) | **Tested:** 2026-05-05

---

**Verdict**
Pivot required. The refund retention hook is clever marketing but makes the business model unsound: you profit most from the users who fail most — the exact people who need your product. The privacy barrier for always-on screen monitoring is brutal, and the "build willpower by removing agency" premise fights human nature. This isn't a venture-scale problem wrapped in a viable business. It's a compelling feature looking for a different product.

---

**Scorecard**

| Area | Score | Read |
|---|---:|---|
| Pain intensity | 4/5 | Productivity/focus is real, painful, and recurring. People spend billions trying to solve it. |
| Buyer clarity | 4/5 | Clear ICP: knowledge workers, freelancers, remote employees, students who admit they procrastinate. |
| Urgency | 2/5 | Most people tolerate their productivity level. Urgency spikes before deadlines, then fades. Chronic — not acute. |
| Differentiation | 3/5 | Refund hook is novel. AI context + active blocking is more aggressive than Freedom/Cold Turkey. But execution gap from "idea that sounds different" to "actual user behaviour shift" is wide. |
| Speed to validate | 4/5 | Can test with a simple timer + screen monitoring + tab close script in days, not months. |
| Founder advantage | 1/5 | Not stated. This business needs deep domain credibility in attention science, OS-level engineering, and trust/security UX. If the founder isn't a known privacy-respecting maker, the trust barrier is fatal. |
| **Total** | **3.0/5** | |

---

**Core Assumption**

People will voluntarily install an app that watches everything they do and actively takes away control of their machine, and pay $30/month for the privilege — because the discomfort of being locked in is less painful than the discomfort of failing their own goals.

---

**Fatal Flaws**

| Risk | Severity | Why It Matters | Fast Test |
|---|---|---|---|
| Perverse revenue incentive | **Critical** | The people who need the app most (chronic procrastinators) are most likely to lose the $30 deposit. The product literally profits from user failure. This is _worse_ than a bad business model — it's a trust poison. If the model "works" financially, it means users are failing. If users succeed, revenue is $0. Either way, the business is fragile or morally awkward. | Talk to 10 people who bought Freedom or Cold Turkey and stopped using it. Ask: "If the app refunded you only when you stayed focused, would you trust their incentive or feel suspicious?" |
| Privacy + trust barrier | **High** | "An AI that watches your screen" is a marketing nightmare. Screenshots? Activity logs? What leaves the machine? Even if fully on-device, the _perceived_ surveillance is enough to reject installation. Apple opened the technical permissions; they did not open the social permission. Corporate IT policies will block this on work machines — your primary deployment target. | Pre-sell the concept without building. 100 cold DMs to remote workers: "Would you install an app that watches your screen to help you focus?" Record honest responses, not polite ones. |
| The willpower paradox | **High** | Active blocking apps have a fundamental problem: the user is fighting themselves. They'll close the app, use incognito, open on their phone, or simply disable permissions. Every workaround reduces trust in the product. Freedom and Cold Turkey solved this with nuclear options (can't uninstall during session); this still resulted in high churn. Your AI context makes it smarter but doesn't solve the underlying problem: the user wants to cheat and the app prevents that. | Survey past Freedom/Cold Turkey users: "Did you ever find ways around the blocks? What happened next?" |

---

**Problem Reality**

- **Pain:** Real but diffuse. "I can't focus" is a symptom of many root causes: poor task clarity, burnout, device addiction, anxiety, lack of sleep, bad environment. This app treats one surface cause (digital distraction) with mechanical force. For users whose focus problem is deeper (task anxiety, indecision), the app won't help and the refund mechanism will feel punitive.
- **Early adopter:** The person who has already bought a focus app before (Freedom, Opal, Forest), used it for 2 weeks, and stopped. They've proven they're willing to pay but haven't found a lasting solution. They're skeptical but desperate — the hardest customer to convert and the most likely to churn.
- **Vitamin or painkiller:** Light painkiller for deadline-driven crunch periods. Pure vitamin for daily productivity. The refund mechanic tries to create a painkiller structure (loss aversion on $30), but most users will mentally categorize this as a self-improvement tool, not a must-pay-to-avoid-suffering product.

---

**Competition**

- **Current behavior:** Post-it notes, Pomodoro timers, iPhone Screen Time, closing tabs manually, putting phone in another room, guilt cycles. The incumbent is habit — and it's free.
- **Direct competitors:** Freedom ($8.67/mo), Cold Turkey ($39 one-time), Opal ($14.99/mo), Focusmate (free + $5/mo), Forest ($4 one-time), RescueTime ($12/mo), Session ($7/mo). Most are cheaper, established, and have years of trust. None have a refund mechanic — which is a warning that the refund mechanic may be hard to monetize, not a gap in the market.
- **Real enemy:** Not another app. It's the 15-second gap between "I should focus" and "I'll just check one thing." No app can close that gap unless the user invites it in — and the user who invites it in already has the self-awareness to self-correct most of the time. The people who need it most are the least likely to install it.
- **Differentiation needed:** Convincing privacy engineering (fully on-device, open-source, auditable) + the refund hook + AI context that demonstrably beats dumb app-blocking. That's three hard things you have to get right simultaneously, each of which is a startup of its own.

---

**First 10 Customers**

These are not "purchase 10 subscriptions." These are people who install, use for 30 days, and either get a refund or don't. The _real_ first test is retention, not acquisition.

1. **5 past Freedom/Cold Turkey users from Reddit r/productivity, r/ADHD, r/digitalminimalism.** DM: "You bought a focus app before and stopped. I'm building something different — active AI monitoring + money-back guarantee. Can I show you the prototype for 15 minutes and hear why the last thing didn't stick?" No pitch. Just a conversation. This validates or kills the core assumption in week 1.

2. **3 remote workers in your personal network who openly struggle with focus** (they mention it in Slack, Twitter, or 1:1 conversations). Offer to sit with them for a day (remote screen share) and manually act as the "AI" — watch their screen and nudge them off distractions. If they can't tolerate a _human_ doing this, they won't tolerate an AI. If they find it valuable, you've validated the concept without writing code.

3. **2 freelancers who use the "deadline fear" method** to produce work. These are people who thrive on last-minute pressure. The question: would an automated lock-in reduce anxiety or amplify it? Watch them use the prototype. Their reaction tells you whether this is a productivity tool or a stress amplifier.

---

**MVP**

The riskiest assumption isn't whether the monitoring works technically. It's whether users will grant permission and tolerate the experience long enough to form a habit.

- **Build:** A minimal macOS app (Apple has opened the permissions) that:
  - User enters a session goal and duration (typed in, no AI yet)
  - App watches active window/tab
  - If user leaves the intended app for >30 seconds, a blocking overlay appears for 10 seconds before closing the distracting tab/app
  - Timer counts down; at end, a "Session complete" screen
  - After 5 sessions, auto-suggests turning on the $30 commitment
- **Cut:**
  - AI context understanding (emails vs. coding vs. writing — start with a manual goal entry)
  - Payment system (manual refund tracking)
  - Cross-device sync
  - Any analytics that leave the machine
  - Android/Windows — macOS only
- **2-week test:** Install on 5 friends' laptops. Watch them use it for 5 sessions each. Does any single user complete all 5 sessions without disabling the app? Do they ask for the app back after the test ends? If zero out of 5 complete the test, the core thesis (people will tolerate active blocking) is disproven. Pivot toward a lighter model: gentle nudges, not locks.

---

**Pivot paths (if core assumption fails)**

1. **Focus accountability, not control.** Pair users with an AI "accountability partner" that checks in via notification — no screen monitoring, no blocking. The $30 goes to a charity of their choice, not back to the company. Profits come from subscription ($7/mo) with the charity mechanic as the retention hook, not as the business model.

2. **B2B team focus management.** Sell to engineering managers who want productivity insights for their team (opt-in, transparent, anonymized). The surveillance is socially sanctioned because it's consensual team transparency. The $30 refund doesn't apply here; it's a straight SaaS seat.

3. **AI pomodoro coach.** No monitoring, no blocking. Just a smart timer that learns your work patterns, suggests break timing, and gives gentle nudges. The $30 is replaced with a yearly subscription ($49/yr). You compete with free timers by being smarter, not by being a jailer.

---

**Final word**

The refund hook is a genuinely creative retention mechanic. But it turns the revenue model into a trap: you align profit with user failure. On top of that, the privacy barrier, the willpower paradox, and the crowded market make this a very uphill battle — not impossible, but not the "obvious version" the pitch claims.

If you want to pursue this: validate the permission + tolerance question first, with a paper prototype (human-as-AI), before writing any code. If people can't tolerate a human watching them focus, the AI version is dead.
