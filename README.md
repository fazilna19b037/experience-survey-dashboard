# 🇦🇪 UAE National Day 2025 — Survey Analytics Dashboard

A fully static, front-end-only analytics dashboard for the UAE National Day 2025 Experience Survey. No backend required — runs entirely in the browser and can be hosted for free on **GitHub Pages**.

---

## 📊 Features

- **150 mock survey responses** generated in JavaScript (realistic weighted distributions)
- **5 KPI cards** — NPS, Star Rating, Satisfaction, Memorability, First-Time %
- **Audience Profile** — respondent type doughnut chart + first-time attendee ring
- **NPS Distribution** — visual bar scale with Detractors / Passives / Promoters
- **Experience Dimensions** — radar chart + progress bars for Impact, Memorability, Satisfaction, Perceived Value
- **Highlights & Improvements** — horizontal bar breakdowns from Q9 & Q10
- **Actionable Insights Panel** — 6 data-driven recommendations
- **Open Feedback Themes** — horizontal bar charts for Q11/Q12 themes
- **Live Filters** — filter all charts instantly by: All / UAE Citizens / Residents / Tourists / Other

---

## 🚀 Deploying to GitHub Pages (Step by Step)

### Step 1 — Create a GitHub account
If you don't have one, sign up at [github.com](https://github.com).

### Step 2 — Create a new repository
1. Click the **+** icon → **New repository**
2. Name it: `uae-survey-dashboard` (or anything you like)
3. Set visibility to **Public**
4. Do NOT initialize with README (you'll upload your own)
5. Click **Create repository**

### Step 3 — Upload your files
**Option A — Using GitHub's web interface (easiest):**
1. On your new empty repo page, click **"uploading an existing file"**
2. Drag and drop `index.html` into the upload area
3. Scroll down, write a commit message like `"Add dashboard"`
4. Click **Commit changes**

**Option B — Using Git (command line):**
```bash
# Clone your new repo
git clone https://github.com/YOUR_USERNAME/uae-survey-dashboard.git
cd uae-survey-dashboard

# Copy index.html into this folder, then:
git add index.html
git commit -m "Add UAE National Day survey dashboard"
git push origin main
```

### Step 4 — Enable GitHub Pages
1. Go to your repo → **Settings** tab
2. Scroll down to **Pages** (left sidebar)
3. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
4. Click **Save**

### Step 5 — Access your live dashboard
After 1–2 minutes, your dashboard will be live at:
```
https://YOUR_USERNAME.github.io/uae-survey-dashboard/
```

GitHub will show you the URL in the Pages settings section.

---

## 📁 File Structure

```
uae-survey-dashboard/
└── index.html          ← Everything is in this single file
```

That's it — the entire dashboard is a single self-contained HTML file. No npm, no build step, no server.

---

## 🔧 Customizing with Real Data

When you have actual survey responses, replace the mock data in `index.html`:

1. Find the `generateResponses()` function (~line 170)
2. Replace it with your real data as a JavaScript array:

```javascript
let ALL_DATA = [
  { type: 'resident', isFirstTime: false, q3: 9, q4: 5, q5: 8.5, q6: 9.0, q7: 8.0, q8: 7.5,
    enjoyed: ['Fireworks display', 'Atmosphere & setting'],
    improve: ['Transport & access'] },
  // ... more responses
];
```

Each response object needs these fields:
| Field | Type | Description |
|-------|------|-------------|
| `type` | `'citizen'` \| `'resident'` \| `'tourist'` \| `'other'` | Q1 answer |
| `isFirstTime` | `boolean` | Q2 answer |
| `q3` | `0–10` | Recommend to friends (NPS) |
| `q4` | `1–5` | Overall star rating |
| `q5` | `1–10` | Impact score |
| `q6` | `1–10` | Memorability score |
| `q7` | `1–10` | Satisfaction score |
| `q8` | `1–10` | Perceived value score |
| `enjoyed` | `string[]` | Q9 selected options |
| `improve` | `string[]` | Q10 selected options |

---

## 🛠 Tech Stack

| Technology | Purpose |
|------------|---------|
| HTML5 / CSS3 | Structure & styling |
| Vanilla JavaScript | Data generation & logic |
| [Chart.js 4.4](https://www.chartjs.org/) | All charts (loaded from CDN) |
| Google Fonts | Syne + DM Sans typography |

No frameworks, no build tools, no dependencies to install.

---

## 📝 Notes

- All 150 mock responses are generated fresh each page load with realistic weighted distributions
- Filters update all charts simultaneously in real time
- The dashboard is fully responsive for mobile and tablet
- Dark theme is hardcoded (matches UAE National Day aesthetic)

---

*Built for UAE National Day 2025 post-event analytics.*
