# Talaro

**Search everything. In your language.**

Talaro is a free search engine for Pakistan and India in 13 languages. No sign-up, no tracking, no server. The whole app is one `index.html` file.

**Live:** https://talaro.netlify.app

## What it does

- **Search in your language:** English, Hindi, Urdu, Punjabi, Bengali, Tamil, Telugu, Marathi, Gujarati, Kannada, Malayalam, Pashto and Sindhi. Switch in one tap. Right-to-left languages work properly.
- **Nine tabs:** All, Images, Videos, News, Papers, Books, Places, Forums, Translate.
- **Instant answers:** weather, prayer times, currency, calculator, units, dictionary, India PIN codes and IFSC bank codes.
- **Trending today** for your language.
- **Install as an app** on Android, iPhone and desktop.
- **Private:** your history stays on your device.
- **Fallback links:** every result page links to the same search on Google, Bing, DuckDuckGo, Brave, Yandex, Baidu and YouTube.

## How it works

Talaro is a meta-search engine that runs entirely in the browser. It calls about 45 free public APIs that need no key, merges the results, removes duplicates and ranks them with its own scoring (term relevance, phrase match, freshness, popularity, region and language). The "Why this result?" button shows the reasons for each result.

Sources include Wikipedia, Wikimedia Commons, Wikinews, Wikisource, Wikivoyage, Mwmbl, GDELT, Openverse, NASA Images, Art Institute of Chicago, SepiaSearch, Crossref, Europe PMC, Semantic Scholar, DOAJ, Zenodo, arXiv, Internet Archive, Open Library, Google Books, Project Gutenberg, GitHub, npm, Stack Overflow, Hacker News, Nominatim, Photon, Open-Meteo, Aladhan, dictionaryapi.dev, Lingva, MyMemory and more.

Click **Check data sources** in the footer to see which sources are working right now. A source that is down is skipped without breaking the page.

## Run it

Open `index.html` in a browser. That is all.

## Deploy

Drag a folder containing `index.html` onto https://app.netlify.com/drop.

Optional: add a `_redirects` file to enable extra news sources (Google News, Bing News, Marginalia):

```
/api/gnews      https://news.google.com/rss/search         200!
/api/bingnews   https://www.bing.com/news/search           200!
/api/marginalia https://api2.marginalia-search.com/search  200!
```

## Limits

- Talaro combines other sites' public data. It does not have its own web crawler, so coverage is smaller than Google's.
- Free APIs can change, slow down or go offline.
- The non-English interface text is machine-written and needs review by native speakers. Corrections are welcome.

## Contributing

Issues and pull requests are welcome, especially:
- Interface translation fixes
- New free, key-less data sources
- Ranking improvements

## License

MIT

Built by Hassan Khan, Lahore, Pakistan.
