to parse a website we need the beautifulsoup module, install like below.

```terminal
pip install beautifulsoup4
```


after installed:

```python
from bs4 import beautifulsoup4

with open("index.html","r") as f:
	doc = BeautifulSoup(f, "html.parser")

print(doc.prettify())

tags = doc.find_all("p")
print(tags.find_all("b"))

```

reading from a website requires the requests module

```terminal
pip install requests
```

```python
from bs4 import beautifulsoup4
import requests

url = "https://ventura.craigslist.org/search/sss?query=exercise%20equipment%20eliptical#search=1~gallery~0~0"

result = requests.get(url)
print(result.text)

```