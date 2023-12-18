# Jobs Scraper API

[![Oxylabs promo code](https://user-images.githubusercontent.com/129506779/250792357-8289e25e-9c36-4dc0-a5e2-2706db797bb5.png)](https://oxylabs.go2cloud.org/aff_c?offer_id=7&aff_id=877&url_id=112)

Oxylabs’ [Jobs Scraper](https://oxylabs.io/products/scraper-api/web/jobs-scraper?utm_source=github&utm_medium=repositories&utm_campaign=product) is a data gathering solution allowing you to extract real-time information from any jobs website effortlessly. This brief guide explains how a Jobs Scraper works and provides code examples to understand better how you can use it hassle-free.

### How it works

You can obtain job results by providing your own URLs to our service. We will return the HTML for any jobs page you specify.

#### Python code example

The example below illustrates how you can obtain the HTML of a sample job posting from [indeed.com](https://www.indeed.com/companies/best-agriculture-companies)
```python
import requests
from pprint import pprint

# Structure payload.
payload = {
    'source': 'universal',
    'url': 'https://www.indeed.com/companies/best-agriculture-companies'
}

# Get response.
response = requests.request(
    'POST',
    'https://realtime.oxylabs.io/v1/queries',
    auth=('user', 'pass1'),
    json=payload,
)

# Instead of response with job status and results url, this will return the
# JSON response with the result.
pprint(response.json())
```
Find code examples for other programming languages [**here**](https://github.com/oxylabs/jobs-scraper/tree/main/code%20examples)

#### Output Example
```json
{
  "results": [
    {
      "content": " ... </html>",
      "created_at": "2023-12-18 11:39:49",
      "updated_at": "2023-12-18 11:40:05",
      "page": 1,
      "url": "https://www.indeed.com/companies/best-agriculture-companies",
      "job_id": "7142478560421252097",
      "status_code": 613
    }
  ]
}
```
With our Jobs Scraper, you can conveniently extract public data from any job web page. Gather necessary job information such as company profiles, salary ranges, job descriptions, location, and qualifications needed to study market trends and stay ahead in your career search. If you have any queries, reach out to our support team using live chat or drop us an email at hello@oxylabs.io.
