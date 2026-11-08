# CMP 262 — Assignment 9
## Introduction to Web Scraping: Understanding HTML and Planning Data Collection

**Instructor: Prof. Amjed Hedhli | Total: 100 points**

### Objective
Learn how HTML organizes a webpage, extract information from a local practice page with Beautiful Soup, and plan a small website data-collection project. The website portion is a proposal: you do not need to scrape a live website or perform the full analysis for this assignment.

### Getting Started
1. Create your own repository from this starter. If **Use this template** is available, select **Create a new repository**; otherwise, select **Fork**.
2. Use your personal GitHub account and name it **LastName-FirstName-CMP262-Assignment09-Web-Scraping**.
3. Make your repository public. Do not include private information or credentials.
4. Clone **your own repository**, then open its folder in Visual Studio Code.
5. Read [the student handout](Web-Scraping-Handout.md).
6. Open `practice.html` in a browser and in the VS Code editor.
7. Open `web-scraping.ipynb`, select your Python kernel, and complete every TODO.
8. Complete `Scraping-Plan.md` and `AI-Use-Report.md`.

### Setup
Use a Python environment with Jupyter, pandas, and Beautiful Soup installed. If needed, run this command in the VS Code terminal:
```bash
python -m pip install -r requirements.txt
```
Install the Python and Jupyter VS Code extensions if prompted. Choose that same environment as the notebook kernel. Open the repository folder so the notebook can find `practice.html`.

### Part 1 — HTML and Local Extraction (40 points)
- Identify tags, attributes, classes, and IDs in the practice page.
- Add a fourth course using the existing structure.
- Use Beautiful Soup to extract course names and integer credit values.
- Build a pandas DataFrame and save `data/courses.csv` without an index.
- Answer the notebook reflection questions and run every cell.

The starter demonstrates a different HTML snippet. Write your own solution for the course page.

### Part 2 — Website Data-Collection Plan (50 points)
In `Scraping-Plan.md`:
1. Identify one website and the exact page URL you want to use.
2. Write at least five questions that the available fields could answer.
3. Identify the HTML tags, classes, IDs, or table that contain the data. Include a short HTML excerpt and explain your selector.
4. Explain the page naming or pagination pattern, or explain why one page is enough.
5. Propose a small collection scope, fields, data types, cleaning steps, and output CSV filename.
6. Review the site's `robots.txt` and terms or scraping policy. Record the URLs, date checked, applicable rules, and your decision.

Do not assume a website allows scraping because a previous example used it. If access is blocked, content requires login, or restrictions prohibit your plan, explain the issue and choose a different source. Do not bypass access controls. Do not collect personal information.

### Part 3 — Reflection and Submission (10 points)
Complete the notebook reflection and `AI-Use-Report.md`. Keep all instructor questions and comments.

### Rubric
| Requirement | Points |
|---|---:|
| Identify HTML structure and explain class versus ID | 10 |
| Add a fourth course with consistent HTML | 10 |
| Extract all course names and integer credits correctly | 15 |
| Create DataFrame and save correct CSV | 5 |
| Website selection and clear scope | 5 |
| Five answerable analysis questions (3 points each) | 15 |
| Specific HTML extraction and page-navigation plan | 20 |
| Document robots.txt, terms/policy, and responsible approach | 10 |
| Reflection and AI-use report | 5 |
| Complete, organized GitHub and Blackboard submission | 5 |
| **Total** | **100** |

### Required Files
- `practice.html` with four course entries
- `web-scraping.ipynb` with your code, answers, and outputs
- `data/courses.csv` with columns `course_name` and `credits`
- `Scraping-Plan.md`
- `AI-Use-Report.md`

Retain the supplied `.github` and `.vscode` folders.

### Saving and Submitting
```bash
git status
git add .
git commit -m "Complete Assignment 9 web scraping"
git push
```
Confirm your latest work appears on GitHub. Submit your public repository link in **Blackboard Ultra**. Uploading to GitHub alone does not count as submitting.

AI may explain concepts or errors, but you must write and understand your work. Workspace settings support this approach; they do not enforce academic integrity.
