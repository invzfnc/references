```python
import requests
import bs4

res = requests.get(url) # requests.models.Response

res.status_code == requests.codes.ok # Status code 200
res.raise_for_status()

res.text # Downloaded web page is stored as string

for chunk in res.iter_content(100000):
    file_open.write(chunk)

soup = bs4.BeautifulSoup(res.text, "html.parser") # bs4.BeautifulSoup

# from file
file_open = open("site.html")
soup = bs4.BeautifulSoup(file_open, "html.parser")
```

`soup.select`

|Selector passed to the `select()` method|Will match|
|---|---|
|`soup.select('div')`|All elements named `<div>`|
|`soup.select('#author')`|The element with an `id` attribute of `author`|
|`soup.select('.notice')`|All elements that use a CSS `class` attribute named `notice`|
|`soup.select('div span')`|All elements named `<span>` that are within an element named `<div>`|
|`soup.select('div > span')`|All elements named `<span>` that are _directly_ within an element named `<div>`, with no other element in between|
|`soup.select('input[name]')`|All elements named `<input>` that have a `name` attribute with any value|
|`soup.select('input[type="button"]')`|All elements named `<input>` that have an attribute named `type` with value `button`|