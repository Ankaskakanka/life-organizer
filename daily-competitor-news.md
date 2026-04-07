# 📰 Daily Competitor Intelligence Shortcut

> **Run this shortcut daily in Cowork** to automatically fetch the latest competitor news and add it to the Industry Updates tab.

---

## What this shortcut does

1. Searches the web for recent news about Cludo's 11 key competitors
2. Formats new items into the correct structure
3. Adds them to the `INDUSTRY_NEWS` array in `index.html`
4. Bumps the app version so changes are picked up on next refresh

---

## Prompt to paste into Cowork

Copy and send the following as a new message to Claude in Cowork:

---

**Search for the latest competitor intelligence and update my Life Organizer.**

Please do all of the following:

1. **Search the web for recent news** (last 7 days) about each of these competitors:
   - SearchStax, Algolia, Raffle, Wonderchat, AddSearch, Inbenta, Coveo, Yext, Glia, Squiz/Funnelback, Vertex AI Search (Google)

   Search for things like: new features, product launches, funding rounds, acquisitions, pricing changes, new customers, leadership changes, partnerships.

2. **Format any relevant findings** as news items using this exact JavaScript object structure:
   ```javascript
   { id:'nXXX', date:'YYYY-MM-DD', competitor:'COMPETITOR_ID', competitorName:'Name', type:'TYPE', title:'Short title', summary:'2-3 sentence summary of what happened and why it matters for Cludo.', source:'Source name', tags:['tag1','tag2'] }
   ```
   Where:
   - `competitor` id is one of: `searchstax`, `algolia`, `raffle`, `wonderchat`, `addsearch`, `inbenta`, `coveo`, `yext`, `glia`, `squiz`, `vertex`
   - `type` is one of: `churn`, `lost-deal`, `product`, `funding`, `competitive`, `partnership`
   - `id` should be `n` + today's date (YYYYMMDD) + a sequence number (e.g. `n20260408_01`)

3. **Edit the file** `/sessions/affectionate-zen-newton/mnt/life-organizer/index.html`:
   - Add the new news items to the **beginning** of the `INDUSTRY_NEWS` array (after the `[` on the `const INDUSTRY_NEWS = [` line)
   - Only add items where you found a concrete, real news event — not speculation
   - Bump `version:` in APP_DATA up by 1

4. **Report back** what you found and added, with a short summary of each competitor's status.

---

## Competitor IDs reference

| Competitor | ID | Website |
|---|---|---|
| SearchStax | `searchstax` | searchstax.com |
| Algolia | `algolia` | algolia.com |
| Raffle | `raffle` | raffle.ai |
| Wonderchat | `wonderchat` | wonderchat.io |
| AddSearch | `addsearch` | addsearch.com |
| Inbenta | `inbenta` | inbenta.com |
| Coveo | `coveo` | coveo.com |
| Yext | `yext` | yext.com |
| Glia | `glia` | glia.com |
| Squiz / Funnelback | `squiz` | squiz.net |
| Vertex AI Search | `vertex` | cloud.google.com/enterprise-search |

---

## Schedule recommendation

Run this shortcut **every Monday morning** to start the week with fresh competitive intelligence. It takes about 2-3 minutes to run.
