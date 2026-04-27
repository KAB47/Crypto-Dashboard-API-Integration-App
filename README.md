# Crypto Market Tracker

A Jupyter Notebook that fetches live cryptocurrency data from the **[CoinMarketCap API](https://coinmarketcap.com/api/)**, processes it into a structured DataFrame, and visualises price performance across multiple timeframes.

## TL;DR

Add your CoinMarketCap API key, run the notebook, and get a live table + chart of the top 15 cryptocurrencies with price changes across 1h, 24h, 7d, 30d, 60d, and 90d timeframes.

## Features

* Fetch live listings for the top 15 cryptocurrencies by market cap
* Track price, volume, market cap, supply, and percent changes across 6 timeframes: `1h`, `24h`, `7d`, `30d`, `60d`, `90d`
* Clean DataFrame output with full column visibility
* Point-plot visualisations comparing coin performance across timeframes
* Timestamped data pulls for potential longitudinal tracking

## Prerequisites

Ensure you have the following installed:

* Python 3.6 or later
* Required Python libraries: `requests`, `pandas`, and `seaborn`
* A valid **CoinMarketCap Pro API key** — sign up at [coinmarketcap.com/api](https://coinmarketcap.com/api/)

You can install the required libraries using pip:

```
pip install requests pandas seaborn
```

## Setup

1. Clone or download the project folder
2. Open the notebook in Jupyter:

```bash
jupyter notebook Test_Notebook.ipynb
```

3. In the first cell, replace the placeholder with your CoinMarketCap API key:

```python
headers = {
  'Accepts': 'application/json',
  'X-CMC_PRO_API_KEY': 'YOUR_API_KEY_HERE',
}
```

4. Run the notebook cells in order

## Output

The notebook will produce:

* A structured Pandas DataFrame containing market data for the top 15 coins
* A point-plot chart visualising percent change across coins and timeframes

## Error Handling

* If the API key is invalid or missing, a connection error will be raised
* If the API rate limit is exceeded, a `TooManyRedirects` error will be caught and printed
* If no data is returned for the requested parameters, the response body will indicate the issue

```

## Notes

* Ensure your CoinMarketCap account has access to the `/v1/cryptocurrency/listings/latest` endpoint
* The default configuration fetches the top 15 coins converted to USD — this can be adjusted via the `parameters` dict in the first cell
* A sandbox API URL is included as a comment for testing without consuming real API credits
