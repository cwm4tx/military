# MilNav — Military Map Reading & Navigation

Interactive training tool for military map reading, protractor plotting, and resection. Built as a Progressive Web App (PWA) that works offline on iPhone.

## What's Inside

- **Lesson 1: Protractor Plotting** — Plot grid references, measure bearings with a virtual mil protractor, calculate distance, convert grid to magnetic
- **Lesson 2: Resection (3-Point Fix)** — Determine your position using compass bearings to three known landmarks
- **Reference Manual** — Complete 8-section map reading reference (terrain features, grid systems, range estimation, military sketches, exercises)
- **Abu Dhabi G-M angle** preconfigured (~39 mils / 2.19° East)
- **NATO 6400-mil system** throughout, degrees as secondary

## Deploy to GitHub Pages (3 minutes)

### Step 1 — Create the Repository

1. Go to [github.com/new](https://github.com/new)
2. Name it `milnav` (or whatever you prefer)
3. Set it to **Public** (required for free GitHub Pages)
4. **Do NOT** add a README — we already have one
5. Click **Create repository**

### Step 2 — Upload the Files

On the repo page, click **"uploading an existing file"** link and drag in ALL of these files/folders:

```
index.html          ← the main app
manifest.json       ← PWA config
sw.js               ← service worker (offline caching)
icons/              ← folder containing the PNG icons
  icon-180x180.png
  icon-192x192.png
  icon-512x512.png
```

Commit directly to the `main` branch.

### Step 3 — Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages** (left sidebar)
2. Under "Source", select **Deploy from a branch**
3. Branch: **main**, folder: **/ (root)**
4. Click **Save**
5. Wait ~60 seconds

### Step 4 — Get Your URL

Your app is now live at:
```
https://YOUR-USERNAME.github.io/milnav/
```

Send this link to anyone via Signal, WhatsApp, email — they tap it and it just works.

## How Recipients Use It

1. They tap the link you send them
2. The app opens in Safari
3. A green banner at the top prompts them to "Add to Home Screen"
4. If they follow the prompt: the app appears as an icon on their home screen, launches full-screen with no browser bar, and works offline after the first visit
5. If they ignore the prompt: it still works perfectly in Safari

## Updating Content

To update the app after deployment:
1. Edit `index.html` on GitHub (or push changes)
2. If you want the service worker to re-cache, bump the version in `sw.js`:
   ```js
   const CACHE_NAME = 'milnav-v2';  // was v1
   ```
3. GitHub Pages updates automatically within ~60 seconds

## Customisation

- **G-M Angle**: Search for `GM_DEG=2.19` in index.html and change to your location's declination
- **Grid labels**: Search for `E0=` and `N0=` to change the starting easting/northing numbers
- **Landmarks** (resection): Search for the `LM=` array to change landmark names, positions, and grid refs

## Tech Stack

- React 18 via CDN (no build step)
- Babel standalone for in-browser JSX transpilation
- Vanilla CSS (no frameworks)
- Service Worker for offline caching
- Web App Manifest for PWA installation

## Classification

**UNCLASSIFIED — For training use**
