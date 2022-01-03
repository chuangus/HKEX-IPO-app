# HKEX-IPO-app

[![scraper-ipo-updater](https://github.com/epiphronquant/HKEX-IPO-app/actions/workflows/main.yml/badge.svg)](https://github.com/epiphronquant/HKEX-IPO-app/actions/workflows/main.yml)

### Press link to use APP https://share.streamlit.io/epiphronquant/hkex-ipo-app/main/HKEX_IPO_app.py

This app visualizes HKEX IPO data from 2018 onwards for healthcare stocks and 2019 onwards for all stocks. It gets updated automatically every Sunday noon Hong Kong time.

**Data Sources**

1. _AA Stocks_: http://www.aastocks.com/en/stocks/market/ipo/mainpage.aspx set of pages from January 1st, 2019 onwards. 
2. _HKEX_: From January 1st, 2018 to December 31st, 2018, healthcare IPOs was added in manually.
3. _Investing.com_: Hang Seng Healthcare Data

The charts visually reflect research by Professor Jay Ritter on the American exchanges https://site.warrington.ufl.edu/ritter/ipo-data/internal and corresponding research conducted by Epiphron Capital on the HKEX. These charts show 
1. The right tail distribution of IPO returns which reflects IPO underpricing.
2. Larger lead underwriters underprice more (Goldman Sachs, Morgan Stanley, Merril Lynch etc.)
      a. Primary western lead underwriters working with a secondary Chinese Lead underwriter would more consistently underprice an offering
3. IPO underpricing correlates with market performance. When market sentiment is strong, underpricing is stronger and vice versa.
4. The drop in lockout expiration return from the 100th trading day to 120th trading day post IPO. 

Change on debut is the 1st day close price / offer price -1. We use simple returns which is (Value t=1) / (Value t=0) -1. 

*We manually adjust IPOs as ones that aren't secondary listings, add on listings or spinoffs. The automatic update function assumes that it is an IPO if the name doesn't end in -S. There are no SPACs yet on the Hong Kong Stock Exchange and we wouldn't count them as IPOs.
