# ⚾ MLB Pitching Stats Scraper

This project provides a Python-based web scraper for collecting Major League Baseball (MLB) pitching statistics using Selenium and BeautifulSoup.

It supports both **individual player stats** and **team pitching stats**, across multiple seasons.

---

## 📌 Features

- ✅ Scrapes **standard** and **expanded** MLB pitching stats
- ✅ Supports **yearly range** scraping (e.g., 2003–2024)
- ✅ Handles **team-level** and **player-level** stats
- ✅ Automatically accepts cookie popups and "Later" dialogs
- ✅ Combines data from multiple pages into a single CSV file
- ✅ Cleans up duplicated columns like `PLAYER`, `TEAM`, `LEAGUE`

---

##  pip install

- Python 3.9
- Selenium
- BeautifulSoup (bs4)
- Pandas
- Chrome WebDriver (managed by `webdriver-manager`)

---

## 🚀 Installation

```bash
pip install selenium pandas beautifulsoup4 webdriver-manager
```

---

##  How to Use

### ▶ Player-level Pitching Stats

```python
from scraper import scrape_mlb_pitching

filename = "mlb_pitching_all_years.csv"
first_write = True

for year in range(2003, 2024):
    scrape_mlb_pitching(year, filename, first_write)
    first_write = False
```

### ▶ Team-level Pitching Stats

```python
from scraper import scrape_team_pitching

filename = "mlb_team_pitching_all_years.csv"
first_write = True

for year in range(2003, 2025):
    scrape_team_pitching(year, filename, first_write)
    first_write = False
```

---

## Output

- `mlb_pitching_all_years.csv` — Player-level pitching data from 2003 to 2023
- `mlb_team_pitching_all_years.csv` — Team-level pitching data from 2003 to 2024

Each row includes the `Season Year`, `PLAYER` or `TEAM`, and all corresponding stats.

---

## 📎 Notes

- This scraper only works for public data at [mlb.com/stats](https://www.mlb.com/stats)
- It uses `aria-label` attributes to extract full player names accurately
- Make sure you have Google Chrome installed

---
