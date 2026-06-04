# 🏔️ UCI Downhill World Cup 2026 — Fan Hub

A single-page web application for fans of the **WHOOP UCI Mountain Bike World Series — Downhill**, covering the full 2026 season across 9 rounds, 7 countries and 3 continents.

Built as a lightweight, self-contained HTML file with no dependencies or build steps required.

---

## Features

### 📊 Standings & Results
- Live overall standings for Men Elite and Women Elite after each completed round
- Round-by-round results with expandable cards showing top 5 finishers and times
- Status badges for each round: **Complete** or **Upcoming**
- "Next up" badge showing the upcoming round, location and date
- Easy to update after each race weekend — just edit one data block and push to GitHub (see instructions below)

### 📅 Race Schedule
- All 9 DH World Cup rounds with local and UK (BST) race times
- Race location, country, track name and event formats (DH, XCO, XCC, EDR)
- Expandable detail cards with broadcast information
- Filter by team or search by individual rider name
- Download individual round or full season `.ics` calendar files for import into Apple Calendar, Google Calendar, Outlook etc.

### 👥 Teams & Riders
- All 20 gravity teams grouped by licence type (2-Year, 1-Year, Wildcard)
- Expandable team cards with full rider rosters
- Search/filter by team name or rider name
- **Clickable rider profiles** opening a detailed modal with:
  - SVG avatar with country flag colours and initials
  - Age, sex, nationality, hometown
  - **Career Statistics** — UCI World Ranking, Total Points, World Championships, World Cup Wins, World Cup Podiums and Overall Titles (all-time career totals, end of 2025)
  - Written biography covering career history and notable achievements
  - Career highlights timeline
  - Direct link to the rider's official UCI MTB World Series profile page

### 📺 How to Watch
- UK broadcast details: TNT Sports, HBO Max, discovery+, Eurosport
- UK pricing and subscription information
- Free alternatives: UCI MTB World Series YouTube channel and Red Bull TV highlights
- Worldwide broadcaster guide covering USA, Canada, Australia, Europe and rest of world

### 🧠 DH Knowledge Quiz
- 20-question bank (10 served randomly per attempt) covering:
  - 2026 season specifics
  - Historic UCI DH World Cup moments
  - Legendary riders and career records
  - Tracks, venues and broadcasting history
- Instant feedback with correct/wrong indicators
- Progress bar and final score with verdict

### 🌙 Light / Dark Mode
- Toggle between light and dark themes via the floating button
- Preference saved to localStorage and persisted between visits

---

## Tech Stack

- **Pure HTML, CSS & JavaScript** — single file, no frameworks, no build tools
- **Google Fonts** — Oswald (headings) + Source Sans 3 (body)
- **Zero dependencies** — works fully offline, no API keys or backend needed

---

## Getting Started

### Quick Start

1. Download `uci-dh-worldcup-2026.html`
2. Open it in any modern browser
3. That's it — everything works out of the box

### Deploy to GitHub Pages

1. Fork or clone this repository
2. Rename the file to `index.html` (or it may already be named this)
3. Go to **Settings → Pages**
4. Set source to **Deploy from a branch**, select `main`, click **Save**
5. Your site will be live at `https://yourusername.github.io/your-repo-name/`

### Deploy to Netlify

1. Log into [app.netlify.com](https://app.netlify.com) and click **Add new site → Import an existing project**
2. Connect your GitHub repo
3. Netlify auto-deploys and your site is live
4. Every `git push` triggers an automatic redeploy

### Add to iPhone Home Screen

1. Open the deployed URL in Safari
2. Tap the **Share** button (square with arrow)
3. Tap **Add to Home Screen**
4. The app will appear as an icon on your home screen

---

## Updating Standings After Each Round

The standings data lives inside `index.html` in a clearly commented JavaScript block near the top of the `<script>` section. After each race weekend, you update three things and push to GitHub. Netlify (or GitHub Pages) redeploys automatically.

### Step-by-step

1. **Open `index.html`** in any text editor and find the `standingsData` block (search for `STANDINGS DATA`)

2. **Update the header:**
   ```js
   lastUpdated: "31 May 2026",   // ← today's date
   roundsCompleted: 2,            // ← increment this
   ```

3. **Update the overall standings** — replace `menOverall` and `womenOverall` arrays with the new cumulative points table. The format for each row is:
   ```js
   { pos: 1, rider: "Name", country: "🇫🇷", team: "Team Name", points: 450 },
   ```

4. **Add the round results** — uncomment the next round template in `roundResults` and fill in the top 5 times:
   ```js
   {
     round: 2,
     location: "Loudenvielle-Peyragudes, France",
     date: "31 May 2026",
     status: "complete",
     menTop5: [
       { pos: 1, rider: "Name", country: "🇫🇷", time: "0:00.000" },
       // ... top 5
     ],
     womenTop5: [
       { pos: 1, rider: "Name", country: "🇦🇹", time: "0:00.000" },
       // ... top 5
     ]
   }
   ```

5. **Save, commit and push:**
   ```bash
   git add index.html
   git commit -m "Add Round 2 results - Loudenvielle"
   git push
   ```

That's it. Netlify or GitHub Pages redeploys within a minute and the site is live with fresh data. No API keys, no server costs, no infrastructure.

### Where to find the results

After each race, results are typically posted within an hour on:
- [Pinkbike](https://www.pinkbike.com/) — detailed results and live updates
- [Vital MTB](https://www.vitalmtb.com/) — full results and race reports
- [UCI MTB World Series](https://www.ucimtbworldseries.com/) — official results

---

## Data Sources

- **Race schedule** — [UCI MTB World Series](https://www.ucimtbworldseries.com/) official calendar
- **Teams & riders** — UCI MTB World Series team announcements and Pinkbike season previews
- **Rider biographies** — Compiled from MTBData.com, Pinkbike, Vital MTB and official team sources
- **Career statistics** — Cross-referenced against [MTBData.com](https://www.mtbdata.com) and [UCI MTB World Series athlete profiles](https://www.ucimtbworldseries.com/athletes)
- **Race results** — Pinkbike, Vital MTB and UCI official results
- **Broadcast information** — Warner Bros. Discovery / TNT Sports

---

## 2026 DH World Cup Calendar

| Round | Venue | Country | Dates |
|-------|-------|---------|-------|
| R1 | MONA YongPyong | 🇰🇷 South Korea | 1–3 May |
| R2 | Loudenvielle-Peyragudes | 🇫🇷 France | 28–31 May |
| R3 | Saalfelden-Leogang | 🇦🇹 Austria | 11–14 Jun |
| R4 | Lenzerheide | 🇨🇭 Switzerland | 19–21 Jun |
| R5 | La Thuile | 🇮🇹 Italy | 3–5 Jul |
| R6 | Pal Arinsal | 🇦🇩 Andorra | 9–12 Jul |
| R7 | Les Gets | 🇫🇷 France | 14–16 Aug |
| R8 | Whistler | 🇨🇦 Canada | 25–27 Sep |
| R9 | Lake Placid | 🇺🇸 USA | 2–4 Oct |

---

## Screenshots

> Add screenshots of the app in light and dark mode here after deploying.

---

## Contributing

This is a personal fan project. If you spot incorrect rider stats, missing results or have feature suggestions, feel free to open an issue or submit a pull request.

---

## Disclaimer

This is an unofficial fan-made application and is not affiliated with, endorsed by or connected to the UCI, Warner Bros. Discovery, or any of the teams or riders featured. All race data, rider information and broadcast details are sourced from publicly available information. Rider profile photos are not included — the app links to official UCI athlete pages instead.

---

## Licence

MIT — free to use, modify and distribute.
