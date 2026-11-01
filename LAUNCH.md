# Talaro: deploy, name and launch plan

## 0. Deploy (2 minutes)
1. Put `index.html` alone in a folder and drag that folder onto https://app.netlify.com/drop. Nothing else is needed.
2. **Optional, for more news and web results.** Google News, Bing News and Marginalia do not allow direct browser calls. If you also add a file named `_redirects` (no extension) next to `index.html` with these three lines, Netlify forwards them for you (this is configuration, not server code):
```
/api/gnews     https://news.google.com/rss/search           200!
/api/bingnews  https://www.bing.com/news/search             200!
/api/marginalia https://api2.marginalia-search.com/search   200!
```
Without that file the site still works. News then comes from GDELT, and the Marginalia web results are skipped. (Marginalia asks for an `API-Key: public` header, which `_redirects` cannot add. If its results stay empty, that is why; it is a small loss.)
3. **First thing after deploying:** open the site, scroll to the footer and click **Check data sources**. It calls every source live and shows a tick or cross with timing for each. I could not reach live APIs from my workspace, so this is the first real test. Any source that shows a cross is silently skipped in searches, and you can send me its name to fix.

### What is inside (about 45 free, key-less sources)
- **Web/knowledge:** Wikipedia (all 13 languages), Mwmbl, YaCy, Marginalia (with proxy), DuckDuckGo instant answers.
- **News:** Google News and Bing News (with proxy), GDELT, Wikinews, rss2json fallback.
- **Images and video:** Wikimedia Commons, Openverse, NASA, Art Institute of Chicago, SepiaSearch (PeerTube).
- **Papers and books:** Crossref, Europe PMC, Semantic Scholar, DOAJ, Zenodo, arXiv, Internet Archive, Open Library, Google Books, Gutenberg, Wikisource.
- **Code and forums:** GitHub, npm, Stack Overflow, Hacker News.
- **Places:** Nominatim, Photon, Wikivoyage.
- **Instant answers:** weather (Open-Meteo), prayer times (Aladhan), currency, calculator, units, dictionary, India PIN code, IFSC bank codes.
- **Translation:** Lingva, then MyMemory. **Trending:** Wikimedia pageviews.
- Every result also has a row of links to search the same words on Google, Bing, DuckDuckGo, Brave, Yandex, Baidu and YouTube, so a visitor is never stuck.


## 0b. SEO and "Install app" (new)
**Already inside `index.html`:** keyword-rich title and description, canonical link, `index,follow` on the home page and `noindex` on result pages (so Google does not index endless searches), hreflang for all 13 languages, Open Graph and Twitter cards, structured data (WebSite with search box, WebApplication, FAQ), one `h1`, and a no-JavaScript fallback text.

**One step for you once you know your web address:** open `index.html` in a text editor and replace every `https://YOUR-DOMAIN` with your real address (for example `https://talaro.pk`). Google picks up the right address automatically even if you skip this, but WhatsApp, Facebook and X link previews need the replacement to show the share image.

**Optional extras (`talaro-extras.zip`):** unzip these next to `index.html` in the same Netlify folder: `og-image.png` (share picture), `icon-192.png` and `icon-512.png`, `robots.txt` and `sitemap.xml` (replace `YOUR-DOMAIN` inside them too), `sw.js` (lets the installed app open offline), `_redirects` (extra news sources), `_headers`, `opensearch.xml`.

**After launch:**
1. Add the site to Google Search Console and Bing Webmaster Tools, verify it, and submit `sitemap.xml`.
2. Use "Request indexing" for the home page and the language pages.
3. Get 5 to 10 real links (your launch posts, GitHub README, Product Hunt page); links matter more than any tag.
4. Check speed with PageSpeed Insights.

**Install on a phone:** Chrome and Edge show an **Install app** button in the top bar, and a banner from the second visit (if dismissed it stays away for 14 days). iPhone Safari does not allow a real install button, so the banner explains "Share, then Add to Home Screen". The text is translated into all 13 languages, and both disappear once the app is installed. Install needs https, which Netlify gives by default.

## 1. The name

**Recommended: Talaro** (from *talash*, "search", in Urdu, Hindi, Punjabi and Bengali, with an open "-aro" ending that is easy to say in any language). Five letters, three syllables, no meaning to avoid in major languages that I know of, and it works as a verb ("Talaro it").

**What I could and could not verify.** My workspace could not reach domain registries (RDAP/WHOIS are blocked) and I could not open one, so **I have not confirmed that any domain is free**. What web searches showed:
- **Sawalo**, my first idea, is **ruled out**: it has a company profile on Tracxn and an Indian trademark application.
- **Talaro**, **Khojio**, **Ilmora**: no search engine, app or startup with that name turned up in my searches. "Ilmora" has a small Android developer account on AppBrain, so I rank it last.
- Plain words such as *Khoj*, *Dhundo*, *Justuju* are already used by search products or startups. Avoid them.

**Do these five checks before you commit (15 minutes, all free):**
1. Domains: search the name at https://lookup.icann.org (RDAP) or any registrar. Check `.com`, `.app`, `.in`, `.pk`, `.net`. If `.com` is taken, `gotalaro.com`, `talaro.app` or `talaro.io` are acceptable starts.
2. Trademarks: WIPO Global Brand Database (branddb.wipo.int), USPTO search (tmsearch.uspto.gov), IP India public search, and IPO Pakistan. Look at class 9, 35, 38 and 42.
3. Handles: check the name on X, Instagram, YouTube, GitHub, Product Hunt and Reddit.
4. App stores: search Google Play and the Apple App Store.
5. Say it aloud to three people from Pakistan and three from India, and ask them to type what they heard.

Backups if Talaro fails any check, in order: **Khojio**, **Ilmora**. Rename in `site/js/config.js`, `<title>` in `index.html`, and `manifest.webmanifest`.

A note on the "Amazon/Alibaba level" goal: those names became global because of the product and years of distribution, not the word. A distinctive, pronounceable, ownable name is the most a name can do.

## 2. Before launch (week 0)
- Deploy on Netlify, add your domain, confirm HTTPS.
- Run 20 searches in each language you want to promote. Fix anything that looks wrong and note which sources fail.
- Write a plain landing line: "Free search in 13 Indian and Pakistani languages. No sign-up. No tracking."
- Record a 30-second screen video: search in Urdu, switch to Hindi, translate a result, open images.
- Open a public GitHub repo with README and MIT licence. Developers trust what they can read.
- Set up a free analytics-free feedback path: a GitHub Issues link and one email address.
- Be honest in all copy: this is a meta-search over free public indexes, not a crawler of the whole web.

## 3. Launch sequence

| Day | Channel | What to post | Notes |
|---|---|---|---|
| T-7 | Friends, class, WhatsApp groups | Link and "tell me what feels wrong" | Fix the top 5 complaints first |
| T-3 | Product Hunt: schedule | Tagline under 60 characters, e.g. "Search in your own language, free". 3-4 screenshots, the video, a founder comment | Launch at 12:01 am Pacific; ask 20 real friends to comment (not just upvote) |
| T-0 | Product Hunt | Reply to every comment within the hour | Do not ask for upvotes publicly |
| T-0 | Hacker News: **Show HN** | Title: "Show HN: Talaro, a free search engine for Urdu, Hindi and 11 other South Asian languages". First comment: how it works, what it cannot do, source list | Post Tue-Thu morning US Eastern; respond to critics calmly; never ask for upvotes |
| T+0 to T+3 | Reddit | r/SideProject, r/webdev, r/InternetIsBeautiful (follow each sub's self-promo rules), r/pakistan, r/india, r/IndiaTech, r/learnprogramming | One post per sub, tailored, no copy-paste; show the language switch |
| T+1 | X / LinkedIn | Build-in-public thread: why local-language search is broken, a GIF, the stack, the honest limits | Tag Pakistani and Indian developer communities |
| T+2 | Dev communities | dev.to and Hashnode post: "How I built a 13-language search engine with no server" | Real technical detail gets shared |
| T+3 | Facebook groups, Telegram, WhatsApp | Urdu, Hindi, Punjabi, Tamil, Telugu, Bengali posts written by native speakers | Different message per language; do not machine-translate the pitch |
| T+7 | Universities and colleges | Short demo to your ADP class, then CS societies in Lahore, Karachi, Islamabad, Delhi, Bengaluru, Hyderabad | Students are early, forgiving users |
| T+14 | Press and newsletters | Pitch to ProPakistani, TechJuice, YourStory, Inc42, Medianama, TechCrunch-style newsletters | Lead with the user problem, not the tech |

## 4. Make people come back
- Add the site as an installable app (a web manifest is already included).
- Ask Firefox, Chrome and Edge users to set it as a custom search engine (`https://YOURDOMAIN/?q=%s`). This works today because search is URL-driven.
- Publish a monthly "most searched, by language" post using only what users volunteer; the site collects nothing by default.
- Make a one-minute video per language for elders: "type or speak, tap a result".

## 5. Measure honestly
Use Netlify's built-in traffic numbers and GitHub stars. Targets for the first month: 1,000 visitors, 100 return visitors, 20 written pieces of feedback. If a language has few users, ask native speakers to read its interface and fix wording; machine-written interface text needs a native reviewer.

## 6. Risks to watch
- **API limits and outages:** Marginalia's shared key, MyMemory's daily characters, and any provider can change. Add a status note in the README when one breaks.
- **Terms of use:** keep requests user-initiated and cached (already done); do not scrape. Show attribution for images (already shown in the viewer).
- **Quality gap:** expect "it did not find X" feedback. Treat each one as a bug report on a source or the ranker.
- **Money:** all of this is free to run today. If traffic grows large, the free proxy bandwidth on Netlify is the first limit to check.
