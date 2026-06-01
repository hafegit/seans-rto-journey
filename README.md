# Sean's RTO Journey 🏃‍♂️

An interactive map tracking my progress through all 36 legs of the [Reno-Tahoe Odyssey](https://renotahoeodyssey.com/) relay race.

**🌐 Live site:** [https://hafegit.github.io/seans-rto-journey/](https://hafegit.github.io/seans-rto-journey/)

---

## How to Update After a Race

**The only file you need to edit is `index.html`.** No build tools, no terminal commands needed — just edit the file on GitHub.com and save.

### Step-by-step:

1. Go to [index.html on GitHub](https://github.com/hafegit/seans-rto-journey/blob/main/index.html)
2. Click the **pencil icon** (✏️) to edit
3. Find the `completedLegs` array (near the top of the `<script>` section, around line 340 — it's clearly marked with a big comment block)
4. Add your new leg(s) to the array:

```javascript
const completedLegs = [
    // ... existing entries ...
    { leg: 7,  year: 2022, pace: "7:58/mi" },
    { leg: 19, year: 2022, pace: "9:43/mi" },
    // ↓ ADD NEW ONES HERE ↓
    { leg: 5,  year: 2027, pace: "7:15/mi" },
    { leg: 17, year: 2027, pace: "8:02/mi" },
    { leg: 29, year: 2027, pace: "7:45/mi" }
];
```

5. Click **"Commit changes"**
6. Wait ~1 minute for GitHub Pages to rebuild
7. Refresh the live site — done! ✅

### Format for each entry:

```javascript
{ leg: LEG_NUMBER, year: YEAR, pace: "M:SS/mi" }
```

- `leg` — The leg number (1–36)
- `year` — The year you ran it (e.g., `2027`)
- `pace` — Your average pace as `"M:SS/mi"` (e.g., `"7:08/mi"`)

That's it. The progress bar, map highlighting, and info panels all update automatically.

---

## Current Progress

| Year | Legs Run | Paces |
|------|----------|-------|
| 2022 | 7, 19, 31 | 7:58/mi, 9:43/mi, 9:59/mi |
| 2023 | 4, 16, 28 | 9:14/mi, 6:48/mi, 7:32/mi |
| 2024 | 2, 14, 26 | 6:58/mi, 7:31/mi, 7:07/mi |
| 2026 | 10, 22, 34 | 7:08/mi, 7:00/mi, 6:55/mi |

**12 of 36 legs completed** (33%)

---

## Leg Reference

| Leg | Miles | Rating | Description |
|-----|-------|--------|-------------|
| 1 | 4.9 | E | Reno to Verdi |
| 2 | 4.4 | M | Verdi to Boomtown |
| 3 | 5.5 | M | Boomtown to Dog Valley Rd |
| 4 | 8.0 | MD | Dog Valley Rd to Truckee (Donner's Downfall) |
| 5 | 5.6 | M | Truckee to Donner Lake |
| 6 | 5.4 | E | Donner Lake to Truckee River |
| 7 | 7.4 | MC | Truckee to Squaw Valley Rd |
| 8 | 4.0 | M | Squaw Valley Rd to Tahoe City |
| 9 | 5.3 | M | Tahoe City to Homewood |
| 10 | 4.8 | M | Homewood to Tahoma |
| 11 | 5.2 | M | Tahoma to Emerald Bay |
| 12 | 6.2 | M | Emerald Bay to Camp Richardson |
| 13 | 6.2 | M | Camp Richardson to South Lake Tahoe |
| 14 | 6.2 | MD | South Lake Tahoe to Stateline |
| 15 | 5.5 | MC | Stateline to Round Hill |
| 16 | 3.4 | E | Round Hill to Zephyr Cove |
| 17 | 3.3 | E | Zephyr Cove to Cave Rock |
| 18 | 4.6 | E | Cave Rock to Glenbrook |
| 19 | 3.8 | MD | Glenbrook to Spooner Summit |
| 20 | 3.7 | M | Spooner Summit to Carson City |
| 21 | 3.7 | M | Carson City (Hwy 50) |
| 22 | 5.7 | M | Carson City to Genoa |
| 23 | 6.1 | M | Genoa to Jacks Valley |
| 24 | 3.2 | E | Jacks Valley to Carson City |
| 25 | 3.4 | E | Carson City (Capital Odyssey Start) |
| 26 | 5.5 | M | Carson City to Silver City |
| 27 | 3.9 | M | Silver City to Gold Hill |
| 28 | 4.8 | M | Gold Hill to Virginia City |
| 29 | 3.4 | MC | Virginia City to Geiger Grade |
| 30 | 3.4 | MD | Geiger Grade descent |
| 31 | 2.6 | MD | Geiger Grade to Steamboat |
| 32 | 3.3 | MD | Steamboat to Pleasant Valley |
| 33 | 6.6 | MC | Pleasant Valley to South Reno |
| 34 | 5.1 | M | South Reno to Moana Lane |
| 35 | 6.9 | MC | Moana Lane to Midtown Reno |
| 36 | 4.2 | M | Midtown Reno to Finish (J Resort) |

### Difficulty Ratings
- **E** — Easy (relatively flat)
- **M** — Moderate
- **MC** — More Challenging
- **MD** — Most Difficult (steepest climbs)

---

## Project Structure

```
seans-rto-journey/
├── index.html          ← THE ONLY FILE YOU NEED TO EDIT
├── data/
│   ├── routes.js       ← GPS coordinates for all 36 legs (auto-generated from GPX)
│   ├── elevations.js   ← Elevation data for profile charts (auto-generated from GPX)
│   ├── legs.json       ← Leg metadata reference file
│   └── gpx/            ← Raw GPX files from Garmin Connect (source of truth)
└── README.md           ← This file
```

## Tech Stack

- Pure HTML/CSS/JavaScript — no build step, no dependencies to install
- [Leaflet.js](https://leafletjs.com/) for interactive mapping (loaded from CDN)
- Esri satellite imagery tiles
- Canvas-drawn elevation profile charts
- Hosted on GitHub Pages (auto-deploys on push)

## Local Development

Just open `index.html` in a browser, or:

```bash
cd seans-rto-journey
python3 -m http.server 8000
# Visit http://localhost:8000
```
