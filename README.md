# NHL Team Statistics: From Web Data to an Analysis-Ready Dataset

## 1. The Problem

Useful data is often publicly available on websites, but it is not always provided in a format that can be directly analysed.

Sports statistics are a good example. Team performance information may be presented in HTML tables designed for human viewing rather than as structured datasets that can be easily queried, compared, or reused.

This project addresses a practical data-collection problem:

> **How can publicly available NHL team performance statistics be systematically collected from a web page and transformed into a structured dataset that is ready for downstream analysis?**

The objective was therefore not simply to scrape a webpage. It was to demonstrate an end-to-end process for moving from **web-based information to structured analytical data**.

The workflow was:

**Identify → Extract → Structure → Validate → Export**

---

## 2. Data Collection Questions

The project was guided by the following questions:

- What team performance information is available on the target webpage?
- How can the relevant records be extracted programmatically rather than manually?
- How can the extracted HTML data be converted into a structured tabular format?
- Can the resulting dataset be exported in a form that can be reused for statistical or analytical work?

The main objective was to create a reproducible collection process rather than manually copying information from the webpage.

---

## 3. Data Source

The data was collected from the **Scrape This Site** NHL team statistics page:

[https://www.scrapethissite.com/pages/forms/](https://www.scrapethissite.com/pages/forms/)

The page contains historical NHL team statistics including:

- Team Name
- Year
- Wins
- Losses
- OT Losses
- Win %
- Goals For (GF)
- Goals Against (GA)
- Goal Differential (+/-)

The source page presents these statistics in HTML form, making it suitable for demonstrating programmatic extraction.

---

## 4. Methodology

The data collection process followed a structured workflow.

### Step 1: Access the webpage

An HTTP request was sent to the target page using the `requests` library.

The purpose was to retrieve the HTML content programmatically rather than manually collecting records.

### Step 2: Parse the HTML

The retrieved HTML was parsed using **BeautifulSoup**.

This made it possible to navigate the page structure and identify the relevant elements containing the team statistics.

### Step 3: Identify the data table

The HTML structure was inspected to locate the table containing the NHL statistics.

Class selectors were used to identify the relevant table elements.

### Step 4: Extract the records

The column headers and individual table rows were extracted from the HTML.

The extracted values included team names, seasons, wins, losses, overtime losses, win percentage, goals for, goals against, and goal differential.

### Step 5: Structure the data

The extracted records were converted into a **Pandas DataFrame**.

This transformed the web-based information into a tabular structure that could be inspected, manipulated, and analysed programmatically.

### Step 6: Export the dataset

The structured DataFrame was exported to:

`Hockey.csv`

The result is a reusable dataset that can serve as an input to downstream statistical analysis or visualisation.

---

## 5. Analytical Readiness

Although the main focus of this project is data collection, the final output is designed with downstream analysis in mind.

Once structured, the dataset can support questions such as:

- How has team performance changed across seasons?
- Which teams recorded the highest win percentages?
- How does goal differential relate to winning performance?
- Which teams consistently performed well across multiple seasons?
- How has league-level performance changed over time?

These questions were not the primary objective of this project, but they demonstrate why converting web content into structured data is useful.

---

## 6. Output

The final output is a structured CSV dataset:

`Hockey.csv`

The file contains NHL team statistics collected from the target webpage and organised into a tabular format suitable for further analysis.

---

## 7. What This Project Demonstrates

The project demonstrates a practical web-data collection workflow rather than web scraping as an isolated programming exercise.

The main capabilities demonstrated include:

- programmatic retrieval of web content;
- HTML parsing with BeautifulSoup;
- identifying and extracting structured information from webpages;
- converting scraped records into a Pandas DataFrame;
- preparing web-derived information for downstream analysis;
- exporting structured datasets for reuse.

More broadly, the project demonstrates the ability to bridge the gap between **information published on the web and data that can be used analytically**.

---

## 8. Limitations

The extraction process depends on the structure of the source webpage.

If the website changes its HTML structure, class names, table layout, or pagination behaviour, the scraper may require modification.

The project also focuses on extracting the available statistics rather than independently verifying the accuracy of the underlying source data.

The resulting dataset should therefore be understood as a structured representation of the information provided by the source webpage.

---

## 9. Tools & Libraries

- Python
- `requests`
- `BeautifulSoup` (`bs4`)
- `pandas`

---

## 10. Project Outcome

The project successfully demonstrates a reproducible workflow for transforming publicly available web-based information into an analysis-ready dataset.

The key transition is:

**Webpage → Raw HTML → Extracted Records → Structured DataFrame → CSV Dataset**

This creates a foundation for subsequent statistical analysis, visualisation, or modelling.

---

## 11. Author

**Justus Onyango**

Data Collection & Web Scraping Portfolio Project
