# ScrapingBee vs ScraperAPI: which is cheaper per 1,000 pages, and which plan should you buy? (credit multipliers, the full plan table, and the billing settings to fix before you pay)

Both APIs start at $49 a month, and neither sticker price tells you much. ScrapingBee's $49 buys 250,000 credits; ScraperAPI's buys 100,000, and the same target page can cost 1 credit on one platform and 75 on the other. Convert credits into dollars per 1,000 pages and ScrapingBee comes out cheaper for plain HTML, JavaScript-rendered pages and Google results at every tier. ScraperAPI is cheaper on Cloudflare-protected pages from the entry plan up, and it takes the lead on Amazon once you're spending around $300 a month.

Every price below is the published list price on both vendors' pricing pages as of October 2026, monthly billing in USD.

> **The 30-second version**
> - **Ordinary or JS-heavy pages at small to medium volume:** ScrapingBee's $49 plan goes roughly five times further on rendered pages ($0.98 vs $5.39 per 1,000).
> - **Pages behind Cloudflare, DataDome or PerimeterX:** ScraperAPI, at $10.29 per 1,000 rendered protected pages against $14.70.
> - **You want parsed JSON from Amazon, Google or Walmart instead of writing parsers:** ScraperAPI's structured endpoints do that server-side.
> - **Not ready to commit:** ScraperAPI gives you 5,000 credits for the first 7 days, then a free plan with 1,000 credits a month. 👉 [Check ScraperAPI's current plans and start the trial](https://www.scraperapi.com/?fp_ref=coupons)

## What ScraperAPI's plans cost

Seven tiers, from $49 to $1,975, then custom. The per-request credit rates are identical on all of them, so upgrading buys volume and concurrency, not cheaper individual pages.

| Plan | Monthly | Annual (per month) | Credits | Threads & geotargeting | Sign up |
| --- | --- | --- | --- | --- | --- |
| Hobby | $49 | $44.10 | 100,000 | 20 threads, US & EU | [Get Hobby](https://www.scraperapi.com/?fp_ref=coupons) |
| Startup | $149 | $134.10 | 1,000,000 | 50 threads, US & EU | [Get Startup](https://www.scraperapi.com/?fp_ref=coupons) |
| Business | $299 | $269.10 | 3,000,000 | 100 threads, global | [Get Business](https://www.scraperapi.com/?fp_ref=coupons) |
| Scaling | $475 | $427.50 | 5,000,000 | 200 threads, global | [Get Scaling](https://www.scraperapi.com/?fp_ref=coupons) |
| Professional | $975 | $877.50 | 10,500,000 | 300 threads, global | [Get Professional](https://www.scraperapi.com/?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50 | 21,500,000 | 500 threads, global | [Get Advanced](https://www.scraperapi.com/?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22,000,000+ | 500+ threads, global | [Talk to sales](https://www.scraperapi.com/?fp_ref=coupons) |

Four things the table doesn't show:

- **Geotargeting beyond the US and EU needs Business.** Hobby and Startup only cover US and EU proxies; country-level targeting starts at $299, and none of the seven plans offers city-level targeting in the current documentation.
- **Pay-as-you-go overage starts at Scaling ($475).** Hobby, Startup and Business cannot spill past their credit allowance.
- **Credits expire at renewal.** No rollover on monthly plans. Annual plans are different: you get the full year's credits up front and can spend them on any schedule, but a year is a long commitment if your target list is still changing.
- **Annual billing is exactly 10% off** at every tier, which is why the third column reads $44.10 rather than $49.

## The credit multiplier is the actual price

ScraperAPI bills by feature and by domain, adding credits on top of a 1-credit base. ScrapingBee bills by feature, multiplying per request. Rendering is the line that decides most budgets: 10 extra credits on ScraperAPI against a 5-credit total on ScrapingBee.

| Page type | ScraperAPI credits | ScrapingBee credits | ScraperAPI per 1,000 | ScrapingBee per 1,000 |
| --- | --- | --- | --- | --- |
| Plain HTML | 1 | 1 | $0.49 | $0.20 |
| JavaScript rendered | 11 | 5 | $5.39 | $0.98 |
| Rendered behind Cloudflare | 21 | 75 | $10.29 | $14.70 |
| Google results page | 25 | 15 | $12.25 | $2.94 |
| Amazon product page | 5 | 10 | $2.45 | $1.96 |

Dollar columns use ScraperAPI Hobby ($49 / 100,000 credits) and ScrapingBee's $49 plan (250,000 credits). The Cloudflare row assumes 1 credit plus 10 for rendering plus ScraperAPI's 10-credit anti-bot bypass surcharge; on ScrapingBee it assumes the 75-credit stealth proxy. The Amazon row assumes ScrapingBee's 10-credit premium proxy, which is what Amazon targets normally need.

ScraperAPI's other rates worth knowing before you size a plan:

- **25 credits for any Google or Bing subdomain**, including Maps and Shopping URLs
- **5 credits for Amazon, Walmart and eBay**
- **30 credits for LinkedIn**
- **+10 credits for a bot-protection bypass** (Cloudflare, Cloudflare Turnstile, DataDome, PerimeterX/HUMAN, Akamai), applied automatically when the bypass logic kicks in
- **+10 for a premium proxy**, **+10 for a screenshot**, **30 for ultra-premium** and **75 for ultra-premium with rendering**
- **Geotargeting, sticky sessions, device type and output format cost nothing extra**

That last point matters for budgeting: setting a country code or holding a session open doesn't move the number, so the only variables you need to model are rendering, proxy tier and domain.

At the ~$300 tier the ranking shifts. Business ($299 / 3,000,000 credits) works out to $0.10 per 1,000 plain pages, $1.10 rendered, $2.49 on Google, $2.09 rendered behind Cloudflare and $0.50 on Amazon. ScrapingBee's $249 Business plan (3,000,000 credits) gives $0.08, $0.42, $1.25, $6.23 and $0.83 on the same rows. ScrapingBee keeps the lead on plain, rendered and Google; ScraperAPI takes Amazon and Cloudflare.

## Four workloads, priced

Same arithmetic, applied to jobs people actually run. Each row picks the smallest plan on each side that covers the month.

| Workload per month | ScraperAPI credits | ScrapingBee credits | ScraperAPI | ScrapingBee |
| --- | --- | --- | --- | --- |
| 200,000 plain pages | 200,000 | 200,000 | Startup, $149 | Freelance, $49 |
| 40,000 JS-rendered pages | 440,000 | 200,000 | Startup, $149 | Freelance, $49 |
| 60,000 Google SERPs (200 keywords, top 10, daily) | 1,500,000 | 900,000 | Business, $299 | Startup, $99 |
| 100,000 rendered pages behind Cloudflare | 2,100,000 | 7,500,000 | Business, $299 | Business+, $599 |

The two middle rows are the ones that surprise people. Rendering 40,000 pages a month costs 440,000 ScraperAPI credits, which is 44% of the $49 Hobby plan spent on 40,000 pages. Google is worse: at 25 credits a page, a modest rank-tracking job of 60,000 requests eats 1.5 million credits and lands you on the $299 plan, while ScrapingBee's 15-credit Google rate fits 900,000 credits inside its $99 plan.

Cloudflare is the row where the direction flips hard, and it flips for a boring reason: ScraperAPI charges 10 credits to bypass, ScrapingBee charges 75 for its stealth proxy. If most of your target list sits behind Cloudflare, that gap compounds faster than any discount code will fix.

## Where ScraperAPI earns its money

Price per page is only half the bill. The other half is what you spend building and maintaining the thing around the API.

**Structured endpoints.** ScraperAPI documents dedicated endpoints for Amazon, Google and Walmart that return parsed JSON: prices, ratings, ranks, SERP results. If your pipeline currently spends engineering hours on HTML selectors that break every few weeks, this replaces that work. 👉 [Compare the plans that include structured endpoints](https://www.scraperapi.com/?fp_ref=coupons)

**Per-request control.** `render=true` for JavaScript, `premium=true` for harder targets, `country_code` for geography, `session_number` to keep the same IP across a multi-step flow. You can switch these per call instead of buying a feature tier that applies to everything.

**Cost visibility before you spend.** Every response carries a `sa-credit-cost` header showing what that request cost, a `max_cost` parameter caps any single request, and the dashboard's Domain Cost Estimator will price a URL before you scrape 100,000 of them. That's the cheapest way to sanity-check the tables above against your own target list.

**Scheduled and async work.** Its documentation lists a no-code DataPipeline for recurring jobs and an asynchronous scraper service, plus integrations aimed at LLM workflows. Both are documented features rather than headline numbers, so verify them against the current docs if they're the reason you're switching.

## Where ScrapingBee is the better buy

ScrapingBee runs a real headless Chrome instance and exposes the browser, not just the HTML. Custom JavaScript scenarios that run for up to 40 seconds, full-page and element screenshots, CSS and XPath extraction rules, and plain-English AI extraction are all first-class features there, and none of them has an equivalent on ScraperAPI's feature list.

If your job involves clicking "load more", scrolling an infinite product grid, filling a search box, or capturing a screenshot for visual QA, that's the deciding factor and the per-page math stops mattering.

Its credit economics also beat ScraperAPI at the low end. The $49 plan carries 250,000 credits against 100,000, and a rendered page costs 5 credits against 11. For a small team scraping a few thousand pages a week, that difference alone can keep you off a $149 plan.

## Three settings to fix before you pay

These are the items that turn a $49 plan into a $299 invoice, and none of them is on the pricing page's headline.

1. **Set a spending cap the day you sign up.** ScraperAPI's billing documentation says pay-as-you-go is available from Scaling upward, and the cap you set there is a hard limit, not a pre-charge. Without PAYG, Hobby, Startup and Business simply return 429s and pause when credits run out. Auto-upgrade is opt-in on every plan, so leave it off unless you'd rather absorb a bigger bill than a stalled crawl.
2. **Check where your traffic needs to come from.** US and EU only on Hobby and Startup. If you need to appear as a Brazilian or Japanese visitor, the entry price is $299, not $49.
3. **Don't buy a year to save 10% until the monthly bill is stable.** Annual plans hand over twelve months of credits at once with no refund of unused volume, and a target list that grows 3x in month two leaves you with a plan you've outgrown and a year to wait.

A 7-day refund applies either way, and the first 7 days after signup come with 5,000 credits, which is enough to run the four workloads above against your own URLs before committing. 👉 [Start on the $49 Hobby plan with 5,000 trial credits](https://www.scraperapi.com/?fp_ref=coupons)

## Success rates: ignore every single number you read

Third-party benchmarks on these two disagree with each other, sometimes by 50 percentage points. One 2025 benchmark of heavily protected sites puts ScrapingBee ahead; another test has both at 92.7% average success with ScrapingBee faster; a third reports ScraperAPI at 100% on Amazon and Walmart but 40-second average response times there; a fourth has ScraperAPI near 98.7%. None of the vendors publishes independently audited success or uptime figures.

The practical implication is that you cannot pick between them from a review's success table. Run 200 of your own URLs through the trial, count the ones that come back with the content you expected, and apply that hit rate to the credit math above. A 90% success rate on 11 credits a page effectively costs 12.2 credits per usable page, and that adjustment is worth more than any benchmark.

## Which one to buy

- **Cloudflare, DataDome or PerimeterX targets make up a serious share of your list** → ScraperAPI, starting at Hobby. The 10-credit bypass against a 75-credit stealth proxy is the whole argument.
- **You want Amazon, Walmart or Google data as JSON without maintaining parsers** → ScraperAPI, and check the Domain Cost Estimator against a sample of your URLs first.
- **You need to click, scroll, screenshot or extract with natural-language rules** → ScrapingBee. No plan on ScraperAPI's ladder substitutes for that.
- **Plain pages, rendered pages or rank tracking at under ~$300 a month** → ScrapingBee's $49 to $99 plans are cheaper per 1,000 pages; ScraperAPI only overtakes on Amazon and protected sites at the Business tier.
- **Under 100,000 plain pages a month with US or EU geotargeting and no rendering** → ScraperAPI Hobby at $49 is competitive at $0.49 per 1,000 and comes with a permanent free tier to test on.

Before you enter a card: confirm your target country is on the plan you're buying, price ten real URLs with the Domain Cost Estimator, and decide now whether hitting the credit ceiling should pause the job or upgrade the plan. 👉 [Pick the ScraperAPI plan that matches your credit math](https://www.scraperapi.com/?fp_ref=coupons)
