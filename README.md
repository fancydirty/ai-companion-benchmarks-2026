# AI Companion App Benchmarks, Bank Statement Descriptors & LLM Stack Dataset (2026)

Open dataset and reproducible evaluation logs from **[The Companion Lab](https://thecompanionlab.com/)** (`https://thecompanionlab.com/`).

Between 16 and 23 October 2026, we tested **10 AI companion and AI girlfriend apps** (`Secrets AI`, `Nomi AI`, `SpicyChat AI`, `Ourdream AI`, `Kindroid AI`, `Xotic AI`, `GirlfriendGPT`, `Candy AI`, `DreamGF`, and `EroLove`) using:
1. **The same 6 standardized conversation prompts** in identical order (empathy/venting, planting two memory facts, character-specific humor, pushback against a terrible financial idea, a memory quiz three turns later, and a contextual selfie request).
2. **8 paid subscriptions on our own bank card**, recording the exact merchant descriptor strings printed on the card notifications, renewal pricing, token/coin meters, and cancellation dark patterns.
3. **Client-side JavaScript bundle and image/video EXIF inspection** to identify the underlying LLMs, image checkpoints (`Z-Image Turbo`, `Seedream`, `WAI-Illustrious-SDXL`), and video engines (`Wan`, `OmniHuman`, `Oh.xyz`).
4. **9 interactive, zero-signup character creator replicas** rebuilt screen-by-screen so readers can inspect each app's onboarding before handing over an email address. (Nine, not ten: EroLove has no character creator, which is a product decision rather than a gap.)
5. **A read of EroLove's 179 KB inline chat JavaScript and its undocumented API**, which is how three of the four defects in its teardown were found. The other nine apps were tested through the interface only.

---

## Quick Navigation & Primary Hubs

- **[Best AI Girlfriend Apps (October 2026 Ranked Roundup)](https://thecompanionlab.com/best-ai-girlfriend-apps/)**
- **[All 10 Hands-On App Reviews](https://thecompanionlab.com/reviews/)**
- **[Bank Statement Descriptor Lookup & Billing Index](https://thecompanionlab.com/billing/)**
- **[Safety, Legitimacy & Cancellation Audits (`/safety/`)](https://thecompanionlab.com/safety/)**
- **[1v1 Side-by-Side Comparisons (`/compare/`)](https://thecompanionlab.com/compare/)**
- **[Competitor & Unfiltered Alternatives Hub (`/alternatives/`)](https://thecompanionlab.com/alternatives/)**
- **[5-Question AI Companion Finder Quiz (`/quiz/`)](https://thecompanionlab.com/quiz/)**
- **[Try 9 Character Creators Without Signing Up (`/try/`)](https://thecompanionlab.com/try/)**
- **[Testing Methodology & Scoring Rubric (`/audits/methodology/`)](https://thecompanionlab.com/audits/methodology/)**
- **[About The Companion Lab (`/about/`)](https://thecompanionlab.com/about/)**

---

## 1. Real Bank Statement Descriptors (`bank-statement-descriptors.csv`)

Every merchant string below comes from a real payment made on our own card in October 2026.

| Merchant Descriptor on Card Notice | App | Charged | Checkout Promise | Discretion & Billing Page Link | Safety & Cancellation Audit |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **`S LABS INC 604-3295224 CA US`** | [Secrets AI](https://thecompanionlab.com/reviews/secrets-ai/) | $19.99 | `Appears as S LABS INC. on your statement` | [S LABS INC Statement Evidence](https://thecompanionlab.com/billing/s-labs-inc/) | [Is Secrets AI Safe & Legit?](https://thecompanionlab.com/is-secrets-ai-safe/) |
| **`NDAI.CC 514-2860020 DE US`** | [SpicyChat AI](https://thecompanionlab.com/reviews/spicychat-ai/) | $19.95 | *(Nothing stated on plans page)* | [NDAI.CC Statement Evidence](https://thecompanionlab.com/billing/ndai-cc/) | [Is SpicyChat AI Safe & Legit?](https://thecompanionlab.com/is-spicychat-ai-safe/) |
| **`NDAI.CHAT 514-2860020 DE US`** | [GirlfriendGPT](https://thecompanionlab.com/reviews/girlfriendgpt/) | $15.00 | `NDAI.CHAT` | [NDAI.CHAT Statement Evidence](https://thecompanionlab.com/billing/ndai-chat/) | [Is GirlfriendGPT Safe & Legit?](https://thecompanionlab.com/is-girlfriendgpt-safe/) |
| **`DREAMSTUDIOS.CO Limassol CY`** | [Ourdream AI](https://thecompanionlab.com/reviews/ourdream-ai/) | $19.99 | `Dream Studio` (in site code) | [DREAMSTUDIOS.CO Statement Evidence](https://thecompanionlab.com/billing/dreamstudios/) | [Is Ourdream AI Safe & Legit?](https://thecompanionlab.com/is-ourdream-ai-safe/) |
| **`EverAI candy.ai MT`** | [Candy AI](https://thecompanionlab.com/reviews/candy-ai/) | $9.99 | `EverAI` (omits `candy.ai` domain) | [EverAI candy.ai Statement Evidence](https://thecompanionlab.com/billing/everai/) | [Is Candy AI Safe & Legit?](https://thecompanionlab.com/is-candy-ai-safe/) |
| **`Dream AI dreamgf.ai RO`** | [DreamGF](https://thecompanionlab.com/reviews/dreamgf-ai/) | $12.99 | `DreamAI` (rebills at **$25.98/mo**) | [Dream AI dreamgf.ai Statement Evidence](https://thecompanionlab.com/billing/dream-ai/) | [Is DreamGF Safe & Legit?](https://thecompanionlab.com/is-dreamgf-ai-safe/) |
| **`Xotic.ai Tallinn EE`** | [Xotic AI](https://thecompanionlab.com/reviews/xotic-ai/) | $24.99 | `Xotic AI` | [Xotic.ai Statement Evidence](https://thecompanionlab.com/billing/xotic/) | [Is Xotic AI Safe & Legit?](https://thecompanionlab.com/is-xotic-ai-safe/) |

*Note on the three apps without a descriptor:* We tested [Nomi AI](https://thecompanionlab.com/reviews/nomi-ai/) on its free plan ([Is Nomi AI Safe?](https://thecompanionlab.com/is-nomi-ai-safe/)); we paid $13.99 on the web for [Kindroid AI](https://thecompanionlab.com/reviews/kindroid-ai/) Standard ([Is Kindroid AI Safe?](https://thecompanionlab.com/is-kindroid-ai-safe/)) without recording the card notification line; and [EroLove](https://thecompanionlab.com/reviews/erolove-ai/) gave us Premium for this test, so we never paid and no charge appeared ([Is EroLove AI Safe?](https://thecompanionlab.com/is-erolove-ai-safe/)). EroLove also takes **crypto only**, so its subscription does not auto-renew.

---

## 2. October 2026 Ranked Scorecard (`benchmarks-october-2026.json`)

| Rank | App | Overall | Conversation | Creator | Free Plan | Price Clarity | Monthly Price (Web) | No-Signup Creator Replica |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **#1** | **[Secrets AI](https://thecompanionlab.com/reviews/secrets-ai/)** | **8.3 / 10** | 9 | 9 | 7 | 8 | $19.99 ($9.17/mo yr) | [Try Secrets Creator](https://thecompanionlab.com/try/secrets/) |
| **#2** | **[Nomi AI](https://thecompanionlab.com/reviews/nomi-ai/)** | **7.8 / 10** | 8 | 6 | 9 | 8 | $15.99 ($8.33/mo yr) | [Try Nomi Creator](https://thecompanionlab.com/try/nomi/) |
| **#3** | **[SpicyChat AI](https://thecompanionlab.com/reviews/spicychat-ai/)** | **7.5 / 10** | 7 | 7 | 8 | 8 | $19.95 (no coin meter) | [Try SpicyChat Creator](https://thecompanionlab.com/try/spicychat/) |
| **#4** | **[Ourdream AI](https://thecompanionlab.com/reviews/ourdream-ai/)** | **7.0 / 10** | 7 | 9 | 6 | 6 | $19.99 ($9.99/mo yr) | [Try Ourdream Creator](https://thecompanionlab.com/try/ourdream/) |
| **#5** | **[Kindroid AI](https://thecompanionlab.com/reviews/kindroid-ai/)** | **6.8 / 10** | 9 | 7 | 5 | 6 | $13.99 web / $15.99 iOS | [Try Kindroid Creator](https://thecompanionlab.com/try/kindroid/) |
| **#6** | **[Xotic AI](https://thecompanionlab.com/reviews/xotic-ai/)** | **5.5 / 10** | 8 | 7 | 2 | 5 | $24.99 (1,200 XOT) | [Try Xotic Creator](https://thecompanionlab.com/try/xotic/) |
| **#7** | **[GirlfriendGPT](https://thecompanionlab.com/reviews/girlfriendgpt/)** | **5.5 / 10** | 8 | 7 | 3 | 4 | $15.00 (5,000 msgs) | [Try GirlfriendGPT Creator](https://thecompanionlab.com/try/girlfriendgpt/) |
| **#8** | **[Candy AI](https://thecompanionlab.com/reviews/candy-ai/)** | **4.8 / 10** | 5 | 8 | 2 | 4 | $9.99 first mo, then $13.99 | [Try Candy Creator](https://thecompanionlab.com/try/candy/) |
| **#9** | **[DreamGF](https://thecompanionlab.com/reviews/dreamgf-ai/)** | **3.5 / 10** | 5 | 4 | 2 | 3 | $12.99 first mo, then $25.98 | [Try DreamGF Creator](https://thecompanionlab.com/try/dreamgf/) |
| **#10** | **[EroLove](https://thecompanionlab.com/reviews/erolove-ai/)** | **6.7 / 10** | 8 | *n/a* | 5 | 7 | $12.99 ($6.50/mo yr), crypto only | *No creator, by design* |


**Ranking rule, stated because row #10 looks out of order.** An app we could score in fewer than four areas is always listed last, whatever its average. EroLove's 6.7 is the mean of three scores, not four, because it has no character creator at all — the cast is written and closed. Scoring that as zero would read a deliberate product decision as a failure, so the app goes last and says why, rather than being silently compared on an axis it does not have.

---

## 3. Head-to-Head 1v1 Comparisons (`/compare/`)

Each comparison page includes a 12-row feature and pricing table with explicit winner calls plus the verbatim 6-message chat transcripts side by side:

- **[Secrets AI vs Nomi AI](https://thecompanionlab.com/compare/secrets-vs-nomi-ai/)** — Best paid all-rounder vs best free plan
- **[Secrets AI vs Kindroid AI](https://thecompanionlab.com/compare/secrets-vs-kindroid/)** — Tied 9/10 on writing; compared on selfies, memory panel, and web pricing
- **[Kindroid AI vs Nomi AI](https://thecompanionlab.com/compare/kindroid-vs-nomi-ai/)** — Custom 2,000-character persona & LLM picker vs zero-paywall free chat
- **[Ourdream AI vs Secrets AI](https://thecompanionlab.com/compare/ourdream-vs-secrets-ai/)** — The two 9/10 character creators compared on coin vs Moment costs
- **[Ourdream AI vs Kindroid AI](https://thecompanionlab.com/compare/ourdream-vs-kindroid/)** — Visual workshop vs writer-first companion
- **[Ourdream AI vs Candy AI](https://thecompanionlab.com/compare/ourdream-vs-candy-ai/)** — Guest creator access, token traps, and bank statement privacy

---

## 4. Competitor & Unfiltered Alternatives Guides (`/alternatives/`)

For readers switching from filtered apps or apps with aggressive token meters, we mapped our 10 tested apps against the specific pain points of each platform:

- **[Best Character.AI Alternatives (Unfiltered & Tested)](https://thecompanionlab.com/alternatives/character-ai/)**
- **[Best Replika Alternatives (Memory, Voice & Clear Pricing)](https://thecompanionlab.com/alternatives/replika/)**
- **[Best CrushOn AI Alternatives (No Per-Message Coin Meter)](https://thecompanionlab.com/alternatives/crushon-ai/)**
- **[Best Janitor AI Alternatives (Hosted Models, Zero API Key Setup)](https://thecompanionlab.com/alternatives/janitor-ai/)**
- **[Best Muah AI Alternatives (Discreet Billing & Easy Cancellation)](https://thecompanionlab.com/alternatives/muah-ai/)**
- **[Best DarLink AI Alternatives (Free Plans & Tested Chat)](https://thecompanionlab.com/alternatives/darlink-ai/)**
- **[Best Candy AI Alternatives (Chats That Don't Lock After 5 Messages)](https://thecompanionlab.com/alternatives/candy-ai/)**
- **[Best Ourdream AI Alternatives (Unlimited Chat Without a Coin Meter)](https://thecompanionlab.com/alternatives/ourdream-ai/)**

---

## 5. Deep-Dive Technical Research Articles (`/blog/`)

- **[What AI Models Power Ourdream, Candy, Secrets and Kindroid?](https://thecompanionlab.com/blog/what-ai-models-power-ourdream-candy-secrets-kindroid/)**
- **[What AI Models Power SpicyChat, GirlfriendGPT, DreamGF, Xotic and Nomi?](https://thecompanionlab.com/blog/what-ai-models-power-spicychat-girlfriendgpt-dreamgf-xotic-nomi/)**
- **[AI Girlfriend Hidden Costs: Dreamcoins, Moments, XOT and Bank Statements](https://thecompanionlab.com/blog/ai-girlfriend-hidden-costs-dreamcoins-moments-and-bank-statements/)**
- **[Which AI Girlfriend Apps Allow NSFW? Tested on 9 Apps](https://thecompanionlab.com/blog/which-ai-girlfriend-apps-allow-nsfw-tested/)** *(written before EroLove joined the set)*
- **[EroLove review: the best memory here, and two photos that failed](https://thecompanionlab.com/blog/erolove-review-memory-and-photos/)** — the API teardown
- **[Kindroid Web vs iPhone App: The Apple Tax and NSFW Rules](https://thecompanionlab.com/blog/kindroid-web-vs-app-apple-tax-and-nsfw/)**
- **[Nomi vs Kindroid vs Candy vs Ourdream: The Same Six Messages](https://thecompanionlab.com/blog/nomi-vs-kindroid-vs-candy-vs-ourdream-same-six-messages/)**
- **[SpicyChat vs GirlfriendGPT vs DreamGF vs Xotic: Our Paid Test](https://thecompanionlab.com/blog/spicychat-vs-girlfriendgpt-vs-dreamgf-vs-xotic-paid-test/)**
- **[Try 9 AI Girlfriend Character Creators Without Signing Up](https://thecompanionlab.com/blog/try-ai-girlfriend-apps-without-signing-up/)**
- **[DeepSeek Roleplay Guide: V4 Flash vs V3.2 vs Companion Apps](https://thecompanionlab.com/blog/deepseek-roleplay-guide-v4-flash-vs-v3-2-vs-companion-apps/)**
- **[AI Girlfriend Apps Status Check (October 2026)](https://thecompanionlab.com/blog/ai-girlfriend-apps-status-check-october-2026/)**

---

## 6. EroLove: what the client bundle showed, and what the interface hides

EroLove is the only app here we tested by reading its code as well as clicking it. It ships its chat
application as a **179 KB inline JavaScript bundle** and drives almost everything over an undocumented
JSON API, so three of its four defects are invisible from the outside. Each is reproducible from a
signed-in account; none requires anyone else's credentials.

| Finding | Evidence | Why it matters |
| :--- | :--- | :--- |
| **30 pages promise a feature that returns 404** | `POST /api/chat/upload` → `404 {"error":"not_found"}`. The attach button is gated on `feat("userPhotos")`, and `/api/config` ships `features: ["chatPhotos","presence","voice"]`. The code for uploads exists (`sendPhoto`, `fileToJpegDataUrl`, the `[userphoto]` message type); only the flag is off. | The copy promising it appears on 17 category pages, 4 comparison pages, 8 scenario pages **and `/privacy`**. A privacy policy describing data handling for a feature that 404s is a different class of problem from a landing page doing it, and every page has an AI-readable `.md` twin that assistants quote verbatim. |
| **Memory is written in the wrong language, inconsistently** | All-English session, `default_language: "en"`, every companion `language: "en"`. Anna's extracted facts came back in **Estonian**, Rae's in **French**, Yuna's in nothing at all (`facts: []`). | The product's headline feature is a memory panel you can read and correct. Memory you cannot read cannot be corrected, so the write bug voids the selling point for exactly the users who look. Editing and injection work correctly, which isolates the fault to extraction. |
| **A blocked photo is indistinguishable from an outage** | 2 of 5 requests returned `{"status":"blocked"}`; the UI shows "Couldn't take a photo right now — try a bit later", the same string used for `photo_queue` errors. No sparks charged either time. | A refusal that does not say it is a refusal teaches users to retry. Unstable is worse than strict. |
| **"Unlimited messages" is 800/day** | `me.dailyLimit = 800` on Premium, while the plans page says unlimited. | Nobody in a 1:1 chat will hit it; a four-person room spends ~12 messages per exchange. |
| **The photo CDN caches 404s** | `/img/photos/{userId}/{id}.webp` returns a cached 404 if fetched before the render finishes. Our first fetch of a finished photo 404'd until we appended a cache-buster. | A user can end up with a permanently broken image for a photo they paid for. |

Full teardown with the reproduced API responses: **[EroLove review: the best memory here, and two photos that failed](https://thecompanionlab.com/blog/erolove-review-memory-and-photos/)**.

---

## 7. Machine-readable access

Every page on the site has a plain-markdown twin at the same path plus `.md`, and the whole dataset is
available as one file. Both are generated from the same source as the HTML, so a crawler cannot receive
a version of these findings without the caveats attached.

| What | Where |
| :--- | :--- |
| Summary with a structured Facts block | `https://thecompanionlab.com/llms.txt` |
| Unabridged dataset: every score with its observation, every price row with its source | `https://thecompanionlab.com/llms-full.txt` |
| Markdown twin of any page | append `.md` — e.g. [the EroLove review as markdown](https://thecompanionlab.com/reviews/erolove-ai.md) |
| This repo's data files | `bank-statement-descriptors.csv`, `benchmarks-october-2026.json` |

`robots.txt` names 30 AI crawlers individually (including `CCBot`, `OAI-SearchBot`, `ClaudeBot` and
`PerplexityBot`) with `Content-Signal: search=yes, ai-train=yes, ai-input=yes`.

---

## License

Data files (`bank-statement-descriptors.csv`, `benchmarks-october-2026.json`) are released under CC BY 4.0. Please attribute **[The Companion Lab](https://thecompanionlab.com/)**.
