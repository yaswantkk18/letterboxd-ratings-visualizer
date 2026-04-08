# 🎬 Letterboxd Ratings Visualizer

A visual tool to help you **see your movie ratings at a glance** — making it easier to compare and rate new movies on Letterboxd.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![TMDB](https://img.shields.io/badge/TMDB-01B4E4?style=flat&logo=themoviedatabase&logoColor=white)

<!-- Add a screenshot of your app here -->
<!-- ![Screenshot](screenshot.png) -->

## The Problem

If you've rated 100+ movies on Letterboxd and watch a new one, figuring out the right rating becomes a pain. You end up scrolling through your ratings, applying filters, and mentally comparing — it's messy.

## The Solution

This tool visualizes all your Letterboxd ratings in a poster grid, grouped by rating (5 → 0.5). Just glance at the posters to see where a new movie fits. Hover over any poster to see the title and year.

## Features

- 📁 **Drag & drop** your Letterboxd `ratings.csv` export
- 🖼️ **Auto-fetches movie posters** via the TMDB API
- ⭐ **Groups movies by rating** from highest to lowest
- 💾 **Caches posters** in localStorage for faster reloads
- 📱 **Responsive grid** layout that works on any screen size
- 🎨 **Clean UI** with hover effects and loading animations

## How to Use

### 1. Export your Letterboxd ratings

Go to [Letterboxd Settings → Import & Export](https://letterboxd.com/settings/data/) and click **Export Your Data**. You'll get a ZIP file — extract it and grab the `ratings.csv` file.

### 2. Get a free TMDB API key

Sign up at [themoviedb.org](https://www.themoviedb.org/signup) and request an API key (it's free). Then open `letterboxd_ratings.html` and replace:

```js
const TMDB_API_KEY = 'YOUR_TMDB_API_KEY_HERE';
```

with your key.

### 3. Open and upload

Open `letterboxd_ratings.html` in your browser, drag & drop your `ratings.csv`, and see your ratings visualized!

## Tech Stack

- **Vanilla HTML/CSS/JS** — no frameworks, no build tools, just one file
- **TMDB API** — for fetching movie poster images
- **AllOrigins** — CORS proxy for scraping Letterboxd pages to get TMDB IDs

## How It Works

1. Parses the Letterboxd CSV export to extract movie names, years, ratings, and Letterboxd URIs
2. Groups movies by their rating value
3. For each movie, scrapes the Letterboxd page to find the TMDB ID, then fetches the poster from TMDB
4. Renders everything in a responsive grid, sorted from highest to lowest rating
5. Caches poster URLs in `localStorage` so subsequent loads are instant

## Project Structure

```
├── letterboxd_ratings.html   # The entire app (single file)
├── ratings.csv               # Sample ratings export (optional)
└── README.md
```

## License

MIT

---

*Built to scratch my own itch — if you're a Letterboxd user who rates a lot of movies, give it a try!*
