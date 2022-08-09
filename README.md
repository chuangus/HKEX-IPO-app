# HKEX-IPO-app

[![scraper-ipo-updater](https://github.com/epiphronquant/HKEX-IPO-app/actions/workflows/main.yml/badge.svg)](https://github.com/epiphronquant/HKEX-IPO-app/actions/workflows/main.yml)

Follow link to access the app

https://share.streamlit.io/epiphronquant/hkex-ipo-app/main/HKEX_IPO_app.py

This app visualizes HKEX IPO data from 2018 onwards for healthcare stocks and 2019 onwards for all stocks. It gets updated automatically every Sunday 8am, Hong Kong time.

**Key Assumptions**
1. Relistings, spinoff of listed company, secondary listing, issuance of additional shares of a listed company are NOT considered IPOs.*
2. Delisted stocks have no data beyond first day IPO return and is not reflected on returns. (survivorship bias)
3. When computing returns, we use close data rather than adjusted close. Thus the return does not reflect dividends but reflects stock splits/merge.
4. Returns gets updated every Sunday noon, Hong Kong time. This means they would use Friday's/last trading day's close data.
5. There will be no major changes in AA stock's page layout and URL for the auto updater to work.
6. Data Sources are accurate

**Data Sources**

1. _AA Stocks_: http://www.aastocks.com/en/stocks/market/ipo/mainpage.aspx set of pages from January 1st, 2019 onwards. We use their first day return, sponsor data, and listing price among other things. Columns A-E and I-Z.
2. _HKEX_: From January 1st, 2018 to December 31st, 2018, healthcare IPOs was added in manually using their prospectuses. Columns A-E and I-Z. 
3. _Investing.com_: Hang Seng Healthcare Index Data. Columns AR-AY.
4. _Yahoo Finance_: Industry, sector, trading day count, and price performance past the first day IPO. Columns F-H and AA - AQ.

**Description**

The charts visually reflect research by Professor Jay Ritter on the American exchanges https://site.warrington.ufl.edu/ritter/ipo-data/ and corresponding research conducted by Epiphron Capital on the HKEX. These charts show 
1. The right tail distribution of IPO returns which reflects IPO underpricing.
2. Larger lead underwriters underprice more (Goldman Sachs, Morgan Stanley, Merril Lynch etc.)
      a. Primary western lead underwriters working with a secondary Chinese Lead underwriter would more consistently underprice an offering
3. IPO underpricing correlates with market performance. When market sentiment is strong, underpricing is stronger and vice versa.
4. The drop in lockout expiration return from the 100th trading day to 120th trading day post IPO. 

Change on debut is the (1st day close price) / (offer price) -1. We use simple returns which is (Value t=1) / (Value t=0) -1. 

*The automatic update function assumes that it is an IPO if the name doesn't end in -S. Data needs to be updated manually to ensure than only IPOs are counted. There are no SPACs yet on the Hong Kong Stock Exchange and we wouldn't count them as IPOs.

**Visualization of ipo-data-updater process**
![image](https://user-images.githubusercontent.com/91112822/148018543-62c689b0-b559-40f1-907c-ab1bfeb05427.png)

**Chart by Chart Explanation**

**1. Normal Distribution Plot and Rugplot for First Day Return**

This displays a histogram of the mean/median first day return with a Kernel Density Estimation (KDE) drawn as a line on top. The KDE estimates the shape of the distribution. The bottom rugplot plots every datapoint that was used in the chart above. It can be viewed by hovering your mouse over each tick. 

**2-5. ____ Deal Count and ____ First Day Return**

This displays with the blue bar the deal counts per a sector/sponsor and the red bar the mean/median first return given conditions on the industry or sponsor.

Lead 1 refers to the first sponsor name on the IPO Prospectus. Lead 2 refers to the second sponsor name on the IPO Prospectus.

**6. Change on Debut/ Return Till Today with Index Level**

This displays the change on debut/return till today based on the IPO date in blue and the Hang Seng Healthcare/HSI level in red.

**7. Last _ _sector_ IPOs Return Post IPO**

This chart plots return measured by (day close price/IPO price -1) from the day of IPO. We assume a return of 0% on the day before IPO.

**8. Selected _sector_ IPOs Return Post IPO**

This is a customizable where you input the name of stocks that have IPO'd and it will generate a chart for you like 7. 

**9. Average Trading Day Return Post IPO by Benchmark**

This chart takes the average/median return of IPO stocks, HSI, and HSH returns of days post IPO of all stocks within the selected timeframe. 480 trading days is only used as a placeholder for the return to today. Day 0 is the day of IPO return. 

**10. Average Trading Day Return Post IPO by Industry**

This chart takes the average/median return of each industry and lots the return based on trading days post IPO. 0 Trading days indicates first day return and 480 trading days is again used as a placeholder for the return to today.
