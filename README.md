# TIGON Golf Carts — Dealer Locator

A mobile-first, PWA-ready dealership finder for TIGON Golf Carts.  
Live at: **https://locator.tigongolfcarts.com**

---

## Features

- 📍 **GPS-powered** — uses native browser geolocation (no API key needed)
- 📏 **Haversine distance** — calculates real distance to every dealer, sorts by closest
- 🗺️ **Google Maps CID links** — every "Get Directions" tap registers as a Google Business interaction, boosting local SEO
- 📱 **Mobile-first** — designed for 95% mobile use, 44px tap targets, PWA-installable
- ⚡ **Zero backend** — pure HTML/CSS/JS + a JSON file. No server, no database
- 🔄 **Easy updates** — add/edit dealers by editing `dealers.json` only

---

## File Structure

```
TIGON-Dealership-Locator/
├── index.html        ← Full app (HTML + CSS + JS in one file)
├── dealers.json      ← ALL dealer data — edit this to add/update dealers
├── manifest.json     ← PWA manifest (enables "Add to Home Screen")
├── CNAME             ← GitHub Pages custom domain config
├── assets/
│   ├── icon-192.png  ← PWA icon (add a 192×192 TIGON icon here)
│   └── icon-512.png  ← PWA icon (add a 512×512 TIGON icon here)
└── README.md
```

---

## Setup: GitHub Pages + Custom Subdomain

### Step 1 — Enable GitHub Pages
1. Go to your repo: https://github.com/Tigon-Golf-Carts-LLC/TIGON-Dealership-Locator
2. Click **Settings** → **Pages**
3. Under "Source" select **Deploy from a branch**
4. Choose **main** branch, **/ (root)** folder
5. Click **Save**

GitHub will provide a URL like `https://tigon-golf-carts-llc.github.io/TIGON-Dealership-Locator`

### Step 2 — Point Your Subdomain
At your domain registrar (GoDaddy, Namecheap, Cloudflare, etc.):

Add a **CNAME DNS record**:
| Type  | Name    | Value                              |
|-------|---------|------------------------------------|
| CNAME | locator | tigon-golf-carts-llc.github.io     |

> ⚠️ DNS changes can take 5–60 minutes to propagate.

### Step 3 — Verify Custom Domain in GitHub
1. Go back to **Settings → Pages**
2. Under "Custom domain" enter: `locator.tigongolfcarts.com`
3. Check **Enforce HTTPS** once it becomes available

---

## Adding or Updating a Dealer

Open `dealers.json` and add a new entry:

```json
{
  "id": "T18",
  "name": "TIGON Golf Carts — City, State",
  "shortName": "City, STATE",
  "address": "123 Main St, City, STATE 12345",
  "phone": "555-000-0000",
  "lat": 00.000000,
  "lng": -00.000000,
  "cid": "000000000000000000",
  "website": "https://tigongolfcarts.com/city/",
  "facebook": "https://www.facebook.com/TigonGolfCartsCity/",
  "youtube": "",
  "pinterest": "",
  "review": "https://g.page/r/XXXXXXXXXXXXX/review"
}
```

### How to find the CID
1. Go to the dealer's **Google Business Profile**
2. Click "Share" → "Copy link"  
3. The URL will look like: `https://www.google.com/maps?cid=12345678901234567`
4. The number after `cid=` is the CID

### How to find lat/lng
1. Go to Google Maps
2. Right-click the exact location → the coordinates appear at the top of the context menu
3. Format: `latitude, longitude` (e.g. `40.2983, -75.2830`)

---

## Embed on Your Main Website

### Option A — Full-page link (recommended for mobile)
```html
<a href="https://locator.tigongolfcarts.com" target="_blank">
  <img src="find-dealer-button.png" alt="Find a TIGON Dealer Near You" />
</a>
```

### Option B — Iframe embed
```html
<iframe
  src="https://locator.tigongolfcarts.com"
  width="100%"
  height="700"
  style="border: none; border-radius: 16px;">
</iframe>
```

> **Note:** Geolocation inside iframes requires the `allow="geolocation"` attribute:
```html
<iframe src="https://locator.tigongolfcarts.com" allow="geolocation" ...>
```

---

## Google Business CID — How It Helps SEO

Every time a user taps **"Get Directions"**, the link goes to:
```
https://www.google.com/maps/dir/?api=1&destination=...&destination_place_id=CID
```

This counts as a **Maps interaction tied to the Google Business listing** — Google treats this as a local relevance signal, which contributes to that location's local search ranking.

Make sure every dealer has their **CID** in `dealers.json`.

---

## PWA Icons

Add TIGON-branded icons to the `/assets/` folder:
- `icon-192.png` — 192×192 pixels, green background, TIGON logo
- `icon-512.png` — 512×512 pixels, same design

These appear when users tap "Add to Home Screen" on iOS/Android.

---

## Current Dealers (18 Locations)

| ID    | Location                    | Phone          |
|-------|-----------------------------|----------------|
| T1    | Hatfield, PA                | 215-595-8736   |
| T2    | Ocean View, NJ              | 609-840-0404   |
| T3    | Long Pond, PA               | 570-580-0567   |
| T3.5  | Pocono Pines, PA            | 570-643-0152   |
| T4    | Dover, DE                   | 302-546-0010   |
| T5    | Scranton / Wilkes-Barre, PA | 570-344-4443   |
| T6    | Raleigh, NC                 | 984-489-0296   |
| T7    | South Bend, IN              | 574-703-0456   |
| T8    | Gloucester Point, VA        | 804-792-0234   |
| T9    | Bayville, NJ                | 732-908-7166   |
| T10   | Waretown, NJ                | 732-998-8146   |
| T11   | Orangeburg, SC              | 803-596-0246   |
| T12   | Swanton, OH                 | 419-402-8400   |
| T13   | Lecanto, FL                 | 352-453-0345   |
| T14   | Rio Grande, NJ              | 609-551-0234   |
| T15   | Pleasantville, NJ           | 640-444-3094   |
| T16   | Portsmouth, VA              | 757-977-0146   |
| T17   | Virginia Beach, VA          | 1-844-844-6638 |

---

## Questions / Support
- Website: https://tigongolfcarts.com
- Phone: 1-844-844-6638
- Repo: https://github.com/Tigon-Golf-Carts-LLC/TIGON-Dealership-Locator
