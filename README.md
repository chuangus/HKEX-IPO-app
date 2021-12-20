# HKEX-IPO-app

[![scraper-ipo-updater](https://github.com/epiphronquant/HKEX-IPO-app/actions/workflows/main.yml/badge.svg)](https://github.com/epiphronquant/HKEX-IPO-app/actions/workflows/main.yml)

### Press link to use APP https://share.streamlit.io/epiphronquant/hkex-ipo-app/main/HKEX_IPO_app.py

This app displays data generated from https://www.kaggle.com/quantepiphron/ipo-data-updater which scrapes raw data from http://www.aastocks.com/en/stocks/market/ipo/mainpage.aspx set of pages and then uses Yahoo Finance and Investing.com data for calculating returns post IPO. Yahoo Finance data tends to colloborate with AA stocks data when *actual IPOs are counted as IPOs. 

Investing.com data is used for the change on debut with index level chart while all other data comes from Kaggle. This also means that the data is only as updated as the manual Kaggle update. We tend to update this every month.

The charts visually reflect research by Professor Jay Ritter on the American exchanges https://site.warrington.ufl.edu/ritter/ipo-data/internal and corresponding research conducted by Epiphron Capital on the HKEX. These charts show 
1. The right tail distribution of IPO returns which reflects IPO underpricing.
2. Larger lead underwriters underprice more (Goldman Sachs, Morgan Stanley, Merril Lynch etc.)
      a. Primary western lead underwriters working with a secondary Chinese Lead underwriter would more consistently underprice an offering
3. IPO underpricing correlates with market performance. When market sentiment is strong, underpricing is stronger and vice versa.
4. The drop in lockout expiration return from the 100th trading day to 120th trading day post IPO. 

Change on debut is the 1st day close price / offer price -1. We use simple returns which is Value t=1 / Value t=0 -1. 

*We manually try to count IPOs as ones that aren't secondary listings, add on listings or spinoffs. There are no SPACs on the Hong Kong Stock Exchange.
