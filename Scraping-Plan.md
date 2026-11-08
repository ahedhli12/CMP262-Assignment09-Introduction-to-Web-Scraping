# Assignment 9 — Website Data-Collection Plan

Name:
Date:

## 1. Website and scope
- Website name:
- Main URL:
- Exact data-page URL:
- Why this dataset interests me:
- Small collection scope (how many pages/records):
- Confirm that the pages are public and contain no personal data:

## 2. Five analysis questions
For each question, name the fields you would need.
1. Question / fields:
2. Question / fields:
3. Question / fields:
4. Question / fields:
5. Question / fields:

## 3. Data fields
| Field | Example value | Intended type | Possible cleaning |
|---|---|---|---|
| TODO | TODO | TODO | TODO |

## 4. HTML extraction plan
- How I inspected the page (View Source or Inspect):
- Short HTML excerpt from the data area (remove any private information):
```html
<!-- Paste a small excerpt here. -->
```
- Repeated element containing one record:
- Tags/classes/IDs or table identifier:
- Proposed Beautiful Soup selector and why it matches:
- Is the data in the downloaded HTML, or only visible after JavaScript loads?
- If the HTML does not contain it, what simpler source will I use?

## 5. Multiple pages
- One page or multiple pages:
- Two actual example URLs, if using multiple pages:
- Naming/pagination pattern, or why no pattern is needed:
- Planned maximum page count:
- How I will avoid duplicate records:
- Planned output CSV filename:

## 6. Restrictions and responsible collection
- Date checked:
- Exact robots.txt URL:
- Relevant user-agent group and Allow/Disallow directives:
- Paths affected by those rules:
- Terms or scraping-policy URL and relevant guidance:
- My decision (proceed with a small permitted plan / choose another source / seek permission):
- Planned pause between requests and stopping conditions:
- What I will do if the server returns an error or blocks access:

If robots.txt is absent or no applicable restrictions are listed, state exactly what you observed. That alone does not establish permission. Do not invent rules or bypass blocks.

## 7. Next steps
Explain how you would collect, clean, and analyze the data later. You do not need to run a live scraper for this assignment.
