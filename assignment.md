# Assignment

## Brief

Write the Python codes for the following questions.

## Instructions

Paste the answer as Python in the answer code section below each question.

### Question 1

Question: The scraping of `https://www.scrapethissite.com/pages/forms/` in the last section assumes a hardcoded (fixed) no of pages. Can you improve the code by removing the hardcoded no of pages and instead use the `»` button to determine if there are more pages to scrape? Hint: Use a `while` loop.

```python
def parse_and_extract_rows(soup: BeautifulSoup):
    """
    Extract table rows from the parsed HTML.

    Args:
        soup: The parsed HTML.

    Returns:
        An iterator of dictionaries with the data from the current page.
    """
    header = soup.find('tr')
    headers = [th.text.strip() for th in header.find_all('th')]
    teams = soup.find_all('tr', 'team')
    for team in teams:
        row_dict = {}
        for header, col in zip(headers, team.find_all('td')):
            row_dict[header] = col.text.strip()
        yield row_dict
```

Answer:

```python
rows = []
page = 1

r = requests.get(f"https://www.scrapethissite.com/pages/forms/?page_num={page}")
#Use BeautifulSoup to parse the HTML. Transforms the raw HTML content of the webpage into a BeautifulSoup object
soup = BeautifulSoup(r.text, "html.parser")
# build a dictionary of info extracted from the website
for row_dict in parse_and_extract_rows(r.text):
        rows.append(row_dict)

#using 'Inspect Elements' under Chrome's Developer option, identify the tag and class name of the arrow that appears on a page that is not the last.
while soup.find('a', {'aria-label'="Next"}):
    #moves to the next page
    page += 1
    #continue building the dictionary
    r = requests.get(f"https://www.scrapethissite.com/pages/forms/?page_num={page}")
    for row_dict in parse_and_extract_rows(r.text):
        rows.append(row_dict)
    # pause for 1 second between requests
    time.sleep(1)
```

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
