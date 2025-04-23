# Letterboxd to TMDb Exporter

This repository contains two Python scripts that help you export movie and show data from your [Letterboxd](https://letterboxd.com) account into CSV format, with associated [TMDb](https://www.themoviedb.org/) IDs and types (movie or show). Perfect for syncing your viewing history or watchlist with services like Trakt, Plex, or Jellyfin.

---

## 📄 Scripts Overview

### `exportLetterboxdHistory.py`

This script extracts:

- All watched movies/shows from your Letterboxd account (`/films/`)
- Optionally: your **ratings**
- Optionally: your **watchlist**

#### Output CSVs:
- `watched_movies_tmdb.csv`
- `watchlist_tmdb.csv` (if watchlist scraping is enabled)

Each CSV row has the following structure:

| Letterboxd URL | TMDB ID | Type  | Rating (optional) |
|----------------|---------|-------|--------------------|
| https://...    | 123456  | movie | 7                  |

**Rating** (optional): rounded to the nearest integer on a 10-point Trakt-compatible scale.

---

### `exportLetterboxdList.py`

This script is designed for exporting a **custom Letterboxd list** (e.g. Top 100 Horror Films) into a CSV with TMDb data.

#### Output CSV:
- `list.csv`

Each CSV row has the following structure:

| Letterboxd URL | TMDB ID | Type  |
|----------------|---------|-------|
| https://...    | 123456  | movie |

---

## ⚙️ Requirements

- Python 3.7+
- Internet connection

### Install dependencies (optional but recommended via virtualenv)

```bash
pip install beautifulsoup4 requests

