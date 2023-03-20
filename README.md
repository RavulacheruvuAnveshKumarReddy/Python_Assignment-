# Python_Assignment-
http://tpcg.io/_J9ACC3
hton

import pandas as pd
import scrapy as scrapy
url = "https://www.amazon.in/s?k=bags&crid=2M096C61O4MLT&qid=1653308124&sprefix=ba%2Caps%2CD283&ref=sr_pg_1"

spider = scrapy.Spider(url)

def parse(self, response):

items = response.css("div.product-listing > h2 > a").extract()

for item in items:

url = item.get("href")

name = item.get("title")

price = item.get("price")

rating = item.get("star-rating")

reviews = item.get("reviews")

asin = item.get("asin")

description = item.get("description")

manufacturer = item.get("manufacturer")

print("%s\t%s\t%s\t%s\t%s\t%s\t%s
" % (

item.get("product_url"),

item.get("name"),

item.get("price"),

item.get("rating"),

item.get("reviews"),

asin,

description,

manufacturer))
