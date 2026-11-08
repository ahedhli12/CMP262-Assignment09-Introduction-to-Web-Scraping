# Web Scraping — A Beginner's Guide
**CMP 262 | Prof. Amjed Hedhli**

## What is web scraping?
Web scraping means using a program to extract information from a webpage. For example, a program could collect product names and prices so you can compare them in pandas.

The usual process is:
1. Choose a question and a permitted source.
2. Inspect the HTML.
3. Obtain the HTML.
4. Extract the values.
5. Clean the values and organize them in rows and columns.
6. Analyze the resulting dataset.

In this assignment, you practice steps 2–5 with a local file and plan the website portion. A local file makes it easier to learn without network errors or changing webpages.

## HTML is the page's structure
HTML is a markup language. It describes elements such as headings, paragraphs, and tables. Python is the programming language we use to read and process that structure.

```html
<p class="price">12 dollars</p>
```
- `p` is the tag name.
- `<p ...>` opens the element; `</p>` closes it.
- `class="price"` is an attribute that labels the element.
- `12 dollars` is the text inside it.

| Item | Purpose | Example |
|---|---|---|
| `h1` | Main heading | Page title |
| `h2` | Section heading | Product name |
| `p` | Paragraph | Price or description |
| `div` | Group of elements | One product record |
| `a` | Link | Its href attribute contains the destination |
| `table`, `tr`, `th`, `td` | Table, row, heading cell, data cell | A statistics table |
| `class` | Label shared by multiple elements | Many products can have class="product" |
| `id` | Identifier intended to be unique within a page | id="page-title" |

## Beautiful Soup turns HTML into searchable objects
The package is installed as **beautifulsoup4**, but imported from **bs4**.

This demonstration uses different data from your course exercise:
```python
from bs4 import BeautifulSoup

html = '<div class="product"><h2>Pencil</h2><p class="price">2 dollars</p></div>'
soup = BeautifulSoup(html, "html.parser")

# Find one product group.
product = soup.find("div", class_="product")

# Extract the heading text inside that group.
name = product.find("h2").get_text(strip=True)
print(name)  # Pencil
```
Use `class_` with an underscore because `class` has a special meaning in Python.

## Find one or find many?
| Expression | Result |
|---|---|
| `soup.find("h1")` | First matching element, or None |
| `soup.find_all("div", class_="product")` | Collection of matching elements |
| `soup.find(id="page-title")` | Element with that ID, or None |
| `soup.select(".product")` | Collection matching a CSS class selector |
| `soup.select("#page-title")` | Collection matching a CSS ID selector |

A dot means a class in a CSS selector; a hash means an ID. A class name passed to `class_=` does not need a dot.

If you get an error involving `None`, check whether your selector actually found an element.

## Read a local file
```python
from pathlib import Path

# This is a local file read, not a request to a website.
html_text = Path("practice.html").read_text(encoding="utf-8")
```
If the file cannot be found, check the notebook's working folder and open the repository folder in VS Code.

## From text to a dataset
HTML text is usually a string. For a value such as "2 dollars", separate the number from its label and convert it to a numeric type before calculating.

A list of dictionaries can become a DataFrame. Each dictionary represents one row; its keys become column names. Use clear names and save a CSV without the pandas index.

## Inspecting a real page
Right-click the data and choose **Inspect** to see the element. **View Page Source** shows the delivered HTML. These may differ: JavaScript can add content after the page loads. If your data is absent from the delivered HTML, choose a simpler source for this assignment.

Find the repeated container for one record first. Then identify the elements inside it. A precise plan explains both where the data is and how multiple pages will be handled.

## Responsible planning
- Check the site's robots.txt and relevant terms or scraping policy.
- robots.txt gives crawler guidance; it is not a complete permission or licensing statement.
- If the file is absent, report that observation rather than claiming unrestricted access.
- Use public, non-personal data and a small scope.
- Plan a pause between requests and stop on blocking or repeated errors.
- Do not bypass login requirements, CAPTCHAs, or other access controls.
- Prefer an official downloadable dataset or API when it is available and suitable.

## Common mistakes
- Finding only the first record when you need all records.
- Extracting names and values separately without keeping the correct pairs together.
- Saving "3 credits" as text when a numeric credits column is required.
- Forgetting to rerun extraction after editing the HTML.
- Proposing questions that cannot be answered with the selected fields.

## Your final check
Your edited practice page has four courses. Your notebook extracts all four, saves course_name and integer credits, and contains your explanations. Your website plan includes five questions, a specific extraction plan, and documented restrictions. See the README for the full 100-point rubric.
