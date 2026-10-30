# AI Companion App Benchmarks, Bank Statement Descriptors & LLM Stack Dataset (2026)

Open dataset and reproducible evaluation logs from **[The Companion Lab](https://thecompanionlab.com/)** (`https://thecompanionlab.com/`).

Between 16 and 27 October 2026, we tested **10 AI companion and AI girlfriend apps** (`Secrets AI`, `Nomi AI`, `SpicyChat AI`, `Ourdream AI`, `Kindroid AI`, `Xotic AI`, `GirlfriendGPT`, `Candy AI`, `DreamGF`, and `EroLove`) using:
1. **The same 6 standardized conversation prompts** in identical order (empathy/venting, planting two memory facts, character-specific humor, pushback against a terrible financial idea, a memory quiz three turns later, and a contextual selfie request).
2. **8 paid subscriptions on our own bank card**, recording the exact merchant descriptor strings printed on the card notifications, renewal pricing, token/coin meters, and cancellation dark patterns.
3. **Client-side JavaScript bundle and image/video EXIF inspection** to identify the underlying LLMs, image checkpoints (`Z-Image Turbo`, `Seedream`, `WAI-Illustrious-SDXL`), and video engines (`Wan`, `OmniHuman`, `Oh.xyz`).
4. **9 interactive, zero-signup character creator replicas** rebuilt screen-by-screen so readers can inspect each app's onboarding before handing over an email address. (Nine, not ten: EroLove has no character creator, which is a product decision rather than a gap.)
5. **A read of EroLove's 179 KB inline chat JavaScript and its undocumented API** (23 Oct 2026), followed by a **48-hour re-test on 26 Oct 2026** confirming that EroLove patched all four initial defects we reported.

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
- **[Try 8 Recorded Paid Chat Rooms Without Signing Up (`/chat-simulator/`)](https://thecompanionlab.com/chat-simulator/)**
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
| **#10** | **[EroLove](https://thecompanionlab.com/reviews/erolove-ai/)** | **7.0 / 10** | 8 | *n/a* | 5 | 8 | $12.99 ($6.50/mo yr), crypto only | *No creator, by design* |


**Ranking rule, stated because row #10 looks out of order.** An app we could score in fewer than four areas is always listed last, whatever its average. EroLove's 7.0 is the mean of three scores (8, 5, 8 after the 26 Oct re-test), not four, because it has no character creator at all — the cast is written and closed. Scoring that as zero would read a deliberate product decision as a failure, so the app goes last and says why, rather than being silently compared on an axis it does not have.

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
- **[EroLove Review: The Best Memory I've Used, and Four Bugs They Fixed in 48 Hours](https://thecompanionlab.com/blog/erolove-review-memory-and-photos/)** — the 179 KB bundle teardown & 26 Oct re-test
- **[We Rebuilt Paid AI Girlfriend Chat Rooms So You Don't Have to Hand Over Your Card First](https://thecompanionlab.com/blog/ai-girlfriend-chat-simulator-no-sign-up-what-paid-apps-hide/)**
- **[We Tested 10 AI Girlfriends With a Safe Word and a Cheating Accusation—Then Checked the Network Logs to See Who Faked the Memory](https://thecompanionlab.com/blog/ai-girlfriend-memory-test-velvet-safe-word-and-jealousy/)**
- **[AI Girlfriend Voice Calls & Read-Aloud Tested Across 10 Apps](https://thecompanionlab.com/blog/ai-girlfriend-voice-calls-and-tts-tested/)**
- **[AI Girlfriend Video Generators Tested (2026): $3 Clips, 15-Minute Queues, and Which Apps Forgot the Sound](https://thecompanionlab.com/blog/ai-girlfriend-video-generators-tested-candy-ourdream-secrets-kindroid/)**
- **[The Real Cost of 10 Turns on Paid AI Girlfriend Apps: Exact Token, Coin & Moment Ledgers](https://thecompanionlab.com/blog/real-cost-of-10-minutes-on-paid-ai-girlfriend-apps/)**
- **[AI Girlfriend Selfie Consistency Tested (2026): Context Blindness & Broken NSFW Blur Switches](https://thecompanionlab.com/blog/ai-girlfriend-selfie-consistency-test/)**
- **[Kindroid Web vs iPhone App: The Apple Tax and NSFW Rules](https://thecompanionlab.com/blog/kindroid-web-vs-app-apple-tax-and-nsfw/)**
- **[Nomi vs Kindroid vs Candy vs Ourdream: The Same Six Messages](https://thecompanionlab.com/blog/nomi-vs-kindroid-vs-candy-vs-ourdream-same-six-messages/)**
- **[SpicyChat vs GirlfriendGPT vs DreamGF vs Xotic: Our Paid Test](https://thecompanionlab.com/blog/spicychat-vs-girlfriendgpt-vs-dreamgf-vs-xotic-paid-test/)**
- **[Try 9 AI Girlfriend Character Creators Without Signing Up](https://thecompanionlab.com/blog/try-ai-girlfriend-apps-without-signing-up/)**
- **[DeepSeek Roleplay Guide: V4 Flash vs V3.2 vs Companion Apps](https://thecompanionlab.com/blog/deepseek-roleplay-guide-v4-flash-vs-v3-2-vs-companion-apps/)**
- **[AI Girlfriend Apps Status Check (October 2026)](https://thecompanionlab.com/blog/ai-girlfriend-apps-status-check-october-2026/)**

---

## 6. EroLove: 179 KB Client Bundle Teardown (23 Oct) & 48-Hour Fix Verification (26 Oct 2026)

> **Update (26 October 2026 — All 4 Issues Fixed & Re-Tested):** Within 48 hours of our initial 23 October teardown, EroLove's engineering team shipped fixes for all four defects below. We re-ran our tests on a live account on 26 October 2026 and verified every fix in both the UI and the network responses. With the 800/day message cap now printed clearly on the plans page, EroLove's price-clarity score moved from `7/10` to `8/10`, raising its overall score from **`6.7/10` to `7.0/10`**. EroLove also tied Secrets AI at the top of our 10-app persistent memory test for its editable, plain-English **What they know** / **Our story** memory panel.

EroLove is the only app here we originally tested by reading its client code (`179 KB` on 23 Oct, `177 KB` on 26 Oct after stripping dormant upload code) as well as clicking through the interface:

| Initial Finding (23 Oct 2026) | What We Saw on 23 Oct | 26 Oct 2026 Patch & Our Re-Test Verification |
| :--- | :--- | :--- |
| **1. 30 pages promised a user-upload feature that returned 404** | `POST /api/chat/upload` returned `404 {"error":"not_found"}` (retired 14 Oct), while ~30 FAQ blocks across category, comparison, scenario pages and `/privacy` still promised user photo uploads. | **Fixed & Verified (26 Oct):** EroLove removed the stale upload FAQ copy across all 9 languages (HTML and `.md` twins) and stripped `sendPhoto` / `fileToJpegDataUrl` / `attachBtn` from the client bundle. |
| **2. Memory extraction drifted into Estonian/French** | In an all-English session (`default_language: "en"`), Anna's extracted facts came back in **Estonian** and Rae's in **French**, while editing and pinning worked in English. | **Fixed & Verified (26 Oct):** Extractor now pins the session language. In our 5-message English re-test with Yuna on 26 Oct, all extracted memory notes and `Our story` entries were written in clean English. |
| **3. A content-blocked photo showed the same message as a server outage** | 2 of 5 photo requests returned `{"status":"blocked"}`, which the UI mapped to the generic `"Couldn't take a photo right now — try a bit later"` string (0 sparks charged). | **Fixed & Verified (26 Oct):** Client bundle now branches `s.status === "blocked" ? "photoBlocked" : "photoFail"`, displaying `"This photo goes against our content rules, so it wasn't made. No sparks spent — ask for a different one."` |
| **4. "Unlimited messages" had an unprinted 800/day cap** | `/api/me` carried `dailyLimit: 800` on Premium while the plans page said `"Unlimited messages"`. | **Fixed & Verified (26 Oct):** `/pricing`, `/account/plan`, `/press` and `/llms.txt` now explicitly state `"Unlimited messages (up to 800 a day)"`. Our Rae + Kit room test also confirmed a multi-companion room turn increments `usedToday` by only `1`. |

Full teardown and 26 October re-test logs: **[EroLove Review: The Best Memory I've Used, and Four Bugs They Fixed in 48 Hours](https://thecompanionlab.com/blog/erolove-review-memory-and-photos/)**.

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
