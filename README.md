# flipkart-phone-data-scraper
Python web scraping project that extracts and cleans mobile phone listings (price, ratings, specifications) from Flipkart using BeautifulSoup, Requests, Regex, and Pandas, exporting structured data to CSV.
# Flipkart Phone Web Scraper

A Python-based web scraping project that extracts real-time mobile phone product data — name, price, rating, number of reviews, and detailed specifications — from Flipkart's e-commerce search results and transforms the raw HTML into a clean, structured dataset for analysis.

## Overview

This project demonstrates end-to-end web scraping and data extraction: sending HTTP requests with browser-like headers to bypass bot detection, parsing HTML using BeautifulSoup, handling pagination across multiple result pages, and applying regular expressions to extract structured attributes (Brand, Processor, RAM, ROM, Battery, Display Size, Camera) from unstructured product feature text. The final output is a cleaned, analysis-ready CSV file.

## Key Features

- **Automated Web Scraping**: Extracts product data from Flipkart search result pages using the `requests` library
- **Anti-Bot Handling**: Uses custom User-Agent headers to simulate real browser requests and avoid HTTP 403 errors
- **HTML Parsing**: Uses BeautifulSoup for DOM traversal and targeted element extraction
- **Multi-Page Scraping**: Loops through multiple pages of search results to build a larger dataset
- **Regex-Based Feature Extraction**: Custom regular expressions parse product specifications (Processor, RAM, ROM, Battery capacity, Display size, Camera) from raw text
- **Data Cleaning & Transformation**: Uses Pandas and NumPy to handle missing values, convert data types, and clean price/rating fields
- **Structured Data Export**: Outputs a clean, tabular dataset to CSV for downstream analysis or machine learning use cases

## Tech Stack

| Category | Tools / Libraries |
|---|---|
| Programming Language | Python |
| Web Scraping | Requests, BeautifulSoup, Selenium |
| Data Manipulation | Pandas, NumPy |
| Text Processing | Regular Expressions (re) |
| Data Visualization | Matplotlib, Seaborn |
| Environment | Jupyter Notebook |

## Project Workflow

1. **Request Handling** – Send HTTP GET requests to Flipkart with appropriate headers to avoid access restrictions
2. **HTML Parsing** – Parse the response content using BeautifulSoup's HTML parser
3. **Data Extraction** – Identify and extract product name, price, rating, and review count using HTML class selectors
4. **Pagination Loop** – Iterate through multiple result pages to scale data collection
5. **Feature Engineering** – Apply regex patterns to pull out Brand, Processor, RAM, ROM, Battery, Display Size, and Camera details from raw specification text
6. **Data Cleaning** – Convert price and rating fields to numeric types; handle missing values
7. **Export** – Save the final structured dataset as a CSV file

## Dataset Fields

| Column | Description |
|---|---|
| Brand | Phone manufacturer/brand name |
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

## Installation

```bash
git clone https://github.com/<your-username>/flipkart-phone-web-scraper.git
cd flipkart-phone-web-scraper
pip install -r requirements.txt
```

## Requirements

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

1. Open `Web_Scraping.ipynb` in Jupyter Notebook
2. Run all cells sequentially
3. The scraped and cleaned dataset will be saved as `Flipkart Phones.csv` in the project directory

## Use Cases

- E-commerce price monitoring and comparison
- Market research and competitor analysis
- Building datasets for machine learning / price prediction models
- Practicing web scraping, data cleaning, and regex skills

## Disclaimer

This project is intended for educational and portfolio purposes only. Web scraping may be subject to a website's Terms of Service; always review and comply with the target website's `robots.txt` and usage policies before scraping.


## License

This project is licensed under the MIT License.
