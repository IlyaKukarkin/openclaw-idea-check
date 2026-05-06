# PenguinDiscount

**Tested:** 2026-05-05T17:33:00Z
**Submitted by:** Ilya

---

## Verdict
**Strong** — but only as a focused emerging-markets micro-SaaS, not a universal price tracker. The scraping data you already collected is the strongest signal in this evaluation: 100% success on Turkish sites is *real evidence*, not a guess. The valuation ceiling is low (niche tool, not a platform) and the subscription monetization is unproven, but the idea passes the basic smell test — real pain, real differentiation, no credible competitor serving Trendyol/N11/Hepsiburada users today.

---

## Scorecard
| Area | Score | Read |
|---|---:|---|
| Pain intensity | **4/5** | High inflation (Turkey ~40-80%) means prices shift frequently. The pain is real and recurrent. |
| Buyer clarity | **2/5** | Free user is clear (price-sensitive shopper), but who pays? eCPM in Turkey is ~$0.50-2, and subscription requires price-sensitive people to pay for a tool they use to *save* money. |
| Urgency | **3/5** | Inflation creates urgency to *buy now*, not to *track systematically*. The "notify me when it drops" use case is real but secondary to FOMO. |
| Differentiation | **4/5** | Genuine. Keepa, CamelCamelCamel, PriceGrabber are Amazon/US-only. No major tracker targets Trendyol, Hepsiburada, N11. Your scraping data proves the technical wedge exists. |
| Speed to validate | **4/5** | Can validate with a Telegram bot + manual price checks this week. No app store, no subscription system needed. |
| Founder advantage | **2/5** | The research (52 sites, detailed methodology) is a strong signal of execution ability. But we don't know: do you speak Turkish? Have connections in the target market? Know how people there discover apps? This matters a lot for an emerging-market play. |
| **Aggregate** | **3.2/5** | |

---

## Core Assumption
People in emerging markets (Turkey being the lead test case) frequently monitor prices on local e-commerce sites and will install a dedicated app to automate that monitoring — and a meaningful percentage (≥3-5%) will pay a monthly subscription to remove ads and get faster notifications.

---

## Fatal Flaws
| Risk | Severity | Why It Matters | Fast Test |
|---|---|---|---|
| **Scraping fragility** | **High** | Sites change HTML weekly. Add bot detection. Block IP ranges. You already hit 21% blocked with basic Playwright (Best Buy, Home Depot, Shopee). Trendyol and Hepsiburada work *today* — but if they add Cloudflare or Akamai, your entire value prop breaks overnight. | Monitor 5 Turkish products for 2 months. Track how many times the parser breaks and how long each fix takes. Log the maintenance tax. |
| **Ad-driven unit economics** | **High** | Turkey CPMs: banner ~$0.30-0.80, interstitial ~$2-5. A free user who tracks 3 products, opens the app twice a week, sees ~10 ad impressions/month = ~$0.01-0.05/user/month in ad revenue. If server/scraping costs exceed that, the free tier is a money-losing acquisition channel. | Model: monthly infra cost for 1,000 users (scraping 3,000 products daily). Compare to projected ad rev. If negative, the free tier needs stricter limits or no free tier at all. |
| **Subscription value prop** | **Medium** | Paying $2-3/month to remove ads from a price tracker is a tough sell in a market where $2-3 buys a meal. The faster-notification perk (subscribers go first in the daily batch) is a weak upgrade — it doesn't change the outcome, just the timing. | Run a landing page test: can you get 10 people to enter a credit card for a $2/month "unlimited track + no ads" plan? If conversion is <1%, rethink pricing or packaging. |
| **Referral link trust erosion** | **Medium** | Wrapping links in referral codes creates a conflict: user is alerted about a price drop, but the link goes through your referral. If the price is identical (or worse, marked up through the referral), users feel tricked. A single "I saw a lower price but your link showed higher" complaint can poison the app's reviews. | Only wrap links for platforms where referral links are transparent and don't inflate prices (e.g., Trendyol's affiliate program). For all others, send the direct link. |

---

## Problem Reality
- **Pain:** Prices change frequently in high-inflation economies. A phone that was 12,000 TRY last week is 13,500 TRY today. You want to buy it but also don't want to overpay by 1,500 TRY because you bought yesterday instead of waiting for tomorrow's drop.
- **Early adopter:** Urban tech-savvy 20-35 year old in Istanbul/Ankara/Izmir who already shops on Trendyol and Hepsiburada, is price-sensitive (inflation pinches everyone), uses Telegram/WhatsApp daily, and has experienced "I bought it and next week it was cheaper" regret.
- **Vitamin or painkiller:** **Vitamin**. Price tracking is a nice-to-have convenience, not a medical-level painkiller. Users won't lose sleep without it. The painkiller version would be "I missed a critical price drop and it cost me real money" — which exists for big-ticket items but not for daily purchases.

---

## Competition
- **Current behavior:** Users check prices manually — visit the product page, see the price, bookmark it, check back in a few days. Some use Telegram deal-sharing groups (e.g., "İndirim Avcıları"). Most do nothing systematic.
- **Real enemy:** **Habit and inertia.** Installing a dedicated app, granting notifications, entering URL links — all to avoid checking a product page for 30 seconds — is a high-friction ask.
- **Direct competitors:** Keepa (Amazon only), CamelCamelCamel (Amazon only), PriceRunner (weak on emerging markets), **akakce.com** (Turkish price comparison site with alerts — most direct competitor).
- **Indirect competitors:** Akakce's price alerts, Trendyol's own wishlist/stock notifications, Google Shopping price history (limited).
- **Genuine differentiation:** The emerging-market *focus* is your wedge. Akakce is a comparison site, not a personal tracker. No one offers "I want to track this specific N11 product and get a push notification when it drops 20%."

---

## First 10 Customers
1. **Turkish expat tech communities on Reddit** (r/Turkey, r/istanbul) — Post a manual offer: "I built a price tracker for Trendyol. Send me a product URL and I'll notify you when the price drops. No app needed, just Telegram." Pick 3 people who reply and do it manually. See if they act on the notification.
2. **Istanbul university Discord/Telegram groups** — Students are price-sensitive and tech-forward. Join student deal-sharing groups and offer manual tracking for their top 5 items. Get 3-5 students.
3. **Your own shopping** — Track 3 products you actually want to buy. When the price drops, do you buy? If you don't, why expect others to?

**No ads, no app store, no automation until you've manually tracked 10 products for 10 people and seen 3 buy.**

---

## MVP (Build in 2 Weeks)
- **Build:**
  - Telegram bot that accepts a product URL, stores it, and checks price daily using your existing parser.
  - Manual price-check script (already exists — adapted for Turkish sites).
  - Notification message: `"📉 Price dropped! [Product]: 12,500 → 10,200 TRY (-18%). Buy link →"`
  - SQLite database of tracked products + users.

- **Cut:**
  - No mobile app (Telegram is the UI).
  - No subscription/ad system (manual onboarding for first 10).
  - No referral link wrapping.
  - No notifications threshold logic (start with any drop = notify).
  - No daily batch processing (run scraper when you remember).

- **2-week test:**
  - Week 1: Telegram bot + scraper for Trendyol and Hepsiburada. Track 3 products yourself.
  - Week 2: Find 5 people. Manually add their URLs. Send notifications for 2 weeks. Track: opens → clicks → purchases.

---

## Pivot Options
- **Telegram bot only** — Drop the app entirely. Zero install friction, viral group sharing, Stripe subscriptions. The app adds distribution cost without distribution benefit.
- **Deal aggregator** — Instead of user-submitted tracking, crawl top 100 trending products daily and push "biggest price drops today" notifications. Lower effort, higher engagement.
- **Affiliate revenue only** — Unlimited free tracking, monetize solely through affiliate commissions. Aligns incentives with user.

---

## Original Input
Price tracking app called PenguinDiscount. Focus on emerging markets (Turkey) rather than US giants. Freemium model: free with ads (3 trackings), subscription for unlimited + no ads + faster notifications. Referral link wrapping, grouping by origin, smart notifications (>20% or >$10 change). User provided scraping research showing 100% success on Turkish sites (Trendyol, Hepsiburada, N11) and blocked on major US retailers (Best Buy, Home Depot).
