# Sean's RTO Journey 🏃‍♂️

An interactive map tracking my progress through all 36 legs of the [Reno-Tahoe Odyssey](https://renotahoeodyssey.com/) relay race.

**Live site:** [https://hafegit.github.io/seans-rto-journey/](https://hafegit.github.io/seans-rto-journey/)

## Progress

| Year | Legs Run | Paces |
|------|----------|-------|
| 2022 | 7, 19, 31 | 7:58/mi, 9:43/mi, 9:59/mi |
| 2023 | 4, 16, 28 | 9:14/mi, 6:48/mi, 7:32/mi |
| 2024 | 2, 14, 26 | 6:58/mi, 7:31/mi, 7:07/mi |
| 2026 | 10, 22, 34 | 7:08/mi, 7:00/mi, 6:55/mi |

**12 of 36 legs completed** (33%)

## How to Update After Future Races

### Adding a new completed leg

1. Open `index.html`
2. Find the `completedLegs` array (around line 220, clearly marked with a comment)
3. Add a new entry:

```javascript
const completedLegs = [
    // ... existing entries ...
    { leg: 5,  year: 2027, pace: "7:15/mi" },  // ← add new ones here
];
```

4. Commit and push — GitHub Pages will update automatically.

### Data format

Each completed leg entry has three fields:
- `leg` — The leg number (1–36)
- `year` — The year you ran it
- `pace` — Your average pace in `"M:SS/mi"` format

### Leg reference

The full course data is also stored in `data/legs.json` for reference. The website itself uses the inline data in `index.html` for simplicity (no build step needed).

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

## Tech Stack

- Pure HTML/CSS/JavaScript (no build step)
- [Leaflet.js](https://leafletjs.com/) for interactive mapping
- Esri satellite imagery tiles
- Hosted on GitHub Pages

## Local Development

Just open `index.html` in a browser, or serve it locally:

```bash
python3 -m http.server 8000
# Then visit http://localhost:8000
```
