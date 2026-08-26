<p align="center">
  <img src="https://raw.githubusercontent.com/omkarcloud/botasaurus/master/images/mascot.png" alt="etsy scraper" />
</p>
<div align="center" style="margin-top: 0;">
  <h1>✨ Etsy Scraper 🤖</h1>
  <p><strong>Scrape Etsy search results, listing details, prices, ratings, reviews, and shop data in real time — across 26 regional sites, in any currency. Clean JSON, no blocks, no proxies.</strong></p>
</div>
<em>
  <h5 align="center">(Programming Language - Python 3)</h5>
</em>
<p align="center">
  <a href="#">
    <img alt="etsy-scraper forks" src="https://img.shields.io/github/forks/omkarcloud/etsy-scraper?style=for-the-badge" />
  </a>
  <a href="#">
    <img alt="Repo stars" src="https://img.shields.io/github/stars/omkarcloud/etsy-scraper?style=for-the-badge&color=yellow" />
  </a>
</p>
<p align="center">
  <img src="https://views.whatilearened.today/views/github/omkarcloud/etsy-scraper.svg" width="80px" height="28px" alt="View" />
</p>

Etsy Scraper turns any keyword into clean JSON, pulled live from Etsy — no blocks, no proxies to manage. Autocomplete a partial phrase into Etsy's own search suggestions, list every matching listing 48 at a time with prices, sale discounts, and ratings, and pull full listing details — description, every image, variations, materials, recent reviews, shop stats, and delivery estimate — all via one API.

It works across **26 Etsy regional sites** — `us`, `uk`, `de`, `fr`, `jp`, `in`, `au`, and 19 more — and prices come back numeric in the locale's home currency, or converted to any display currency you pick (`USD`, `EUR`, `GBP`, `INR`, ...).

- **Rated Excellent — 4.6 based on 25 reviews** on [Trustpilot](https://www.trustpilot.com/review/omkar.cloud). Our open source work is sponsored by [1000+ devs on GitHub](https://github.com/sponsors/omkarcloud).

[![Try the Etsy Scraper API in the live playground — free, no signup](https://img.shields.io/badge/%E2%96%B6%20Playground-Run%20a%20live%20request%2C%20free-brightgreen?style=for-the-badge)](https://www.omkar.cloud/tools/etsy-scraper/playground?utm_source=github&utm_medium=cpc&utm_content=badge)

[![Free Plan: 100 requests per month](https://img.shields.io/badge/Free%20tier-100%20requests%2Fmonth-blue?style=for-the-badge)](#pricing)

The same scraper is also available on **Apify** and **RapidAPI**:

[![Run on Apify](https://img.shields.io/badge/Run%20on-Apify-blue)](https://apify.com/omkar-cloud/etsy-scraper) [![Run on RapidAPI](https://img.shields.io/badge/Run%20on-RapidAPI-blue?logo=rapidapi)](https://rapidapi.com/Chetan11dev/api/etsy-api/playground)

[![Etsy Scraper API — scrape Etsy listings, prices, ratings, and reviews into JSON](https://raw.githubusercontent.com/omkarcloud/etsy-scraper/master/etsy-scraper-featured-image.png)](https://www.omkar.cloud/tools/etsy-scraper/playground?utm_source=github&utm_medium=cpc&utm_content=hero-image)

## Example: Etsy Search Data in One Request

One request to the search API:

```
GET https://etsy-scraper.omkar.cloud/etsy/search?query=jewelry
```

```json
{
  "count": 450308,
  "per_page": 48,
  "current_page": 1,
  "total_pages": 250,
  "next": "https://etsy-scraper.omkar.cloud/etsy/search?query=jewelry&locale=us&page=2",
  "previous": null,
  "query": "jewelry",
  "locale": "us",
  "currency": "USD",
  "results": [
    {
      "id": "550059739",
      "title": "14k Gold Diamond Solitaire Necklace: Dainty Bridal Jewelry",
      "link": "https://www.etsy.com/listing/550059739/14k-gold-diamond-solitaire-necklace",
      "image": {
        "link": "https://i.etsystatic.com/7003748/r/il/febe6d/4441477806/il_255x319.4441477806_h0w5.jpg",
        "large_link": "https://i.etsystatic.com/7003748/r/il/febe6d/4441477806/il_794xN.4441477806_h0w5.jpg"
      },
      "video_link": "https://v.etsystatic.com/video/upload/ac_none,du_15,q_auto:good/file_audee1.mp4",
      "pricing": {
        "amount": 80.08,
        "original_amount": 114.4,
        "discount_percent": 30,
        "currency": "USD"
      },
      "rating": { "value": 5.0, "review_count": 20700 },
      "badge": "Popular now",
      "shop": {
        "id": "7003748",
        "name": "DIAMONDFORLOVE",
        "link": "https://www.etsy.com/shop/DIAMONDFORLOVE"
      },
      "is_sponsored": true,
      "has_free_shipping": true
    },
    {
      "id": "4306368113",
      "title": "Birth Flower Ring 925 Sterling Silver Mother of Pearl Sakura Rings Adjustable Delicate Personalized Birthstone Gift",
      "link": "https://www.etsy.com/listing/4306368113/birth-flower-ring-925-sterling-silver",
      "image": {
        "link": "https://i.etsystatic.com/14792900/r/il/153030/7389351270/il_255x319.7389351270_gz4k.jpg",
        "large_link": "https://i.etsystatic.com/14792900/r/il/153030/7389351270/il_794xN.7389351270_gz4k.jpg"
      },
      "video_link": null,
      "pricing": {
        "amount": 29.4,
        "original_amount": 42.0,
        "discount_percent": 30,
        "currency": "USD"
      },
      "rating": { "value": 4.7, "review_count": 8900 },
      "badge": "Popular now",
      "shop": {
        "id": "14792900",
        "name": "PBJewelryGift",
        "link": "https://www.etsy.com/shop/PBJewelryGift"
      },
      "is_sponsored": false,
      "has_free_shipping": true
    }
  ]
}
```

*Trimmed for readability — a real page returns 48 listings. See the full samples in the [API reference](#api-reference).*

Every card carries the listing's price with strikethrough original and discount percent when it's on sale, the rating with review count, the shop behind it, and sponsored/free-shipping flags — the same numbers a visitor sees on Etsy right now.

**[Run this exact request in the Playground — no signup, no key →](https://www.omkar.cloud/tools/etsy-scraper/playground?utm_source=github&utm_medium=cpc&utm_content=example)**

The playground comes prefilled with this request and runs it against the live API in your browser. The JSON it returns is identical to what the API returns.

## Start Getting Data in Minutes

Python and Node.js integration examples are available for every endpoint in the playground, so you can get Etsy data in minutes instead of days.

```python
import requests

# Scrape Etsy listings for a keyword
response = requests.get(
    "https://etsy-scraper.omkar.cloud/etsy/search",
    params={"query": "jewelry"},
    headers={"API-Key": "YOUR_API_KEY"}
)

print(response.json())
```

## API Reference

### Autocomplete

Turn a partial phrase into Etsy's own search suggestions — ideal for keyword research and for expanding seed terms before calling Search Listings.

▶ [Try it live in the Playground — no key needed →](https://www.omkar.cloud/tools/etsy-scraper/playground?utm_source=github&utm_medium=cpc&utm_content=endpoint-autocomplete)

```
GET https://etsy-scraper.omkar.cloud/etsy/autocomplete?query=jewel
```

| Parameter | Description |
|-----------|-------------|
| `query` | Partial search phrase to complete — e.g. `jewel` |
| `locale` | Etsy regional site code (default `us`). Suggestions come back in that locale's language — `schmu` with locale `de` returns *schmuck*, *schmuckschatulle*, ... |

#### Response

<details>
<summary>Sample Response (click to expand)</summary>

```json
{
  "query": "jewel",
  "locale": "us",
  "count": 11,
  "results": [
    "jewelry",
    "jewelry box",
    "jewelry jar",
    "jewelry set",
    "jewellery",
    "jewelry gift",
    "jewelry holder",
    "jewellery box",
    "jewelry dish",
    "jewels",
    "jewelry making"
  ]
}
```

</details>

---

### Search Listings

▶ [Try it live in the Playground →](https://www.omkar.cloud/tools/etsy-scraper/playground?utm_source=github&utm_medium=cpc&utm_content=endpoint-search)

```
GET https://etsy-scraper.omkar.cloud/etsy/search?query=jewelry
```

Returns one full results page — 48 listings — with next/previous pagination links, up to 250 pages per query.

| Parameter | Description |
|-----------|-------------|
| `query` | Search phrase used to find matching Etsy listings — e.g. `jewelry` |
| `locale` | Etsy regional site code (default `us`): `us`, `uk`, `ca`, `ca-fr`, `au`, `nz`, `ie`, `de`, `at`, `fr`, `be-fr`, `es`, `mx`, `it`, `nl`, `pl`, `pt`, `jp`, `se`, `ru`, `in`, `in-en`, `sg`, `sg-en`, `hk`, `hk-en`. Sets the result language and the default display currency |
| `currency` | 3-letter display currency prices are converted to — `USD`, `EUR`, `GBP`, `CAD`, `AUD`, `INR`, ... Defaults to the locale's home currency (`us` → USD, `de` → EUR, `jp` → JPY) |
| `page` | Results page, `1`–`250` (48 listings per page) |

#### Response

Each of the 48 results carries the listing id, title, canonical URL, image in two sizes, video link, pricing (current amount plus strikethrough original and discount percent when on sale), rating with review count, badge (like "Popular now"), the shop's id/name/URL, and sponsored/free-shipping flags — plus the total match count and pagination links.

<details>
<summary>Sample Response (click to expand)</summary>

```json
{
  "count": 450308,
  "per_page": 48,
  "current_page": 1,
  "total_pages": 250,
  "next": "https://etsy-scraper.omkar.cloud/etsy/search?query=jewelry&locale=us&page=2",
  "previous": null,
  "query": "jewelry",
  "locale": "us",
  "currency": "USD",
  "results": [
    {
      "id": "550059739",
      "title": "14k Gold Diamond Solitaire Necklace: Dainty Bridal Jewelry",
      "link": "https://www.etsy.com/listing/550059739/14k-gold-diamond-solitaire-necklace",
      "image": {
        "link": "https://i.etsystatic.com/7003748/r/il/febe6d/4441477806/il_255x319.4441477806_h0w5.jpg",
        "large_link": "https://i.etsystatic.com/7003748/r/il/febe6d/4441477806/il_794xN.4441477806_h0w5.jpg"
      },
      "video_link": "https://v.etsystatic.com/video/upload/ac_none,du_15,q_auto:good/file_audee1.mp4",
      "pricing": {
        "amount": 80.08,
        "original_amount": 114.4,
        "discount_percent": 30,
        "currency": "USD"
      },
      "rating": { "value": 5.0, "review_count": 20700 },
      "badge": "Popular now",
      "shop": {
        "id": "7003748",
        "name": "DIAMONDFORLOVE",
        "link": "https://www.etsy.com/shop/DIAMONDFORLOVE"
      },
      "is_sponsored": true,
      "has_free_shipping": true
    },
    {
      "id": "4306368113",
      "title": "Birth Flower Ring 925 Sterling Silver Mother of Pearl Sakura Rings Adjustable Delicate Personalized Birthstone Gift",
      "link": "https://www.etsy.com/listing/4306368113/birth-flower-ring-925-sterling-silver",
      "image": {
        "link": "https://i.etsystatic.com/14792900/r/il/153030/7389351270/il_255x319.7389351270_gz4k.jpg",
        "large_link": "https://i.etsystatic.com/14792900/r/il/153030/7389351270/il_794xN.7389351270_gz4k.jpg"
      },
      "video_link": null,
      "pricing": {
        "amount": 29.4,
        "original_amount": 42.0,
        "discount_percent": 30,
        "currency": "USD"
      },
      "rating": { "value": 4.7, "review_count": 8900 },
      "badge": "Popular now",
      "shop": {
        "id": "14792900",
        "name": "PBJewelryGift",
        "link": "https://www.etsy.com/shop/PBJewelryGift"
      },
      "is_sponsored": false,
      "has_free_shipping": true
    }
  ]
}
```

</details>

---

### Listing Details

▶ [Try it live in the Playground →](https://www.omkar.cloud/tools/etsy-scraper/playground?utm_source=github&utm_medium=cpc&utm_content=endpoint-details)

```
GET https://etsy-scraper.omkar.cloud/etsy/details?listing_id=https://www.etsy.com/listing/4447282937/gold-body-chain-necklace-adjustable
```

| Parameter | Description |
|-----------|-------------|
| `listing_id` | A numeric Etsy listing id (`4447282937`) or any etsy.com listing URL — tracking parameters are fine, the id is extracted automatically |
| `locale` | Etsy regional site code (default `us`). Sets the result language and the default display currency |
| `currency` | 3-letter display currency prices are converted to — defaults to the locale's home currency |

#### Response

Returns the full listing: title, description, pricing (current + strikethrough original + per-variation min/max range, stock quantity), rating and recent reviews, every image with thumbnail and alt text, variation options, highlights, materials, category breadcrumbs, delivery estimate, bestseller/star-seller badges, return policy, the shop's profile with sales and review counts, and the shop's FAQ section.

<details>
<summary>Sample Response (click to expand)</summary>

```json
{
  "id": "4447282937",
  "title": "Dainty Gold Body Chain, Minimal Waist Chain Necklace, Adjustable Front or Back Body Jewelry",
  "link": "https://www.etsy.com/listing/4447282937/gold-body-chain-necklace-adjustable",
  "description": "Delicate gold body chain with a minimal Y-shaped design. Adjustable and lightweight, it can be worn on the front or back for an elegant, feminine look.\n\nDelicate gold body chain designed to be worn either on the front or...",
  "pricing": {
    "amount": 39.5,
    "original_amount": null,
    "min_amount": null,
    "max_amount": null,
    "currency": "USD",
    "is_in_stock": true,
    "quantity_available": 46
  },
  "rating": { "value": 4.5, "review_count": 4 },
  "is_bestseller": false,
  "is_star_seller": true,
  "accepts_returns": true,
  "estimated_delivery": "Order today to get by Sep 1-24",
  "images": [
    {
      "link": "https://i.etsystatic.com/48159131/r/il/f4bde5/7854608778/il_fullxfull.7854608778_5lyu.jpg",
      "thumbnail": "https://i.etsystatic.com/48159131/r/il/f4bde5/7854608778/il_340x270.7854608778_5lyu.jpg",
      "alt": "Gold body chain necklace worn on front, delicate waist chain jewelry on model"
    },
    {
      "link": "https://i.etsystatic.com/48159131/r/il/0ab1c0/7689392667/il_fullxfull.7689392667_cqbt.jpg",
      "thumbnail": "https://i.etsystatic.com/48159131/r/il/0ab1c0/7689392667/il_340x270.7689392667_cqbt.jpg",
      "alt": "Minimal gold body chain jewelry styled on model, elegant body necklace"
    }
  ],
  "variations": [
    {
      "name": "Primary color",
      "options": ["Silver", "Gold"]
    }
  ],
  "highlights": [
    "Made by UtopiaJewelleryStore",
    "Materials: Stainless steel",
    "Closure: Lobster claw",
    "Jewelry style: Minimalist",
    "Length: 25 Inches"
  ],
  "materials": ["Stainless Steel", "Gold Plated", "18k"],
  "categories": [
    { "name": "Jewelry", "link": "https://www.etsy.com/c/jewelry?explicit=1&ref=breadcrumb_listing" },
    { "name": "Body Jewelry", "link": "https://www.etsy.com/c/jewelry/body-jewelry?explicit=1&ref=breadcrumb_listing" },
    { "name": "Belly Chains", "link": "https://www.etsy.com/c/jewelry/body-jewelry/belly-chains?explicit=1&ref=breadcrumb_listing" }
  ],
  "shop": {
    "id": "48159131",
    "name": "UtopiaJewelleryStore",
    "link": "https://www.etsy.com/shop/UtopiaJewelleryStore",
    "logo": "https://i.etsystatic.com/48159131/r/isla/eb0caa/83163610/isla_500x500.83163610_rrt4xj4x.jpg",
    "sales_count": 534,
    "review_count": 81
  },
  "reviews": [
    {
      "author": "Shabana",
      "rating": 5.0,
      "date": "2026-04-30",
      "text": "Absolutely worth every penny! Love this soo much! Quality is great."
    },
    {
      "author": "Alyssa Tucker",
      "rating": 5.0,
      "date": "2026-04-15",
      "text": "⭐ ⭐ ⭐ ⭐ ⭐ I ordered the gold by accident (which was still gorgeous!) and the seller was very responsive and sent me the silver one once I sent the other one back. I put it on right away and I love it! Extremely friendly customer service and just an overall lovely experience. Definitely recommend!"
    }
  ],
  "faqs": [
    {
      "question": "Custom and personalized orders",
      "answer": "At Utopia Jewellery, we're delighted to offer customization options to ensure your jewelry is as unique as you are. If you're looking to adjust the size, colors, remove or add an element, just reach out to us. We'll be more than happy to collaborate with you and make your vision a reality. Feel free to send us a message, and together we'll create a piece that reflects your personal style"
    }
  ],
  "locale": "us"
}
```

</details>

## Pricing

| Plan | Price | Requests/Month |
|------|-------|----------------|
| Free | $0 | 100 |
| Starter | $16 | 3,000 |
| Grow | $48 | 15,000 |
| Scale | $148 | 75,000 |

1 API call = 1 request. One search page — 48 listings — is a single request.

Free Plan Available — [create your API key →](https://www.omkar.cloud/auth/sign-up?redirect=/api-key&utm_source=github&utm_medium=cpc&utm_content=pricing-signup). No credit card for the free tier.

## FAQs

### Can I try the API before signing up?

Yes. The playground runs live requests in your browser — free, no account, no API key. [Try it in the Playground →](https://www.omkar.cloud/tools/etsy-scraper/playground?utm_source=github&utm_medium=cpc&utm_content=faq)

### How do I scrape Etsy search results?

Call the search endpoint with a keyword:

```
GET https://etsy-scraper.omkar.cloud/etsy/search?query=jewelry&page=1
```

It returns 48 listings per page — price with sale discounts, rating with review count, images, video, shop, and sponsored/free-shipping flags — with `next`/`previous` links for pagination, up to 250 pages per query.

### How many listings can I get per search?

48 per page, up to 250 pages — up to 12,000 listings per query. To go deeper on a niche, split it into more specific keywords (use the Autocomplete endpoint to expand a seed term into what Etsy shoppers actually type) and paginate each.

### What data does the API return?

**Search Listings** returns 48 listings per page, each with:
- Listing id, title, and canonical URL
- Image (standard + large) and video link
- Pricing — current amount, strikethrough original, and discount percent when on sale
- Rating with review count
- Badge (like "Popular now"), sponsored and free-shipping flags
- The shop — id, name, and URL

**Listing Details** returns the full listing: description, pricing with stock quantity and per-variation price range, rating and recent reviews with dates, every image with alt text, variation options, highlights, materials, category breadcrumbs, delivery estimate, bestseller/star-seller badges, return policy, shop profile with sales and review counts, and the shop's FAQs.

**Autocomplete** returns Etsy's own search suggestions for a partial phrase, in the locale's language.

### Can I get prices in my currency?

Yes. Pass `currency=EUR` (or any of Etsy's display currencies) and every price in the response is converted. Without it, prices come in the locale's home currency — USD for `us`, EUR for `de`, INR for `in`, and so on.

### Which Etsy regional sites are supported?

All 26 locales: `us`, `uk`, `ca`, `ca-fr`, `au`, `nz`, `ie`, `de`, `at`, `fr`, `be-fr`, `es`, `mx`, `it`, `nl`, `pl`, `pt`, `jp`, `se`, `ru`, `in`, `in-en`, `sg`, `sg-en`, `hk`, `hk-en`. The locale sets the result language and the default currency — `locale=de` returns German titles and EUR prices.

### Can I pass a listing URL instead of an id?

Yes. Listing Details accepts a numeric id (`4447282937`) or any etsy.com listing URL — even one full of tracking parameters copied straight from your browser. The id is extracted automatically.

### How fresh is the data?

Live. Every request is scraped from Etsy on demand, so prices, discounts, stock, ratings, and reviews reflect the listing as it looks right now.

### Will I get blocked or need proxies?

No. We handle the scraping infrastructure — you call a normal REST API and never touch Etsy directly, so there are no proxies, headless browsers, or CAPTCHAs on your side.

## More E-commerce & Data Scrapers: Amazon & Google Maps

- **[Amazon Scraper API](https://github.com/omkarcloud/amazon-scraper)** — the same clean JSON for Amazon: product search, full product details, category browsing, and top reviews across 24 marketplaces. Compare a handmade product's Etsy price against its mass-market Amazon equivalent.

- **[Google Maps Scraper (3,100+ GitHub Stars)](https://github.com/omkarcloud/google-maps-scraper)** — need tens of thousands of leads? Type a niche and a city ("dentists in New York") and get every matching business as a ready-to-call lead list — name, address, phone, website, emails, rating, and reviews. The free tier alone pulls up to 100K leads a month, enough to run your entire outreach pipeline on $0.

- **[Website Email Contact Scraper](https://github.com/omkarcloud/website-email-contact-scraper)** — **Free and open source.** Point it at any website and get every email, phone number, and social profile on it, each with source pages and an official/unofficial flag.

## Support

Built by developers, for developers — when you reach out, you talk to the engineers who built the API, not a support script. Message us anytime and we'll solve your query within 1 working day.


[![Contact Us on WhatsApp about Etsy Scraper](https://raw.githubusercontent.com/omkarcloud/assets/master/images/whatsapp-us.png)](https://api.whatsapp.com/send?phone=918178804274&text=I%20have%20a%20question%20about%20the%20Etsy%20Scraper%20API.)

Email: [happy.to.help@omkar.cloud](mailto:happy.to.help@omkar.cloud?subject=Etsy%20Scraper%20API%20Question)

[![Email Us about Etsy Scraper](https://raw.githubusercontent.com/omkarcloud/assets/master/images/ask-on-email.png)](mailto:happy.to.help@omkar.cloud?subject=Etsy%20Scraper%20API%20Question)

## Love It? Star It! ⭐

From one developer to another: If the Etsy Scraper API saved you time, please [star the repo](https://github.com/omkarcloud/etsy-scraper).

Here's why it matters: most developers judge a scraper by its stars before trying it. Your star helps the next developer — someone deciding whether the Etsy data here is real and reliable — try it with confidence.

It takes only 1 second, and means the world to me.
