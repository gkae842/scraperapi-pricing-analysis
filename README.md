# ScraperAPI Plans Explained: Which Tier Actually Fits Your Scraping Needs — Credits, Pricing, Concurrency, and the Hidden Cost Math Demystified (Includes Full Plan Comparison Table and Discount Tips)

You googled "scraperapi plans" because you want a straight answer. Not a glossy overview with stock photos of people typing. You want to know: which plan should I actually pay for, and what am I genuinely getting?

Fair question. Let's get into it.

---

## What ScraperAPI Is (and Who It's Actually For)

ScraperAPI is a web scraping API that does the unglamorous plumbing work for you: rotating proxies across 40 million+ IPs in 50+ countries, handling CAPTCHAs, rendering JavaScript pages with a headless browser, and retrying failed requests automatically. You fire off an API call with a URL. It hands you back clean HTML or parsed JSON. That's the core deal.

It's been around since 2018, processes over 36 billion requests a month, and counts Deloitte, Sony, and Alibaba among its customers. It's genuinely one of the most recommended starting points in the scraping API space — not because it's always the cheapest, but because it's well-documented, straightforward to integrate, and reliable on the sites that matter most to most developers (Amazon, Google, Zillow, standard e-commerce pages).

If you're a developer building a data pipeline and need to scrape at scale without managing your own proxy infrastructure, ScraperAPI makes that easier. If you're a non-technical user looking to grab some product data into a spreadsheet without writing code — ScraperAPI probably isn't the right tool for you.

With that framing out of the way, let's talk about the plans.

---

## The Credit System: The Thing You Need to Understand Before Anything Else

Every ScraperAPI plan gives you a monthly bucket of **API credits**. Every request you make costs some number of those credits — and this is where people get tripped up, because it's almost never just 1 credit per request.

The actual cost per request depends on two things:

**1. The domain you're scraping:**

| Domain Type | Credits Per Request | Examples |
|---|---|---|
| Normal pages | 1 | Blogs, news sites, basic HTML |
| E-commerce | 5 | Amazon, eBay, Walmart |
| Search engines (SERP) | 25 | Google, Bing (all subdomains) |
| Social media | 30 | LinkedIn |

**2. The parameters you use:**

| Parameter | Extra Credits |
|---|---|
| `render=true` (JS rendering) | +10 |
| `screenshot=true` | +10 |
| `premium=true` | +10 |
| `ultra_premium=true` | +30 |
| `premium=true` + `render=true` (combined) | +25 total (not +20) |
| `ultra_premium=true` + `render=true` (combined) | +75 total (not +40) |
| Cloudflare / Datadome / PerimeterX bypass (auto) | +10 each |

Notice the last two rows in that second table. Combining `premium` and `render` costs 25 extra credits, not 20 — the combination is priced at a premium over the sum of its parts. Same story with ultra-premium plus render: 75 extra credits, not 40. This non-linear stacking catches a lot of people off guard.

On the bright side: **ScraperAPI only charges for successful requests.** A 200 or 404 response burns credits; anything else doesn't. So you're paying for data it actually delivered, not its own infrastructure failures.

One useful tool before you start any job: ScraperAPI's dashboard has a **Domain Cost Estimator** at `api.scraperapi.com/account/urlcost` — plug in your target URL and the parameters you plan to use, and it tells you exactly how many credits that request will cost. Use it. It saves a lot of surprise math later.

---

## All ScraperAPI Plans: Full Comparison Table

Here's the complete lineup as of the latest pricing page. All paid plans include: JavaScript rendering, premium proxy rotation, geotargeting (scope varies by tier), CAPTCHA/anti-bot bypass, automatic retries, custom sessions, custom headers, JSON auto-parsing, unlimited bandwidth, and a 99.9% uptime guarantee.

| Plan | Monthly Price | Annual Price (10% off) | API Credits/Month | Concurrent Threads | Geotargeting | Pay-as-You-Go | Purchase |
|---|---|---|---|---|---|---|---|
| **Free** | $0 | — | 1,000 (ongoing) + 5,000 trial (7 days) | 5 | Limited | ✗ |  [Start for free — no card required](https://www.scraperapi.com/?fp_ref=coupons) |
| **Hobby** | $49/mo | $44.10/mo | 100,000 | 20 | US & EU only | ✗ |  [Get the Hobby Plan](https://www.scraperapi.com/?fp_ref=coupons) |
| **Startup** | $149/mo | $134.10/mo | 1,000,000 | 50 | US & EU only | ✗ |  [Get the Startup Plan](https://www.scraperapi.com/?fp_ref=coupons) |
| **Business** | $299/mo | $269.10/mo | 3,000,000 | 100 | Global (50+ countries) | ✗ |  [Get the Business Plan](https://www.scraperapi.com/?fp_ref=coupons) |
| **Scaling** ⭐ Most Popular | $475/mo | $427.50/mo | 5,000,000 | 200 | Global | ✓ |  [Get the Scaling Plan](https://www.scraperapi.com/?fp_ref=coupons) |
| **Professional** | $975/mo | $877.50/mo | 10,500,000 | 300 | Global | ✓ |  [Get the Professional Plan](https://www.scraperapi.com/?fp_ref=coupons) |
| **Advanced** | $1,975/mo | $1,777.50/mo | 21,500,000 | 500 | Global | ✓ |  [Get the Advanced Plan](https://www.scraperapi.com/?fp_ref=coupons) |
| **Enterprise** | Custom | Custom | 22,000,000+ | 500+ | Global | ✓ |  [Contact Sales for Enterprise](https://www.scraperapi.com/?fp_ref=coupons) |

**A few things that aren't obvious from the table alone:**

- **Geotargeting is gated.** Hobby and Startup are limited to US and EU proxies only. If your project requires country-level targeting anywhere else — say, Japan, Brazil, or Australia — you need Business or higher.
- **Pay-as-you-go kicks in at Scaling.** On Hobby, Startup, and Business, exhausting your credits mid-cycle means you're cut off until renewal. Starting at Scaling ($475/mo), you can keep running via PAYG at a fixed rate.
- **Credits don't roll over.** Unused credits reset each billing cycle. There's no accumulation.
- **Unlimited analytics history** starts at Business. Hobby and Startup cap your dashboard history at 30 days.
- **Annual billing saves 10%** across all paid plans — no coupon code needed, it's applied automatically when you select yearly billing.

There's also an **Education Plan** for researchers: a one-time $10 package that gives you 50,000 scraping credits valid for 24 months, with 25 concurrent connections. This is specifically for university researchers, NGOs, or public bodies working on projects with positive social impact. If that's you, it's worth checking eligibility. 👉 [Learn about the Education Plan](https://www.scraperapi.com/?fp_ref=coupons)

---

## What You're Actually Getting Per Plan (Real Talk Edition)

The numbers in a table are one thing. What those numbers mean in practice is another.

**Free Plan / 7-Day Trial**

The free plan (1,000 credits/month) is genuinely useful for testing the API against a handful of pages or verifying integration. The 7-day trial bumps you to 5,000 credits — enough to run real test jobs against your actual targets. No credit card required. This is worth starting with before paying anything, because it lets you calibrate your real credit burn rate with the exact domains and parameters you'll use. 👉 [Start the free trial here](https://www.scraperapi.com/?fp_ref=coupons)

**Hobby ($49/mo) — For Side Projects and Prototypes**

100,000 credits sounds like a lot. For plain, unprotected HTML pages (1 credit each), it's 100,000 actual requests — plenty for a personal project checking competitor prices on a handful of products or monitoring a small set of pages. But once Amazon enters the picture (5 credits/request), you're down to 20,000 requests. Add JavaScript rendering (+10), and a single Amazon request costs 15 credits — that's 6,666 requests total. Know your multipliers before you pick this plan.

Good for: personal projects, prototypes, lightweight monitoring, learning the API.

Not great for: production workloads, non-US/EU geotargeting, any heavy Amazon or Google scraping at volume.

**Startup ($149/mo) — For Small Teams and Consistent Volume**

1,000,000 credits with 50 concurrent threads is a meaningful jump. This is the tier where you start running real production workloads — a small SaaS with a scraping backend, an agency running jobs for a handful of clients, or a solo developer doing serious data collection. Still limited to US/EU geotargeting, which matters if your clients or data needs are global.

Good for: consistent scraping pipelines at moderate scale, small SaaS products, solo developers doing production-grade work.

**Business ($299/mo) — Where Global Geotargeting Unlocks**

The Business plan is where things open up. Global geotargeting across 50+ countries means you can target-proxy by country-code for real international projects. 3,000,000 credits with 100 concurrent threads handles serious parallel workloads. Unlimited analytics history in the dashboard replaces the 30-day cap. This is the first tier that genuinely serves production infrastructure other parts of a business depend on.

Good for: international data collection, production pipelines with concurrency requirements, teams needing full dashboard history.

**Scaling ($475/mo) — The "Don't Get Cut Off" Plan**

This is ScraperAPI's most popular plan for a reason. 5,000,000 credits and 200 concurrent threads cover a wide range of high-volume use cases. But the differentiating feature is pay-as-you-go overflow — if you exhaust your monthly credits, you can keep going at a predictable fixed rate rather than hitting a hard wall. For any workflow where going dark mid-month is unacceptable, this changes the calculus significantly. You can even set a monthly spending cap on PAYG usage so there are no surprise bills.

Good for: high-volume scraping, any use case where continuity mid-cycle matters, scaling operations.

**Professional ($975/mo) and Advanced ($1,975/mo) — For Serious Infrastructure**

At this level you're talking about 10.5 million and 21.5 million credits respectively, with 300 and 500 concurrent threads. Both include pay-as-you-go. These tiers make sense for large-scale data operations — think enterprise-grade e-commerce price monitoring, large SERP tracking platforms, or AI training data pipelines.

**Enterprise (Custom Pricing)**

Everything above Advanced, built to spec. Custom credits, custom concurrency, custom pricing negotiated directly with the sales team. If you're running tens of millions of requests a month and want dedicated support and SLA guarantees, this is the tier for that conversation.

---

## The Real Cost-Per-Request Math (Before You Commit)

Raw plan prices don't tell the full story. Here's what you're paying per 1,000 requests at each tier across different use cases:

| Plan | Standard (1 credit) | Amazon (5 credits) | Google SERP (25 credits) | Amazon + JS (15 credits) |
|---|---|---|---|---|
| **Hobby ($49)** | $0.49 | $2.45 | $12.25 | $7.35 |
| **Startup ($149)** | $0.15 | $0.75 | $3.73 | $2.24 |
| **Business ($299)** | $0.10 | $0.50 | $2.49 | $1.50 |
| **Scaling ($475)** | $0.10 | $0.48 | $2.38 | $1.43 |
| **Professional ($975)** | ~$0.09 | ~$0.46 | ~$2.32 | ~$1.39 |

The unit economics improve meaningfully from Hobby to Startup, and again from Startup to Business. Above Business, the gains are more incremental — the jump from Hobby to Startup is where the biggest per-credit cost improvement happens.

---

## What ScraperAPI Does Particularly Well

ScraperAPI's performance isn't uniform across all websites, and that's worth understanding before choosing a plan.

**Strong performers:**
- **Amazon** — 98% success rate in independent benchmarks, with structured data endpoints returning 18+ fields (price, ratings, BSR, variants, images, seller info) in clean parsed JSON
- **Zillow** — 100% success rate in third-party testing, near the top of the industry for real estate data
- **Etsy** — 99% success rate
- **Google SERPs** — structured endpoints covering organic results, Shopping, Maps, News, Jobs
- **Walmart, eBay** — high reliability with structured data endpoints available

**Where it struggles:**
- **Instagram, Twitter/X, Booking.com** — 0% success rate in independent benchmarks. Not a limitation of the plan you pick; these sites are effectively off the table regardless of tier.
- **Login-required sites** — ScraperAPI explicitly does not support scraping behind authentication walls. The `session_number` parameter maintains the same IP across requests but cannot handle form fills or 2FA.
- **Frequently rotating anti-bot systems** — Success rates vary more on sites that aggressively change their protection measures.

One practical note: ScraperAPI applies a **10-minute forced result cache** on difficult targets. If you're scraping time-sensitive data — live pricing, inventory levels — you may get results that are up to 10 minutes stale. Worth factoring in if real-time accuracy matters to your use case.

---

## Is There a Discount? Yes — Here's How It Actually Works

The cleanest, most reliable discount ScraperAPI offers is **annual billing: 10% off across all paid plans**, applied automatically when you switch from monthly to yearly. No code, no expiration date.

For Hobby that's $44.10/mo instead of $49 — saving ~$59/year.
For Business it drops from $299 to $269.10/mo — saving ~$359/year.
For Scaling it goes from $475 to $427.50/mo — saving ~$570/year.

Beyond that, occasional promotional codes circulate through partner and affiliate channels. The most reliable place to catch an active offer is signing up through a current promotional link. 👉 [Check the latest ScraperAPI offer and start free](https://www.scraperapi.com/?fp_ref=coupons)

---

## What Real Users Say

ScraperAPI sits at **4.5/5 on Trustpilot** (42+ reviews), **4.4/5 on G2**, and **4.6/5 on Capterra** with a 4.9/5 for Ease of Use — which is genuinely notable. The praise that comes up most consistently: clean documentation, simple integration (it works as a proxy replacement in existing code), and responsive support when something goes wrong.

The complaints that come up most consistently: the credit math is confusing until you really sit with it, and performance on harder targets can be inconsistent depending on how aggressively the site changes its anti-bot measures.

One Capterra reviewer specifically called out that plan upgrades and downgrades were painless — you can move between tiers from the dashboard without friction, which matters when you're trying to match spend to your actual usage over time.

---

## The Free Trial Strategy: How to Use It Right

Before paying anything, run your actual scraping targets through the free trial. Here's the approach that actually works:

1. Sign up at 👉 [scraperapi.com](https://www.scraperapi.com/?fp_ref=coupons) — you get 1,000 ongoing free credits plus 5,000 trial credits for the first 7 days. No credit card.
2. Use the Dashboard's **Domain Cost Estimator** to check the credit cost for each of your target URLs before running bulk jobs.
3. Run a representative sample of your actual workflow — the same domains, the same parameters you'll use in production.
4. Watch your credit consumption in the dashboard and do the math: `(credits consumed in test) / (pages successfully scraped) = your real cost per page`.
5. Multiply that real cost-per-page by your expected monthly volume to figure out which plan actually covers your needs.

This takes maybe an hour and saves you from picking the wrong tier based on headline numbers.

---

## Frequently Asked Questions About ScraperAPI Plans

**Does one API credit equal one page request?**
Almost never. The base rate is 1 credit for a standard plain HTML page, but domain-based multipliers (Amazon = 5x, Google = 25x, LinkedIn = 30x) and feature flags (rendering, premium proxies) stack on top of that. Always check your specific target URL with the cost estimator before scaling.

**What happens when I run out of credits mid-month?**
On Hobby, Startup, and Business: you're cut off until renewal. Your only options are upgrading to the next tier or contacting support. On Scaling and above, pay-as-you-go lets you keep going at a fixed predictable rate with an optional spending cap.

**Do credits carry over if I don't use them all?**
No. Credits reset at each billing cycle. Plan accordingly — there's no benefit to overpaying for credits you won't actually use.

**Can I cancel anytime?**
Yes, directly from the dashboard or by contacting support. No penalty for cancelling. ScraperAPI also offers a 7-day no-questions-asked refund if you're not happy with the service after signing up.

**Is annual billing worth it?**
If you're committing to 12 months of usage, yes — 10% off is applied automatically. If you're still testing whether ScraperAPI is the right fit, start monthly and switch to annual once you've confirmed the plan matches your workflow.

**Can I get global geotargeting on the cheaper plans?**
No. US and EU proxies only on Hobby and Startup. Global geotargeting (country-level targeting across 50+ countries) starts at Business ($299/mo).

---

## The Bottom Line: Which ScraperAPI Plan Should You Actually Get?

Here's the honest decision framework:

- **You're testing or building a prototype**: Start with the free trial. Genuinely. It's 5,000 credits with full feature access, no card required. 👉 [Start the free trial](https://www.scraperapi.com/?fp_ref=coupons)
- **Personal project, lightweight monitoring, learning the API**: Hobby ($49/mo) — just know your multipliers before assuming 100,000 credits means 100,000 pages.
- **Small team, consistent volume, US/EU targets**: Startup ($149/mo) — the per-credit cost drops significantly here.
- **Production infrastructure, global targeting, unlimited analytics**: Business ($299/mo) — this is where the platform unlocks for serious use.
- **High-volume operations, continuity matters mid-cycle**: Scaling ($475/mo) — the PAYG overflow protection alone justifies the jump for many use cases.
- **Enterprise-grade pipelines**: Professional, Advanced, or Enterprise — price-per-credit keeps improving, and dedicated support becomes part of the deal.

ScraperAPI isn't the cheapest option on the market for every use case. But it's one of the most well-documented, easy-to-integrate, and reliably supported tools in the scraping API space — especially for Amazon, Google, and standard e-commerce targets. For most developer teams getting started with production scraping, it's a solid first choice.

Run your real workload through the free trial first. Then look at the table above and pick the tier your actual credit math points to.

👉 [Start your free ScraperAPI trial — 5,000 credits, no credit card needed](https://www.scraperapi.com/?fp_ref=coupons)
