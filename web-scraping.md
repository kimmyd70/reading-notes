## Web Scraping
notes on [this article](https://towardsdatascience.com/how-to-web-scrape-with-python-in-4-minutes-bc49186a8460)

and [this article](https://en.wikipedia.org/wiki/Web_scraping)

[video](https://www.youtube.com/watch?v=Bg9r_yLk7VY)

[Python library Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/)

Web scraping is a technique to automatically access and extract large amounts of information from a website to gather data. 

Also called web harvesting or web data extraction. 

The wiki article lists several techniques as well as cautions about legality.

The notes below are the process from the main article.

Important notes about web scraping:
1. Read through the website’s Terms and Conditions to understand how you can legally use the data. Most sites prohibit you from using the data for commercial purposes.

2. Make sure you are not downloading data at too rapid a rate because this may break the website. You may potentially be blocked from the site as well.

### How to:
1. inspect the data via browser console.  Most txt files will be within an `<a>` tag

2. import requests
```
import urllib.request
import time
from bs4 import BeautifulSoup
```
3. we set the url to the website and access the site with our requests library

`url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url)`

you should see the following output if successful:
` <Response [200]>`

4. parse the html with BeautifulSoup
` soup = BeautifulSoup(response.text, "html.parser")`
using findAll to locate all the tags `soup.findAll('a')`

5. extract the link
```
one_a_tag = soup.findAll(‘a’)[38]
link = one_a_tag[‘href’]
```
6. click on the first data file to get the full path and use `urllib.request` library to download the files with 2 params for file url and filename:
```
download_url = 'http://web.mta.info/developers/'+ link
urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:])
```
7. Pause the code to avoid spamming the website and getting blocked:
`time.sleep(1)`

8. After successful single download, write a loop to download all. See the article for code or the [author's Jupyter nb](https://github.com/julia-git/webscraping_ny_mta)

