# Spotify Listening Analysis

A personal data analysis project built with the Spotify API that analyzes my own listening history to uncover patterns in my music taste, listening habits, and how my preferences have shifted over time.

---

## Motivation

Instead of waiting for Spotify Wrapped once a year, I wanted to build my own analysis using real personal data pulled directly from the Spotify API and use it as an opportunity to practice working with APIs, data manipulation, and visualization in Python.

---

## What I Analyzed

### 1. Top Artists & Tracks
Pulled my all-time top 10 most listened to artists and tracks using the Spotify API.

**Top 10 Artists (All Time):**
1. Drake
2. J. Cole
3. Travis Scott
4. Future
5. All Time Low
6. Lil Wayne
7. Kanye West
8. A$AP Rocky
9. Childish Gambino
10. Pierce The Veil

**Top 10 Tracks (All Time):**
1. One Last Breath — Creed
2. Fancy — Drake
3. Time — Hans Zimmer
4. You Were Right — RÜFÜS DU SOL
5. Over My Dead Body — Drake
6. Come Thru — Drake
7. DtMF — Bad Bunny
8. Too Deep for the Intro — J. Cole
9. 9 — Drake
10. U With Me? — Drake

---

### 2. Listening by Hour of Day
Analyzed my last 50 played tracks to find peak listening hours.

| Hour (UTC) | Tracks Played |
|------------|---------------|
| 14:00 | 3 |
| 15:00 | 8 |
| 16:00 | 4 |
| 17:00 | 4 |
| 19:00 | 1 |
| 20:00 | 16 |
| 21:00 | 3 |
| 22:00 | 11 |

> Peak listening at 20:00 UTC (4:00 PM Eastern). Heavy evening listening pattern from 3 PM–10 PM Eastern.

---

### 3. Short Term vs Long Term Taste
Compared my top 20 artists over the last 4 weeks vs all time to identify shifts in my listening habits.

**Consistent Favorites (in both lists):**
All Time Low, Childish Gambino, Drake, Future, J. Cole, Kanye West, Lil Uzi Vert, Lil Wayne, Mac Miller, Pierce The Veil, RÜFÜS DU SOL, Travis Scott

**New Obsessions (last 4 weeks only):**
A Boogie Wit da Hoodie, Bad Bunny, Bas, Frank Ocean, Joey Bada$$, Linkin Park, Paramore, Prospa

**Fallen Off (all time but not recent):**
A$AP Rocky, Fred again.., Green Day, Hans Zimmer, Kendrick Lamar, Neck Deep, Ramin Djawadi, blink-182

---

## Key Findings

- My taste is anchored by hip hop (Drake, J. Cole, Travis Scott) and alternative/pop punk (All Time Low, Pierce The Veil) across both time ranges
- 12 out of 20 all-time artists remain in my recent rotation signaling a strong core of consistent favorites
- Recent listening shows a shift toward classic rock-adjacent acts (Linkin Park, Paramore) and new hip hop discoveries (Frank Ocean, Joey Bada$$)
- Notably fallen off: Kendrick Lamar and A$AP Rocky despite being all-time favorites. Likely reflects mood-based listening rather than a permanent shift
- Peak listening window is 3 PM–10 PM Eastern, heavily concentrated around 8 PM

---

## Tech Stack

- Python
- [Spotipy](https://spotipy.readthedocs.io/) — Python wrapper for the Spotify Web API
- Pandas — data aggregation
- Matplotlib — visualization
- python-dotenv — secure credential management
- Jupyter Notebook

---

## Setup

1. Clone the repo
2. Install dependencies:
```bash
pip install spotipy pandas matplotlib python-dotenv jupyter
```
3. Create a `.env` file in the root directory:
```
SPOTIPY_CLIENT_ID=your_client_id
SPOTIPY_CLIENT_SECRET=your_client_secret
SPOTIPY_REDIRECT_URI=http://127.0.0.1:8888/callback
```
4. Create a Spotify Developer app at https://developer.spotify.com/dashboard and add yourself as a user
5. Run the notebook:
```bash
jupyter notebook
```

> Note: Spotify's audio features endpoint (`/audio-features`) is restricted in development mode apps as of 2024 and requires extended access approval. This project pivots to artist comparison analysis as an alternative.

---

## Project Structure

```
spotify-analysis/
├── spotify_analysis.ipynb   # Main analysis notebook
├── .env                     # API credentials (not uploaded to GitHub)
├── .gitignore               # Excludes .env and .cache files
└── README.md
```
