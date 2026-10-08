# Flipkart Mobile Scraper

A web scraping project that collects data on **mobile phones under ₹50,000** from Flipkart search results and saves it to a CSV file.

## What It Collects

For each phone on the first 9 result pages:

| Column | Example |
|--------|---------|
| Product Name | OnePlus 11R 5G (Sonic Black, 256 GB) |
| Price | ₹44,398 |
| Description | RAM, storage, display, camera, battery, warranty |
| Review | 4.6 |

The output is `flipkart mobile under 50000.csv` with about 216 phones.

## Tech Stack

- Python
- Requests (download pages)
- BeautifulSoup with the lxml parser (extract data)
- Pandas (build the table and export CSV)
- Jupyter Notebook

## How to Run

```bash
git clone https://github.com/PRiNCeKUsHW/flipkart-scrap.git
cd flipkart-scrap
pip install requests beautifulsoup4 lxml pandas jupyter
jupyter notebook Flipkart.ipynb
```

Run all cells. The CSV is written to the project folder.

## How It Works

1. Loop through result pages 1 to 9 of the search "mobile under 50000".
2. Download each page with `requests` and parse it with BeautifulSoup.
3. Find product names, prices, spec lists and ratings by their CSS classes.
4. Combine the lists into a Pandas DataFrame and save it as CSV.

## Notes

- Flipkart changes its CSS class names from time to time. If the scraper returns nothing, update the class names in the notebook.
- The dataset was collected in 2023, so prices and listings are out of date.
- This project is for learning only. Please respect Flipkart's terms of use and scrape responsibly.
