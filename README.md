# NewsAggre

A Java Swing desktop app that reads **CNBC's free public RSS feeds** and turns each headline into a structured outline: key takeaways, verbatim quotes, a PESTEL read, sector tags, connected-story grouping and a time-decaying importance score.

Everything is **rule-based**. There is no LLM, no API key and no external library. The app compiles and runs with only the JDK.

<!--
Add screenshots after you upload them to a docs/ folder, then remove these comment markers:
![Main window](docs/main-window.png)
![Outline view](docs/outline.png)
-->

## Features

- **Free content only:** fetches CNBC's public RSS feeds (never CNBC Pro or paywalled stories) and, where possible, the full article text and lead image. If a full-page fetch is blocked, it falls back to the RSS title and description.
- **Key-takeaway outlines:** an extractive, word-frequency summarizer picks the most informative sentences and drops redundant ones.
- **Categorized outline:** Key Event, Market Analysis and Impact, Figures and Data, Outlook, and a **PESTEL** read (political, economic, social, technological, environmental, legal) based on what the article actually contains.
- **Verbatim quotes:** quoted text is extracted exactly, not paraphrased.
- **Connected stories:** articles about the same event are grouped using keyword overlap, so follow-ups are merged.
- **Sector tagging:** up to three industry or market-sector tags per article.
- **Life-cycle score:** an importance score that decays over time unless the story's cluster keeps growing, in which case it is marked **Developing**.
- **Save and retrieve:** generated outlines are stored locally and can be reopened by article title.
- **Export and print:** export to **Excel (`.xlsx`)** and **Word (`.docx`)**, written directly without Apache POI, and print from the app.
- **Safer by design:** URL validation, size-bounded network reads, a restricted deserialization filter and atomic file writes.

> The score, tags and outlines come from keyword rules. Treat them as a scanning aid, not as financial advice or a verified measure of market impact.

## Getting started

**Requirements:** JDK 17 or newer. NetBeans is optional.

1. Clone the repository:

   ```bash
   git clone https://github.com/marsdux/news-aggre.git
   ```

2. In NetBeans, choose *File > Open Project* and select the `newsaggre` folder.
3. Press `F6` to build and run, or use Ant:

   ```bash
   cd newsaggre
   ant jar
   java -jar dist/newsaggre.jar
   ```

The main class is `newsaggre.App`. Saved articles and outlines are stored locally on your machine.

## Project structure

```text
newsaggre/src/newsaggre/
├── App.java, MainFrame.java        entry point and main window
├── FeedCatalog.java, RssFetcher.java   feed list and fetching
├── Summarizer.java, QuoteExtractor.java, OutlineBuilder.java   outline generation
├── StoryGrouper.java, IndustryTagger.java, LifecycleAnalyzer.java   grouping, tags, score
├── OutlineService.java, OutlineDatabase.java, ArticleStore.java   saving and retrieval
├── OfficeExporter.java, PrintUtil.java   export and printing
└── UrlSafety.java, BoundedReader.java, SerializationSafety.java   safety helpers
```

## Notes

This project is not affiliated with CNBC. Use it in line with CNBC's terms of use.

## Author

Built by [@marsdux](https://github.com/marsdux).
