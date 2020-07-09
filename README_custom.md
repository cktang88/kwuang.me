https://kwuang.me

Will basically be a collection of cool stuff I find on the interwebs.

1. articles

- basically hackernews, but with full text search, not just on the URLS/titles, but on the _ENTIRE WEBPAGE_ of all those links. See [FTS](./FTS).

2. pictures collage (eg. masonry.js)
3. links to videos

^^^ above is static site, prob w/ React + Chakra UI + React Router v6

### FTS

- webpages for all links will be scraped w/ python, beautiful soup, run on GCP w/ celery task, stores scraped text only in DB
- webpages will be cached (daily refresh?) and stored in mongo/postgres for simplicity
  - later Redis? -> `hello overengineering :)`
- search based on mongodb Atlas full text search/postgres full text search/apache lucene/solr/algolia/
- returns the links that match the query
