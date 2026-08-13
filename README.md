# Flipkart Phone Data Scraper

A Python web scraping project that extracts, cleans, and structures mobile phone listing data from Flipkart. The scraper collects product name, price, rating, number of ratings/reviews, and detailed specifications (processor, RAM, ROM, battery, display size, camera), then exports the final dataset to a CSV file for analysis.

## Overview

This project demonstrates an end-to-end **data extraction and data cleaning pipeline**: sending HTTP requests to a live e-commerce website, parsing raw HTML, handling anti-bot restrictions with custom headers, extracting unstructured text with regular expressions, and transforming the result into a clean, analysis-ready dataset using Pandas.

## Key Features

- **Web Scraping**: Automated data collection from Flipkart search result pages using `requests` and `BeautifulSoup`.
- **HTTP Header Handling**: Uses a custom `User-Agent` header to bypass basic bot-detection (403 Forbidden) restrictions.
- **Multi-Page Scraping**: Iterates through multiple paginated search result pages to build a larger dataset.
- **HTML Parsing**: Locates and extracts nested product elements (name, price, rating, reviews, specifications) using CSS class-based selectors.
- **Regular Expressions (Regex)**: Extracts structured attributes — Brand, Processor, RAM, ROM, Battery, Display Size, and Camera — from unstructured specification text.
- **Data Cleaning & Transformation**: Converts scraped strings into proper numeric types (float/int), handles missing values with NumPy, and removes currency symbols and formatting artifacts.
- **Data Export**: Outputs the final structured dataset as a CSV file using Pandas.

## Tech Stack / Skills Demonstrated

| Category | Tools / Libraries |
|---|---|
| Language | Python |
| Web Scraping | Requests, BeautifulSoup4, Selenium |
| Data Processing | Pandas, NumPy |
| Data Extraction | Regular Expressions (re) |
| Data Visualization (setup) | Matplotlib, Seaborn |
| Data Format | CSV |
| Environment | Jupyter Notebook |

**Core competencies:** Web Scraping, HTML Parsing, Data Extraction, Data Cleaning, Data Wrangling, Regex Pattern Matching, Automation, Python Programming, Pandas DataFrames, Exploratory Data Analysis (EDA) preparation.

## Project Structure

```
flipkart-phone-data-scraper/
│
├── Web_Scraping.ipynb        # Main Jupyter Notebook with full scraping & cleaning pipeline
├── Flipkart_Phones.csv       # Final extracted and cleaned dataset (output)
└── README.md                 # Project documentation
```

## Dataset Columns

The final cleaned dataset includes the following columns:

| Column | Description |
|---|---|
| Brand | Phone brand/manufacturer |
| Product_name | Full product title |
| Processor | Processor/chipset details |
| RAM | RAM capacity |
| ROM | Internal storage capacity |
| Battery | Battery capacity (mAh) |
| Display_Size | Screen size (inches) |
| Camera | Camera specification summary |
| No_of_ratings | Total number of ratings |
| No_of_reviews | Total number of reviews |
| Rating | Average product rating |
| Price | Product price (INR) |

## How It Works

1. **Send Request**: Send an HTTP GET request to a Flipkart search URL with a browser-like `User-Agent` header to avoid a 403 response.
2. **Parse HTML**: Parse the returned HTML content with BeautifulSoup to locate product containers.
3. **Extract Fields**: For each product block, extract name, price, rating, review count, and raw specification text.
4. **Paginate**: Repeat the request/parse process across multiple result pages to scale the dataset.
5. **Clean Data**: Apply regex patterns to pull structured fields (Processor, RAM, ROM, Battery, Display, Camera) out of the raw specification string, and convert price/rating fields to numeric types.
6. **Export**: Reorder columns and save the final DataFrame to a CSV file.

## Installation

```bash
git clone https://github.com/<your-username>/flipkart-phone-data-scraper.git
cd flipkart-phone-data-scraper
pip install -r requirements.txt
```

### Requirements

```
numpy
pandas
matplotlib
seaborn
requests
beautifulsoup4
selenium
```

## Usage

1. Open `Web_Scraping.ipynb` in Jupyter Notebook or JupyterLab.
2. Run all cells sequentially to scrape live data from Flipkart.
3. The final cleaned dataset will be saved as a CSV file in the project directory.

> **Note:** Website structure and CSS class names on Flipkart may change over time, which can affect scraping accuracy. Always review and update the class selectors if the scraper stops returning data.

## Future Improvements

- Add error handling and retry logic for failed requests.
- Store data directly into a database (SQL/MongoDB) instead of CSV.
- Add data visualization (price distribution, brand-wise comparison) using Matplotlib/Seaborn.
- Convert the notebook into a modular Python script/package with CLI support.
- Add scheduling/automation for periodic data collection.

## Disclaimer

This project is created for educational purposes to demonstrate web scraping, regex, and data cleaning techniques. Please review and comply with Flipkart's Terms of Service and `robots.txt` policy before scraping data for any purpose beyond learning.

## License

This project is licensed under the MIT License.

## Author

**Usman Makhdoomi**
- GitHub: [github.com/makhdoomiusman](https://github.com/makhdoomiusman)

Feel free to connect for feedback, suggestions, or collaboration opportunities.
