# Japan Trip Itinerary — Interactive HTML Template

A single-file interactive travel itinerary built for a 7-day Japan trip. No frameworks, no build tools, no server required — just one HTML file you open in a browser or host anywhere for free.

**[Live demo →](https://lcfjan.github.io/Tamuska-Japan)**

![HTML](https://img.shields.io/badge/HTML-single%20file-orange) ![No dependencies](https://img.shields.io/badge/dependencies-none-brightgreen) ![Free to host](https://img.shields.io/badge/hosting-free-blue)

---

## What it looks like

A mobile-friendly page with collapsible day cards, live widgets, and reference sections — everything you need for a trip in one place, accessible offline for the static content.

---

## Features

### Itinerary
- Collapsible day cards — one per day, tap to expand
- Each activity has a time, title, description, venue link, and transport/cost tags
- Auto-opens the card matching today's date when you load the page

### Live widgets (no API key required)
- **Weather** — 7-day forecast pulled from [Open-Meteo](https://open-meteo.com/) on page load
- **World clock** — shows current time in multiple cities simultaneously, rendered on a canvas arc
- **Exchange rate** — live USD → JPY rate from [Frankfurter](https://www.frankfurter.app/), updates every load
- **Quick rate strip** — always-visible one-liner showing ¥1,000 / ¥3,000 / ¥10,000 / ¥20,000 in dollars
- **Coin guide** — all 6 Japanese coin denominations with photos and live USD values

### Reference cards (collapsible)
- **Apartment access** — address, step-by-step entry instructions, building photos
- **Budget guide** — daily spend estimates per person for Tokyo days, Kyoto day trip, Nikko day trip, ATM tips
- **Local rules** — tipping etiquette, transit manners, cash customs, dining habits
- **Getting around** — metro, JR, IC cards, airport trains, taxi
- **Connectivity** — eSIM, pocket Wi-Fi, free hotspot options
- **Essential apps** — Google Maps, Google Translate, Hyperdia, Suica, currency

---

## How to adapt it for your own trip

### 1. Download
Click the green **Code** button on this page → **Download ZIP**, unzip it, and open `index.html` in a text editor (VS Code, Notepad++, TextEdit on Mac).

### 2. Set your trip dates
Search for `day-arrival` and update the header date. Each day card has a date in the `.day-date` element — update these to match your actual travel dates. The auto-open logic reads these to open today's card automatically.

### 3. Update the weather location
Search for `latitude` and `longitude` in the file. Change the values to your destination city's coordinates. You can find coordinates for any city on [Google Maps](https://maps.google.com) by right-clicking the location.

### 4. Update the exchange rate currency
Search for `frankfurter.app` — change `from=USD&to=JPY` to your own currency pair, e.g. `from=EUR&to=JPY`.

### 5. Update the world clock cities
Search for `wcActive` near the bottom of the file. It looks like this:
```js
wcActive = ['tokyo', 'prague', 'la'];
```
Change the city IDs to match your home city and destination. Available cities are listed just above in the `WC_ALL` array.

### 6. Edit the day cards
Each day is a `<div class="day-card day-N">` block. Inside each one, activities follow this pattern:
```html
<div class="activity">
  <div class="activity-time">9:00 AM</div>
  <div class="activity-content">
    <div class="activity-title">Your activity name</div>
    <div class="activity-desc">Description goes here.</div>
    <div class="tags">
      <span class="tag tag-walk">10 min walk</span>
      <span class="tag tag-cost">¥1,200</span>
    </div>
    <a class="venue-link" href="https://..." target="_blank">Venue website</a>
  </div>
</div>
```
Available tag styles: `tag-walk`, `tag-train`, `tag-cost`, `tag-food`, `tag-tip`

### 7. Update apartment/accommodation details
Search for `apt-address` to find the accommodation section. Replace the placeholder address, room number, floor, and access codes with your own.

### 8. Open in a browser
No server needed. Just double-click `index.html` — it opens in your browser and all the live widgets load automatically.

---

## Hosting for free

| Option | How |
|---|---|
| **GitHub Pages** | Push to a repo → Settings → Pages → select main branch → Save. Live in ~60 seconds at `yourusername.github.io/repo-name` |
| **Vercel** | Go to [vercel.com](https://vercel.com), sign up free, drag and drop your folder |
| **Cloudflare Pages** | Connect your GitHub repo at [pages.cloudflare.com](https://pages.cloudflare.com) |
| **Your own domain** | Point your domain's DNS to any of the above — all support custom domains for free |

---

## External services used

All calls are made from the browser. No backend, no server, no API keys needed.

| Service | What it does | Cost |
|---|---|---|
| [Open-Meteo](https://open-meteo.com/) | Weather forecast | Free, no key |
| [Frankfurter](https://www.frankfurter.app/) | Exchange rates | Free, no key |
| [Wikimedia Commons](https://commons.wikimedia.org/) | Coin images | Free |

---

## License

MIT — use it, change it, share it. No credit required.
