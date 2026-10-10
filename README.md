# CodeAlpha Web Scraping: E-commerce Book Data Collection

## Project Overview
This project uses Python web scraping to collect, clean, validate, and analyze book product data from [Books to Scrape](https://books.toscrape.com/), a practice website designed for web scraping exercises.

The project demonstrates how to extract product information from multiple catalogue pages, structure it into a tabular dataset, perform data-quality checks, and generate visualizations for exploratory data analysis.

## Objectives
- Collect book product information from multiple catalogue pages.
- Extract product names, prices, categories, ratings, availability, and product URLs.
- Clean and validate the collected data.
- Investigate unusual category values and preserve the original source data.
- Analyze price and rating distributions and visualize category frequencies.
- Export the dataset to CSV for further analysis.

## Tools and Technologies
- **Python** — programming and data collection
- **Requests** — retrieving webpage content
- **BeautifulSoup** — parsing HTML
- **pandas** — data cleaning, validation, and analysis
- **Matplotlib** — data visualization
- **Google Colab** — notebook environment

## Dataset Description
The final dataset contains 100 book records collected from the first five catalogue pages.

| Column | Description |
|---|---|
| Product_Name | Title of the book |
| Price | Book price represented as a numeric value |
| Category | Original category text extracted from the website |
| Rating | Book rating converted to a numeric scale from 1 to 5 |
| Availability | Availability text shown on the product listing |
| Product_URL | URL of the individual product page |
| Category_Cleaned | Category field with questionable labels mapped to `Unknown` |

## Methodology
1. Retrieved catalogue pages using HTTP requests.
2. Parsed HTML content using BeautifulSoup.
3. Extracted product details from each listing.
4. Visited individual product pages to retrieve breadcrumb category values.
5. Converted prices to numeric values and ratings to numbers.
6. Validated the dataset for missing values and duplicate product names.
7. Investigated unusual category labels found in the source website.
8. Preserved the original category values and created a cleaned category column.
9. Generated visualizations and exported the final dataset to CSV.

## Data Quality Checks
- **Records collected:** 100
- **Columns in the final dataset:** 7
- **Missing values:** 0 across the six original fields, based on the validation performed before adding the cleaned category column
- **Duplicate product names:** 0
- **Questionable category labels mapped to `Unknown`:** 14

The labels `Default` and `Add a comment` appeared in the source website's breadcrumb trail. They were mapped to `Unknown` in the cleaned column rather than being replaced with guessed categories. The original `Category` values remain available for traceability.

## Exploratory Data Analysis
The analysis examined:
- Summary statistics and the distribution of book prices
- The cheapest and most expensive books in the sample
- Average book ratings and rating frequencies
- The most frequent known categories

In the 100-book sample, Sequential Art appeared 14 times and Nonfiction appeared 12 times. Fourteen records had questionable category labels and were excluded from the known-category comparison, leaving 86 records for that chart.

These results describe the five catalogue pages collected for this project; they should not be interpreted as statistics for the entire website.

## Project Files
- `CodeAlpha_WebScraping_ipnyb.ipynb` — notebook containing the scraping, cleaning, validation, and analysis workflow
- `CodeAlpha_Ecommerce_Product_Data.csv` — exported dataset

## How to Run
1. Open the notebook in Google Colab or Jupyter Notebook.
2. Install the required packages if they are not already available:
   `pip install requests beautifulsoup4 pandas matplotlib`
3. Run the notebook cells in order.
4. Execute the CSV export cell to generate the dataset.

The notebook sends HTTP requests to the practice website. Successful execution depends on the website being accessible.

## Data Source
[Books to Scrape](https://books.toscrape.com/)


## Author
Completed as a Python web scraping and data analysis project for the CodeAlpha Data Analytics Internship.
