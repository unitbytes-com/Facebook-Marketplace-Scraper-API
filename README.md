# 🛒 Facebook Marketplace Scraper API

<div align="center">

[![Available on Apify](https://img.shields.io/badge/Available_on-Apify-28B52A?style=for-the-badge&logo=apify&logoColor=white)](https://apify.com/unitbytes/facebook-marketplace-scraper)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg?style=for-the-badge)](https://apify.com/unitbytes/facebook-marketplace-scraper)
[![No Login Required](https://img.shields.io/badge/Login_Required-No-success.svg?style=for-the-badge)](https://apify.com/unitbytes/facebook-marketplace-scraper)
[![Cost Efficient](https://img.shields.io/badge/Cheapest%20%26%20Fastest-Yes-blue.svg?style=for-the-badge)](https://apify.com/unitbytes/facebook-marketplace-scraper)

**The fastest and most cost-effective Facebook Marketplace Scraper on Apify. Extract 40+ fields per listing including seller intelligence, vehicle specs, and HD images. No login required.**

[**🚀 Try it for free on Apify**](https://apify.com/unitbytes/facebook-marketplace-scraper?fpr=939u3w&fp_sid=20260605)

</div>

---

## 📖 Overview

Are you looking to extract data from Facebook Marketplace for lead generation, market research, price monitoring, or dropshipping? 

This robust scraper allows you to collect data from **any category** (Vehicles, Real Estate, Furniture, Electronics) at scale. It uses concurrent processing and a lightweight API-driven engine to deliver results instantly, bypassing the need for Facebook accounts or slow headless browsers.

### 🚀 Why is this the best choice?
> [!IMPORTANT]
> **Cheapest & Fastest on the Market**: Most Facebook scrapers use slow, heavy browsers that eat up compute time and expensive proxy bandwidth. Our scraper is built completely differently. We use a lightweight, API-driven engine that extracts data directly. Because it uses a fraction of the resources, you get your datasets at lightning speed while paying significantly less per run!

## ✨ Key Features

- **⚡ Lightning Fast & Cheap**: No headless browsers means virtually no wasted proxy bandwidth or compute time. Get results in minutes, not hours.
- **🛡️ No Login Required**: Runs completely anonymously. No risk of getting your personal account banned.
- **📦 40+ Data Fields**: The most comprehensive data extraction available.
- **🕵️ Seller Intelligence**: Get seller ratings, review counts, join dates, and locations.
- **🚗 Auto-Enriched Vehicle Data**: Automatically extracts VIN, mileage, transmission, engine details, and clean title status.
- **🔗 Copy-Paste URL Intelligence**: Just drop a Facebook Marketplace URL into the scraper and it will flawlessly pass your custom filters (`make`, `model`, etc.) directly into the scraping engine.
- **🚀 Bypasses the 1,000 Listing Cap**: Our engine automatically sweeps the entire market natively to extract tens of thousands of listings without missing a single item.
- **⚡ High-Speed Concurrency**: Run up to 10 parallel threads to extract thousands of listings instantly.
- **🌐 Any Location Worldwide**: Search by `city_slug` and radius, or just paste a direct Facebook search URL!

## 💡 Use Cases

- **Used Car Dealerships**: Monitor local inventory, track competitor pricing, and find underpriced vehicles to flip.
- **Real Estate & Rentals**: Scrape local rental listings and property availability.
- **E-commerce & Dropshipping**: Identify trending products and monitor local market prices.
- **Market Research**: Analyze supply and demand for specific item categories in different cities.

## 🛠️ How to use it (API Examples)

You can run this scraper via the [Apify Console](https://apify.com/unitbytes/facebook-marketplace-scraper), or integrate it directly into your own applications using Apify's API.

### Python Integration

```python
from apify_client import ApifyClient

# Initialize the ApifyClient with your API token
client = ApifyClient("YOUR_APIFY_API_TOKEN")

# Prepare the Actor input
run_input = {
    "start_urls": [{"url": "https://www.facebook.com/marketplace/sanfrancisco/vehicles/?make=1274042129420222"}],
    "search_query": "honda civic",
    "city_slug": "sanfrancisco",
    "min_price": 2000,
    "max_price": 15000,
    "max_results": 50,
    "concurrency": 5,
    "days_since_listed": 3
}

# Run the Actor and wait for it to finish
run = client.actor(\"unitbytes/facebook-marketplace-scraper\").call(run_input=run_input)

# Fetch and print Actor results from the run's dataset
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

### Node.js Integration

```javascript
import { ApifyClient } from 'apify-client';

// Initialize the ApifyClient with your API token
const client = new ApifyClient({
    token: 'YOUR_APIFY_API_TOKEN',
});

// Prepare the Actor input
const input = {
    "start_urls": [{"url": "https://www.facebook.com/marketplace/sanfrancisco/vehicles/?make=1274042129420222"}],
    "search_query": "honda civic",
    "city_slug": "sanfrancisco",
    "min_price": 2000,
    "max_price": 15000,
    "max_results": 50,
    "concurrency": 5,
    "days_since_listed": 3
};

// Run the Actor and wait for it to finish
const run = await client.actor(\"unitbytes/facebook-marketplace-scraper\").call(input);

// Fetch and print Actor results from the run's dataset
const { items } = await client.dataset(run.defaultDatasetId).listItems();
items.forEach((item) => {
    console.dir(item);
});
```

## 📈 Sample Output Data

### 🖼️ Apify Dataset View
![Apify Dataset Preview](https://raw.githubusercontent.com/unitbytes-com/Facebook-Marketplace-Scraper-API/main/assets/Facebook_MarketPlace_Scraper.png)

The API returns clean, structured JSON data. Here is an example of an extracted vehicle listing:

```json
{
  "title": "2019 Honda Civic EX",
  "price": "$8,500",
  "seller_name": "Lawrence",
  "seller_rating": 4.6,
  "listing_age": "on Thursday",
  "category": "Vehicles",
  "make": "Honda",
  "model": "Civic",
  "year": 2019,
  "mileage": "45000",
  "vin": "2HGFC2F5XKH...",
  "url": "https://www.facebook.com/marketplace/item/982185697762732/"
}
```

## 🤝 Support and Custom Solutions

If you encounter any bugs, please [open an issue on Apify](https://apify.com/unitbytes/facebook-marketplace-scraper/issues). 

Need a custom scraping solution or enterprise integration? Feel free to reach out via [Apify](https://apify.com/unitbytes/facebook-marketplace-scraper).

---
*Disclaimer: This tool is for educational and research purposes only. Please scrape responsibly and respect Facebook's terms of service.*
