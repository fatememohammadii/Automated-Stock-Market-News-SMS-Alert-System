# Automated Stock Market News SMS Alert System

## Project Overview

This Python project provides an automated monitoring and alert system for stock price movements. It tracks daily closing price fluctuations for a target stock (e.g., Tesla / `TSLA`). When a significant price movement is detected, the script automatically fetches top relevant news headlines and dispatches instant updates via SMS/WhatsApp using the Twilio API.

---

## Key Features

* **Stock Movement Tracking:** Fetches daily closing prices from Alpha Vantage API and calculates percentage variations between consecutive trading days.
* **Targeted News Fetching:** Queries the News API for recent articles referencing the company when stock price changes exceed a defined threshold.
* **Automated Notifications:** Formats key headlines with custom directional indicators (🔺/🔻) and delivers messages directly to a phone or WhatsApp account via Twilio.

---

## Project Workflow

1. **Fetch Market Data:**
* Calls the Alpha Vantage `TIME_SERIES_DAILY` endpoint.


* Compares yesterday's closing price with the day prior to calculate price difference and percentage shift.




2. **Trigger Condition & News Filtering:**
* Evaluates if the price variance breaches the threshold percentage.


* If triggered, requests latest articles from News API matching the company name.


* Extracts the top 3 relevant articles.




3. **Format & Dispatch:**
* Constructs formatted message payloads including stock ticker, percentage change, news headline, and brief summary.


* Dispatches each payload as an SMS/WhatsApp message via Twilio Client.





---

## Tech Stack & APIs

* **Language:** Python 3


* **Libraries:** `requests`, `twilio`


* **APIs Used:**
* [Alpha Vantage API](https://www.alphavantage.co/?utm_source=gemini) (Stock market data)


* [News API](https://newsapi.org/?utm_source=gemini) (Real-time news articles)


* [Twilio API](https://www.twilio.com/?utm_source=gemini) (SMS/WhatsApp Messaging Service)





---

## Setup & Environment Variables

### Prerequisites

Install required Python dependencies:

```bash
pip install requests twilio

```

### Configuration

Update the script configuration or set environment variables for your credentials:

```python
STOCK_NAME = "TSLA"
COMPANY_NAME = "Tesla Inc"

STOCK_API_KEY = "YOUR_ALPHA_VANTAGE_KEY"
NEWS_API_KEY = "YOUR_NEWS_API_KEY"

TWILIO_SID = "YOUR_TWILIO_ACCOUNT_SID"
TWILIO_AUTH_TOKEN = "YOUR_TWILIO_AUTH_TOKEN"

```

---

## Sample Message Output

```text
TSLA: 🔺5%
Headline: Were Hedge Funds Right About Piling Into Tesla Inc. (TSLA)?
Brief: An analysis of recent portfolio filings regarding major positions following market movements.

```

---

## Usage Instructions

Run the script manually or schedule it as a daily cron job:

```bash
python stock-data.py

```
