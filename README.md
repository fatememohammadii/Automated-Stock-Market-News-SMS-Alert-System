# Automated Stock Market News SMS Alert System

## Project Overview
This Python project provides an automated monitoring and alert system for stock price movements. It tracks daily closing price fluctuations for a target stock (e.g., Tesla / `TSLA`). When a significant price movement is detected, the script automatically fetches top relevant news headlines and dispatches instant updates via SMS or WhatsApp using the Twilio API.

---

## Technical Features
* **Stock Movement Analysis:** Retrieves daily closing prices from the Alpha Vantage API and calculates percentage variations between consecutive trading days.
* **Contextual News Fetching:** Queries the News API for recent news articles referencing the target company when price shifts exceed a specified threshold.
* **Automated Notifications:** Formats key headlines with directional indicators (🔺/🔻) and delivers messages directly to a phone or WhatsApp account via Twilio.
* **Secure Credential Handling:** Utilizes system environment variables to prevent hardcoding API keys and sensitive tokens.

---

## Tech Stack & APIs
* **Language:** Python 3
* **Libraries:** `requests`, `twilio`
* **APIs Used:**
  * [Alpha Vantage API](https://www.alphavantage.co/) (Stock market data)
  * [News API](https://newsapi.org/) (Real-time news articles)
  * [Twilio API](https://www.twilio.com/) (SMS/WhatsApp Messaging Service)

---

## Setup & Configuration

### 1. Prerequisites
Install required dependencies:
```bash
pip install requests twilio

```

### 2. Environment Variables

To keep API credentials secure, set the following environment variables on your system or inside a `.env` file (ensure your `.env` is listed in `.gitignore`):

```bash
export STOCK_API_KEY="your_alpha_vantage_key"
export NEWS_API_KEY="your_news_api_key"
export TWILIO_SID="your_twilio_account_sid"
export TWILIO_AUTH_TOKEN="your_twilio_auth_token"

```

---

## Sample Message Output

```text
TSLA: 🔺5%
Headline: Were Hedge Funds Right About Piling Into Tesla Inc. (TSLA)?
Brief: An analysis of recent portfolio filings regarding major positions following market movements.

```

---

## Execution

Run the script manually or configure it as a scheduled daily job:

```bash
python stock-data.py

```

```

```
