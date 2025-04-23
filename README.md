# Python
Web Crawler_udn news

import requests
from bs4 import BeautifulSoup as soup

url = "https://udn.com/news/breaknews/1/"
page = requests.get(url).text
web = soup(page, "html.parser")

items = web.find_all("div", class_="story-list__news")

#y.find_all("h2")[0].find_all("a")[0].string

for y in items[:5]:
    title = y.find_all("h2")[0].find_all("a")[0].string
    eye = y.find_all("span")[0].text
    date = y.find_all("time")[0].text
    print("發布日期:" + " " + date)
    print("瀏覽次數:" + " " + eye)
    print("文章標題:" + " " + title)
    print("-" * 30)  
