<div align="center">

# 🔎 Indeed Job Market Scraper & Skill Intelligence Pipeline

### 🚀 Automated Job Data Extraction • Data Cleaning • Skill Detection • Excel & CSV Reporting

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&duration=3000&pause=1000&color=2F81F7&center=true&vCenter=true&width=850&lines=Automate+Indeed+Job+Data+Collection;Clean+and+Transform+Job+Listings;Detect+Technical+Skills;Export+Analysis-Ready+CSV+%26+Excel+Reports" alt="Typing Animation">

<br>

<img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white">
<img src="https://img.shields.io/badge/Apify-API-00D084?style=for-the-badge&logo=apify&logoColor=white">
<img src="https://img.shields.io/badge/Pandas-Data%20Processing-150458?style=for-the-badge&logo=pandas&logoColor=white">
<img src="https://img.shields.io/badge/BeautifulSoup-HTML%20Parsing-4B8BBE?style=for-the-badge">
<img src="https://img.shields.io/badge/OpenPyXL-Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white">

<br><br>

[![GitHub Repository](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge\&logo=github)](https://github.com/Prabanjan29/Cybernaut-Project-Indeed-Web-Scraper)
[![Python](https://img.shields.io/badge/Built%20With-Python-3776AB?style=for-the-badge\&logo=python\&logoColor=white)](https://www.python.org/)

</div>

---

## 📌 Overview

**Indeed Job Market Scraper & Skill Intelligence Pipeline** is a Python-based job data collection and preprocessing project that uses the **Apify API** to retrieve Indeed job listings and convert them into structured datasets.

The pipeline accepts a job title, starts an Apify Actor, retrieves the resulting job data, cleans HTML descriptions, detects selected technical skills, removes duplicate listings, sorts the results, and exports the processed data into **CSV and formatted Excel files**.

> 🎯 **Goal:** Turn raw job-listing data into a clean, structured dataset that can be used for job-market and skill-demand analysis.

---

## ⚡ What This Project Does

```text
                 🔎 JOB TITLE
                      │
                      ▼
              ┌───────────────┐
              │   APIFY API   │
              │ Indeed Actor  │
              └───────┬───────┘
                      │
                      ▼
              📦 RAW JOB DATA
                      │
                      ▼
            ┌───────────────────┐
            │  DATA CLEANING    │
            │ HTML → Plain Text │
            └─────────┬─────────┘
                      │
                      ▼
            🧑‍💻 SKILL DETECTION
                      │
                      ▼
            ♻️ DUPLICATE REMOVAL
                      │
                      ▼
             📅 SORTING RESULTS
                      │
                      ▼
            ┌───────────────────┐
            │ STRUCTURED DATA   │
            └───────┬─────┬─────┘
                    │     │
                    ▼     ▼
                 📄 CSV  📊 Excel
```

---

# ✨ Key Features

<table>
<tr>
<td width="50%">

### 🔎 Automated Scraping

Uses the **Apify API** to start an Indeed scraping Actor and retrieve job listings automatically.

</td>

<td width="50%">

### 🧹 Data Cleaning

Uses **BeautifulSoup** to remove HTML markup and convert descriptions into readable text.

</td>
</tr>

<tr>
<td width="50%">

### 🧑‍💻 Skill Detection

Identifies predefined technical skills such as Python, SQL, Excel, AWS and Machine Learning.

</td>

<td width="50%">

### ♻️ Duplicate Removal

Removes duplicate listings using:

`Job Title + Company + Location`

</td>
</tr>

<tr>
<td width="50%">

### 📅 Job Sorting

Sorts processed records using the `Posted` field so newer listings appear first.

</td>

<td width="50%">

### 📊 Excel & CSV Export

Creates structured CSV and formatted Excel reports for further analysis.

</td>
</tr>
</table>

---

# 🛠️ Technology Stack

<div align="center">

|      Technology      | Purpose                         |
| :------------------: | :------------------------------ |
|     🐍 **Python**    | Core processing and automation  |
|   🔌 **Apify API**   | Job data collection             |
|    🌐 **Requests**   | API communication               |
|     🐼 **Pandas**    | Data transformation             |
| 🥣 **BeautifulSoup** | HTML parsing and cleaning       |
|    📊 **OpenPyXL**   | Excel generation and formatting |
| 🔐 **python-dotenv** | Environment-variable management |

</div>

---

# 🧠 Skill Detection

The current implementation uses a predefined keyword-based approach.

### Supported Skills

```text
🐍 Python
☕ Java
🗄️ SQL
📊 Excel
🤖 Machine Learning
☁️ AWS
🌐 Django
🔥 Flask
```

When a skill appears in a cleaned job description, it is added to the:

```text
Skills (detected)
```

column.

> ℹ️ This is **keyword-based skill detection**, not a machine-learning or NLP classification model.

---

# 🧹 Data Processing Pipeline

The processing stage performs several transformations.

### 1️⃣ HTML Cleaning

Job descriptions returned by the source may contain HTML.

The project uses BeautifulSoup to convert:

```html
<p>Experience with <b>Python</b> and SQL</p>
```

into readable text:

```text
Experience with Python and SQL
```

### 2️⃣ Skill Detection

The cleaned description is checked against the predefined skill list.

### 3️⃣ Duplicate Removal

Duplicate records are removed using:

```python
df.drop_duplicates(
    subset=["Job Title", "Company", "Location"],
    inplace=True
)
```

### 4️⃣ Sorting

Results are sorted using the `Posted` field.

### 5️⃣ Export

The processed DataFrame is exported to:

```text
📄 CSV
📊 Excel
```

---

# 📊 Dataset Structure

The generated dataset contains:

| Column              | Description                                 |
| ------------------- | ------------------------------------------- |
| `Job ID`            | Identifier associated with the listing      |
| `Job Title`         | Position title                              |
| `Company`           | Hiring company                              |
| `Location`          | Job location                                |
| `Remote`            | Remote indicator derived from location text |
| `Salary`            | Salary information when available           |
| `Job Type`          | Job type returned by the source             |
| `Rating`            | Company rating when available               |
| `Reviews`           | Number of company reviews                   |
| `Posted`            | Posting information                         |
| `Benefits`          | Available benefits                          |
| `Skills (detected)` | Skills identified through keyword matching  |
| `Apply Link`        | Job application URL                         |
| `Description`       | Cleaned job description                     |

---

# 📂 Repository Structure

```text
Cybernaut-Project-Indeed-Web-Scraper/
│
├── 🐍 scraper.py
│
├── 📄 Data Analyst_cleaned_jobs.csv
│
├── 📊 Data Analyst_cleaned_jobs.xlsx
│
├── 📑 Indeed Web Scraper Report.pdf
│
└── 📘 README.md
```

---

# 🚀 Getting Started

## 1️⃣ Prerequisites

You need:

* Python 3.x
* An Apify account
* Access to an Indeed scraping Actor
* Internet connection

---

## 2️⃣ Install Dependencies

```bash
pip install requests pandas beautifulsoup4 python-dotenv openpyxl
```

---

## 3️⃣ Configure Apify

Create a `.env` file in the project directory:

```env
APIFY_TOKEN=your_apify_token
ACTOR_ID=your_actor_id
```

⚠️ **Never commit `.env` or your API token to GitHub.**

---

## 4️⃣ Run the Scraper

```bash
python scraper.py
```

The program will ask:

```text
Enter Job Title:
```

Example:

```text
Enter Job Title: Data Analyst
```

The script then:

```text
🚀 Starts Apify Actor
        ↓
⏳ Waits for completion
        ↓
📥 Retrieves dataset
        ↓
🧹 Cleans descriptions
        ↓
🧑‍💻 Detects skills
        ↓
♻️ Removes duplicates
        ↓
📅 Sorts records
        ↓
📄 Creates CSV
        ↓
📊 Creates formatted Excel
```

---

# 📁 Output Files

For a search such as:

```text
Data Analyst
```

the generated files are:

```text
Data Analyst_cleaned_jobs.csv
Data Analyst_cleaned_jobs.xlsx
```

### 📄 CSV

The CSV contains the structured processed dataset.

### 📊 Excel

The Excel output is formatted with:

* Bold headers
* Styled header background
* Center-aligned headers
* Automatically adjusted column widths

---

# 📈 Example Analytical Use Cases

The resulting dataset can be used for further analysis such as:

### 🧑‍💻 Skill Demand

Which technical skills are most frequently requested?

### 🏢 Company Analysis

Which companies are hiring for similar roles?

### 🌎 Location Analysis

Which locations contain the most job listings?

### 🏠 Remote Job Analysis

How many listings are identified as remote?

### 💰 Salary Analysis

What salary information is available across collected listings?

### 🔗 Skill Combinations

Which technical skills frequently appear together?

---

# 🔐 Security

API credentials should **never** be hard-coded in a public repository.

Recommended `.gitignore`:

```gitignore
.env
__pycache__/
*.pyc
```

### ⚠️ Important

If an API token has ever been committed to a public GitHub repository, **revoke or rotate it immediately** and replace it with a new credential stored through environment variables.

---

# ⚠️ Current Limitations

The current implementation has several limitations:

* Skill detection uses a predefined keyword list.
* Keyword matching can produce false positives.
* Only the first **500 characters** of each description are stored.
* The script processes up to **50 jobs** from the retrieved dataset.
* Remote classification is based on `"remote"` appearing in the location text.
* The `Posted` field is sorted based on the value returned by the source.
* Salary and optional fields depend on the information available in the listing.
* The project does not currently use a trained ML/NLP model for skill extraction.

---

# 🚧 Future Improvements

```text
🔹 NLP-based skill extraction
🔹 Expanded technical skill dictionary
🔹 Job seniority classification
🔹 Salary normalization
🔹 Location standardization
🔹 Improved date parsing
🔹 Job-ID-based duplicate detection
🔹 PostgreSQL database integration
🔹 Scheduled scraping
🔹 Automated data refresh
🔹 Power BI integration
🔹 Skill-demand trend analysis
🔹 Job-category classification
```

---

# 🎯 What This Project Demonstrates

<div align="center">

### Technical Skills

`Python` • `REST API` • `Apify` • `Web Data Extraction` • `Pandas` • `BeautifulSoup`

### Data Skills

`Data Cleaning` • `Data Transformation` • `Deduplication` • `Keyword Extraction`

### Reporting Skills

`CSV Processing` • `Excel Automation` • `OpenPyXL` • `Structured Data Export`

</div>

---

# 📑 Project Deliverables

The repository contains:

| Deliverable     | Description                                |
| --------------- | ------------------------------------------ |
| 🐍 `scraper.py` | Main Python scraping and processing script |
| 📄 `.csv`       | Structured processed job dataset           |
| 📊 `.xlsx`      | Formatted Excel version of the dataset     |
| 📑 `.pdf`       | Project report                             |
| 📘 `README.md`  | Project documentation                      |

---

# 👤 Author

<div align="center">

## **Srideep Sarkar**

### Data Analyst | Python | SQL | Data Analytics | Data Mining 

<img src="https://img.shields.io/badge/GitHub-srideepgit-181717?style=for-the-badge&logo=github&logoColor=white">
</a>

<br><br>

⭐ **If you find this project useful, consider giving the repository a star!**

</div>
