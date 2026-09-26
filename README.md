# 📰 NewsAggre

NewsAggre is a **robust Java desktop application** designed to aggregate, parse, group, and analyze news articles from live RSS feeds. Built with a rich graphical user interface (Swing), it features advanced story-grouping algorithms, metadata tagging, industry classification, and custom reporting tools.

## 🚀 Key Architectural Features

* **Live RSS Engine (`RssFetcher`)**: Asynchronously fetches and parses live XML/JSON article feeds with built-in network safety and progress monitoring.
* **Intelligent Data Pipeline**:
  * **Story Grouper (`StoryGrouper`)**: Automatically identifies related articles and groups them into unified news stories.
  * **Summarizer (`Summarizer` & `QuoteExtractor`)**: Extracts core highlights, metrics, and relevant direct quotes from article bodies.
  * **Industry Tagger (`IndustryTagger`)**: Scans article context to classify feeds into financial, technology, or custom market sectors.
* **System Lifecycle Monitoring (`LifecycleAnalyzer`)**: Tracks application states, feed health metrics, and background task performances visualized using a custom interface (`LifecycleGauge`).
* **Advanced Document Exporting (`OfficeExporter`)**: Generates and exports structured news summaries and aggregated briefs straight into Microsoft Office formats.
* **Interactive UI Layers (`MainFrame`)**: Implements an optimized, multi-threaded workspace complete with structural outlines (`OutlineBuilder`), custom rendering tables, and clean metadata tag chips.

## 🛠️ Built With

* **Java SE** (JDK 8 or higher) [1]
* **NetBeans IDE** - Built-in project configuration paths [1]
* **Java Swing & AWT** - For the interactive dashboard interface [1]

## 💻 Setup & Local Execution

1. **Clone this project repository** to your local Windows system:
   ```bash
   git clone https://github.com
   ```

2. **Open the project in NetBeans**:
   * Launch **NetBeans IDE**.
   * Navigate to `File > Open Project`.
   * Select the root `newsaggre` directory and click **Open**.

3. **Compile and Run**:
   * Press **`F6`** or click the green **Play** icon in NetBeans to clean, compile, and execute the desktop workspace.

## 📂 Project Structure Snapshot
```text
newsaggre/
├── src/newsaggre/
│   ├── App.java                   # Main entry point [1]
│   ├── MainFrame.java             # Graphical UI Dashboard [1]
│   ├── RssFetcher.java            # Network content streaming [1]
│   ├── StoryGrouper.java          # Article grouping logic [1]
│   ├── LifecycleAnalyzer.java     # App performance and metrics monitoring [1]
│   └── OfficeExporter.java        # MS Office document exporting pipeline [1]
└── build.xml                      # NetBeans compilation definitions [1]
```

## 👥 Authors
* **marsdux** - Core Software Architecture & Development [1]
