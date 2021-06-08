# Web Scraping with Python

## Requests & Beautiful Soup Libraries Installations

```bash
# Installing Requests 
pip install requests

# Installing Beautiful Soup
pip install bs4
```

## Importing Libraries in Code

To soupify means to parse the content of a site so we can use it.
```python
# we need the requests library
import requests

# we import the BeaufifulSoup class from bs4
from bs4 import BeautifulSoup
```

## Using Requests

Some Requests Methods & Attributes
- `.get()`
- `.post()`
- `.status_code`
- `.headers`
- `.content` : Returns content of response, in bytes.
- `.json`

```python
# the "get" function takes a url
result = requests.get("https://www.google.com/")

# check that 'result' got the content
# 200 = content present (good) // 404 = content not present
print(result.status_code)

# we can check the headers to verify we have the correct page
print(result.headers)

# see payload in bytes
src = result.content
```

## Create a Soup object (to extract info)

```python
soup = BeautifulSoup(src)
```

## Beautiful Soup Methods & Attributes

```python
# find all the < a > tags
# find all returns a LIST
links = soup.find_all("a")

# find the first element only
urls = []
for h2_tag in soup.find_all("h2"):
    a_tag = h2_tag.find('a')
    urls.append(a_tag.attrs["href"])

# print only links that have the string 'About' in them
for link in links:
    if "About" in link.text:
        print(link)
        print(link.attrs['href'])
```

## Beautiful Soup Objects

```python
# To keep things simple and also reproducible, consider the following HTML code
html_doc = """
<html><head><title>The Dormouse's story</title></head>
<body>
<p class="title"><b>The Dormouse's story</b></p>
<p class="story">Once upon a time there were three little sisters; their names:
<a href="http://example.com/elsie" class="sister" id="link1">Elsie</a>,
<a href="http://example.com/lacie" class="sister" id="link2">Lacie</a> and
<a href="http://example.com/tillie" class="sister" id="link3">Tillie</a>;
and they lived at the bottom of a well.</p>
<p class="story">...</p>
<b class="boldest">Extremely bold</b>
<blockquote class="boldest">Extremely bold</blockquote>
<b id="1">Test 1</b>
<b another-attribute="1" id="verybold">Test 2</b>
"""

soup = BeautifulSoup(html_doc, "lxml")

# Print out nicely formatted HTML
print(soup.prettify())

```

## Beautiful Soup Tags

```python
# print first occurence of bold tag [ 2 ways ]
print(soup.b)
print(soup.find('b'))

# print first occurence of paragraph tag [ 2 ways ]
print(soup.p)
print(soup.find('p'))

# find all occurences of a tag
print(soup.find_all('b'))

# give the name of the tag
pring(soup.b.name)
```