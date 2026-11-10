# College-Town Home Sales

## What this site is for

The site shows two numbers for each of the 18 college towns and cities in the dataset: how many home sales the dataset records there, and the median sale price of those sales. The dataset covers 35,442 completed sales collected in March 2026 around 11 universities.

It is for anyone comparing what homes sold for in college towns, such as students and families choosing where to live, and people studying housing near campuses. It does not show trends over time, days on market, or any measure of home quality.

## Live site

https://sixiansong.github.io/accy593-campustown-home-sales-site/

## Data notes

**Sales left out.** Sales under $10,000 are left out. That removes 40 of the 35,442 rows, which leaves 35,402 sales. The table states this rule on the page, along with how many rows were left out. Sales of exactly $10,000 or more are kept, including the high-priced ones.

**Why medians, not means.** The dataset has 31 sales over $5,000,000, the largest at $81,510,000. A single sale like that pulls an average up sharply. Across all 35,402 kept sales, the mean is $509,951 and the median is $410,000. The median is the sale price in the middle when the prices are sorted, so those few very large sales do not move it much.

**How each figure is defined.**
- **Number of sales:** the count of kept rows (sale price of $10,000 or more) for each city and state. Each row is one completed sale.
- **Median sale price:** the middle sale price of those rows. With an even number of sales, it is the average of the two middle prices. It is rounded to the nearest whole dollar.
- Cities are grouped by city and state. No rows are merged or removed for having the same street address.

**The five problems in the data description sheet, and whether they affect this page:**
1. **Days on market needs both dates, and blanks are not random.** Does not affect this page. The page shows no days-on-market figures.
2. **The street address is not unique.** Partly affects this page. The page does not remove rows that share an address, so repeated addresses are counted as separate sales. For example, the State College figures include the condo units at one address.
3. **Some prices are impossible.** Affects this page. Sales under $10,000 are left out by the rule above. The 31 sales over $5,000,000 are kept, and the median is used so they do not dominate the figures.
4. **`home_type` is wrong more often than it looks.** Does not affect this page. The page does not use `home_type`.
5. **A few values are impossible on their face.** Does not affect this page. The page uses only the city, state and sale price columns.

## Tools we used

- **Claude Code on the web**, an AI coding agent from Anthropic, used to write the page code and this README. Its project instructions are in `AGENTS.md`.
- **Plain HTML, CSS and JavaScript.** The page reads `data/college_town_home_sales.csv` in the browser and computes the table from it. No build step and no server-side code.
- **GitHub Pages**, which publishes the repository's files from `main`.

## Citation

College-town home sales dataset, version 1.0 (2026). University of Illinois-Deloitte Foundation Center for Business Emerging Technologies. Data collected March 2026.
