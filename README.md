# GoQuant Assignment: Fear & Greed Sentiment Engine

This project is a proof-of-concept for a sentiment analysis and trade signal generation system, completed as part of the GoQuant software engineer internship application process.

The system ingests data from social media (Reddit) and financial markets (Yahoo Finance), analyzes sentiment, and generates simple trade signals based on a "Fear & Greed" proxy.

---

## 🚀 System Architecture

The project is implemented as a Python script within a Google Colab notebook, demonstrating a sequential data processing pipeline.

1.  **Data Ingestion**: Fetches posts from `r/CryptoCurrency` and historical price data for `BTC-USD`.
2.  **Sentiment Analysis**: Each post's text is analyzed using the VADER model to produce a compound sentiment score (-1 to +1).
3.  **Data Aggregation**: Sentiment scores are aggregated into a single average score for each day.
4.  **Signal Generation**: A simplified "Fear & Greed" index is created by comparing a short-term moving average of sentiment to a long-term one. "Buy" signals are generated on a "Fear" proxy and "Sell" signals on a "Greed" proxy.
5.  **Visualization**: The results are plotted on a chart showing the asset's price, sentiment, and trade signals.

---

## 🛠️ Technical Decisions

* **Language (Python)**: Chosen for its powerful data science ecosystem (`pandas`, `yfinance`) and rapid development capabilities.
* **Environment (Google Colab)**: Used for its free-tier access to computational resources and easy, reproducible setup.
* **Sentiment Model (VADER)**: Selected because it is lightweight, fast, and specifically tuned for social media text, making it perfect for a proof-of-concept.
* **Single-Threaded Design**: For this MVP, a simple, sequential pipeline was implemented. A production system would use multi-threading or `asyncio` to ingest data from multiple sources concurrently.

---

## 🔮 Future Work

* **Expanded Data Sources**: Integrate Twitter, news APIs, and real-time fund flow data.
* **Advanced NLP**: Implement models like FinBERT and Named Entity Recognition (NER) to improve accuracy and automatically tag assets.
* **Robust Backtesting**: Develop a proper backtesting engine to evaluate the profitability and risk metrics of the generated signals.
