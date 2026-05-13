# YouTube Trending Videos Analysis
 
> **Exploratory Data Analysis on Global YouTube Trending Videos (2017–2018)**
 
Analysis of YouTube trending video data across 10 countries using Python and Pandas.
The dataset covers trending videos from November 2017 to June 2018.
 
---
 
## Dataset
 
The dataset contains trending video statistics from 10 countries:
 
| Code | Country        |
|------|----------------|
| CA   | Canada         |
| DE   | Germany        |
| FR   | France         |
| GB   | United Kingdom |
| IN   | India          |
| JP   | Japan          |
| KR   | South Korea    |
| MX   | Mexico         |
| RU   | Russia         |
| US   | United States  |
 
**Files:**
- `data/` — CSV files per country (`CAvideos.csv`, `DEvideos.csv`, ...)
- `catagories/` — JSON files with video category metadata per country
---
 
## Project Structure
 
```
CS_project_2025/
├── data/
│   ├── CAvideos.csv
│   ├── DEvideos.csv
│   └── ...
├── catagories/
│   ├── CA_category_id.json
│   ├── DE_category_id.json
│   └── ...
├── notebooks/
│   └── Main.ipynb      <- Main analysis notebook
└── README.md
```
 
---
 
## Analysis Tasks
 
The notebook `Main.ipynb` covers the following tasks:
 
| # | Task |
|---|------|
| 1 | Load and concatenate all CSV files into a single DataFrame with a `country` column |
| 2 | Extract all videos with no tags (`[none]`) |
| 3 | Total number of views per channel |
| 4 | Filter out videos with disabled comments/ratings or errors into a separate `excluded` DataFrame |
| 5 | Add a `like_ratio` column (likes / dislikes) |
| 6 | Cluster `publish_time` into 10-minute intervals |
| 7 | Per interval: video count, average likes, average dislikes |
| 8 | Count videos per tag (treating `[none]` as a valid tag) |
| 9 | Find the tag with the largest number of videos |
| 10 | Per (tag, country) pair: average like/dislike ratio |
| 11 | Per (trending\_date, country) pair: video with the largest number of views |
| 12 | Split `trending_date` into year, month, day columns |
| 13 | Per (month, country) pair: video with the largest number of views |
| 14 | Load and parse all JSON category files |
| 15 | Per country: number of videos with a non-assignable category |
 
---
 
## Key Findings
 
- **Most viewed video overall:** Luis Fonsi & Demi Lovato — *Échame La Culpa* (143M views, GB)
- **Most common tag:** `"funny"` (14,969 videos), excluding `[none]`
- **Most used tag (including none):** `[none]` — 37,698 videos have no tags
- **Excluded videos:** 2,620 rows removed (disabled comments + ratings, or video errors)
- **Non-assignable categories:** India (884) and Russia (780) have the most videos
  in non-assignable categories; Japan has zero
---
 
## Installation
 
```bash
# Clone the repository
git clone https://github.com/aminentezari/CS_project_2025.git
cd CS_project_2025
 
# Install dependencies
pip install pandas numpy
```
 
---
 
## Usage
 
```bash
# Open the notebook
jupyter notebook notebooks/Main.ipynb
```
 
Make sure the `data/` and `catagories/` folders are in place before running.
 
---
 
## Dependencies
 
| Package  | Purpose                    |
|----------|----------------------------|
| `pandas` | Data loading and analysis  |
| `numpy`  | Numerical operations       |
| `json`   | Parsing category JSON files|
| `pathlib`| File path handling         |
 
---
 
## Author
 
**Amin Entezari**
- GitHub: [aminentezari](https://github.com/aminentezari)
- LinkedIn: [Amin Entezari](https://www.linkedin.com/in/aminentezari)
