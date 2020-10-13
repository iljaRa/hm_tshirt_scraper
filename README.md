# Web scraper for hm.com T-Shirts
A simple web scraper based on Python (requests, selenium, beautifulsoup4) to get images and information on the T-Shirts available on hm.com

First, please check the current hm.com/robots.txt to see whether hm.com allows to scrape the information. At the time of writing this text, hm.com/robots.txt returns:
```
User-agent: *
Disallow:
```
This means that nothing is disallowed, for all agents (scrapers).

Note that it is generally recommended to use the API of the store to scrape data. However, preferred to write my own scraper because it is more educative and fun, and gives me more options to explore.

You can run the scraper from inside the cloned `hm_tshirt_scraper` directory, using
```
python3 fashion_hm_selenium_lvl1.py
```

To add the scraped information to a MySQL database, first create a databes and set up the connection inside the `db_export.py` by replacing the input of `ms.connect(...)`:
```
db = ms.connect(
	host = "localhost",
	user = "root",
	passwd = " ",
	database = "hm_tshirts"
)
```
by the information that fits your own set up.

Afterwards, you can create the SQL entries using:
```
python3 fashion_hm_exp_to_db.py
```

The provided code focuses on scraping the T-Shirts for men but you can easily switch to the offer for women, or any other fashion item, by editing the `url_tshirts` variable in `fashion_hm_selenium_lvl1.py`.
