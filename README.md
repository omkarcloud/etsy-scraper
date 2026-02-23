![Etsy Scraper Featured Image](https://raw.githubusercontent.com/omkarcloud/etsy-scraper/master/etsy-scraper-featured-image.png)

# Etsy Scraper API

Scrape Etsy listings, prices, tags, shop info, and 10 status flags via a simple REST API. 5,000 free requests/month.

## Key Features

- Search Etsy listings by keyword
- Get 20+ data points per listing (price, tags, categories, shop info, images, status flags)
- Favorites count, category path, and 10 boolean status flags per listing
- **5,000 requests/month on free tier**
- Example Response:
```json
{
    "listing_id": "893790449",
    "name": "Turquoise Ring, 925 Silver Ring, Handmade Ring, Gemstone Ring, Turquoise Jewelry, Boho Ring, Silver Band, Designer Band, Gift For Her",
    "url": "https://www.etsy.com/listing/893790449/turquoise-ring-925-silver-ring-handmade",
    "price": 40.0,
    "price_usd": 40.0,
    "currency": "USD",
    "favorites_count": 0,
    "tags": ["Turquoise Ring", "925 Silver Ring", "Handmade Ring", "Gemstone Ring"],
    "categories": ["jewelry", "rings", "bands"],
    "shop": {
        "shop_id": 25231883,
        "name": "newjewelshop"
    },
    "flags": {
        "active": true,
        "in_stock": true,
        "sold_out": false,
        "bestseller": false,
        "made_to_order": false
    }
}
```

## Get API Key

Create an account at [omkar.cloud](https://www.omkar.cloud/auth/sign-up?redirect=/api-key) to get your API key.

It takes just 2 minutes to sign up. You get 5,000 free requests every month for detailed Etsy data — more than enough for most users to get their job done without paying a dime.

This is a well built product, and your search for the best Etsy Scraper API ends right here.


## Quick Start

```bash
curl -X GET "https://etsy-scraper.omkar.cloud/etsy/search?keyword=handmade%20ring" \
  -H "API-Key: YOUR_API_KEY"
```

```json
{
  "result_count": 10000,
  "listings": [
    {
      "listing_id": "893790449",
      "name": "Aquamarine Ring, Crystal Ring, Dainty Handmade Ring, Handmade Ring, Boho Ring, Handmade Wire Ring, Simple Ring, Handmade Ring"
    }
  ]
}
```

## Quick Start (Python)

```bash
pip install requests
```

```python
import requests

# Search for listings
response = requests.get(
    "https://etsy-scraper.omkar.cloud/etsy/search",
    params={"keyword": "handmade ring"},
    headers={"API-Key": "YOUR_API_KEY"}
)

print(response.json())
```


## API Reference

### Search Listings

```
GET https://etsy-scraper.omkar.cloud/etsy/search
```

#### Parameters

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `keyword` | Yes | — | Search phrase to find matching Etsy listings. |

#### Example

```python
import requests

response = requests.get(
    "https://etsy-scraper.omkar.cloud/etsy/search",
    params={"keyword": "handmade ring"},
    headers={"API-Key": "YOUR_API_KEY"}
)

print(response.json())
```

#### Response

<details>
<summary>Sample Response (click to expand)</summary>

```json
{
  "result_count": 10000,
  "listings": [
    {
      "listing_id": "893790449",
      "name": "Aquamarine Ring, Crystal Ring, Dainty Handmade Ring, Handmade Ring, Boho Ring, Handmade Wire Ring, Simple Ring, Handmade Ring"
    },
    {
      "listing_id": "949066317",
      "name": "Dainty Handmade Ring, Handmade Ring, Boho Ring, Handmade Wire Ring, Simple Ring, Minimalist Ring, Hippie Ring, Handmade Band Ring"
    },
    {
      "listing_id": "863456037",
      "name": "Handmade Silver Ring, Handmade Ruby Ring, Handmade Sterling Silver Ring, Indian Handmade Ring,"
    }
  ]
}
```

</details>

---

### Listing Details

```
GET https://etsy-scraper.omkar.cloud/etsy/listing
```

#### Parameters

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `listing_id` | Yes | — | Unique numeric identifier for the Etsy listing. |

#### Example

```python
import requests

response = requests.get(
    "https://etsy-scraper.omkar.cloud/etsy/listing",
    params={"listing_id": "893790449"},
    headers={"API-Key": "YOUR_API_KEY"}
)

print(response.json())
```

#### Response Fields

Returns 20+ fields including price, tags, categories, shop info, images, 10 status flags, and timestamps.

<details>
<summary>Sample Response (click to expand)</summary>

```json
{
    "listing_id": "893790449",
    "name": "Turquoise Ring, 925 Silver Ring, Handmade Ring, Gemstone Ring, Turquoise Jewelry, Boho Ring, Silver Band, Designer Band, Gift For Her",
    "url": "https://www.etsy.com/listing/893790449/turquoise-ring-925-silver-ring-handmade",
    "price": 40.0,
    "price_usd": 40.0,
    "currency": "USD",
    "favorites_count": 0,
    "tags": [
        "Turquoise Ring",
        "925 Silver Ring",
        "Handmade Ring",
        "Gemstone Ring",
        "Turquoise Jewelry",
        "Boho Ring",
        "Silver Band",
        "Designer Band",
        "Gift For Her",
        "Birthday Ring",
        "Antique Ring",
        "Anniversary Ring",
        "Promised Ring"
    ],
    "categories": [
        "jewelry",
        "rings",
        "bands"
    ],
    "images": {
        "full": "https://i.etsystatic.com/25231883/r/il/706249/2665253237/il_fullxfull.2665253237_l9st.jpg",
        "thumbnail": "https://i.etsystatic.com/25231883/d/il/706249/2665253237/il_75x75.2665253237_l9st.jpg?version=0"
    },
    "shop": {
        "shop_id": 25231883,
        "name": "newjewelshop",
        "opened_at": null
    },
    "flags": {
        "active": true,
        "in_stock": true,
        "sold_out": false,
        "digital": false,
        "made_to_order": false,
        "bestseller": false,
        "top_rated": false,
        "featured": false,
        "on_vacation": false,
        "taxable": true
    },
    "listed_at": "2020-10-27T10:30:00+00:00",
    "refreshed_at": "2020-11-12T09:41:06+00:00",
    "last_crawled_at": "2020-12-25T17:26:39+00:00"
}
```

</details>

## Error Handling

```python
response = requests.get(
    "https://etsy-scraper.omkar.cloud/etsy/search",
    params={"keyword": "handmade ring"},
    headers={"API-Key": "YOUR_API_KEY"}
)

if response.status_code == 200:
    data = response.json()
elif response.status_code == 401:
    # Invalid API key
    pass
elif response.status_code == 429:
    # Rate limit exceeded
    pass
```

## FAQs

### What data does the API return?

**Search Listings** returns total result count, listing ID, and name for each match.

**Listing Details** returns 20+ fields — listing name, URL, price in USD, currency code, favorites count, up to 12 tags, full category path, full-size image and thumbnail URLs, shop ID, shop name, shop opening date, 10 status flags (active, in stock, sold out, digital, made-to-order, bestseller, top rated, featured, on vacation, taxable), and timestamps for listing creation, last update, and last crawl.

All in structured JSON. Ready to use in your app.

### How accurate is the data?

Data is pulled from Etsy in real time. Every API call fetches live data — not cached or stale results. Prices, availability, tags, and status flags reflect what's on Etsy right now.

### Can I use listing IDs from search in the details endpoint?

Yes. That's the intended workflow. Search for listings by keyword, grab the `listing_id` from any result, and pass it to the Listing Details endpoint to get the full breakdown.

### What do the status flags mean?

The `flags` object gives you 10 boolean indicators about a listing's current state: **active** (live on Etsy), **in_stock** (available for purchase), **sold_out** (all inventory gone), **digital** (digital download), **made_to_order** (created after purchase), **bestseller** (Etsy bestseller badge), **top_rated**, **featured** (by shop owner), **on_vacation** (shop in vacation mode), and **taxable**.

## Rate Limits

| Plan | Price | Requests/Month |
|------|-------|----------------|
| Free | $0 | 5,000 |
| Starter | $25 | 100,000 |
| Grow | $75 | 1,000,000 |
| Scale | $150 | 10,000,000 |

## Questions? We have answers.

Reach out anytime. We will solve your query within 1 working day.

[![Contact Us on WhatsApp about Etsy Scraper](https://raw.githubusercontent.com/omkarcloud/assets/master/images/whatsapp-us.png)](https://api.whatsapp.com/send?phone=918178804274&text=I%20have%20a%20question%20about%20the%20Etsy%20Scraper%20API.)

[![Contact Us on Email about Etsy Scraper](https://raw.githubusercontent.com/omkarcloud/assets/master/images/ask-on-email.png)](mailto:happy.to.help@omkar.cloud?subject=Etsy%20Scraper%20API%20Question)
