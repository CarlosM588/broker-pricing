# Broker Quote Tool

A single-page tool that turns real freight lane-rate data into a carrier benchmark and a shipper quote with your margin already built in. Pick a lane, and it tells you what the market pays a carrier, how much of that is diesel, and what to quote the shipper.

No install, no account, no backend. It is one HTML file that runs in any browser.

## What it does

Enter an origin region, a destination market, the distance, the diesel price, and your margin. The tool returns:

- the benchmark carrier rate per mile for that lane
- the all-in carrier cost for the trip, with fuel included
- how much of that cost is diesel, as a dollar figure and a percentage
- the typical rate range for the lane, from the 25th to the 75th percentile
- your margin in dollars
- the shipper quote to negotiate from

A market gauge tells you whether rates are hot, soft, or normal right now compared to the long-run average, so you know which end of the range to quote.

## How the quote is built

- Carrier cost = benchmark rate per mile x miles. The rate is all-in, so fuel is already inside it.
- Diesel portion = (diesel price / 6 mpg) x miles, shown so you can see fuel's bite.
- Shipper quote = carrier cost / (1 - your margin).
- Market gauge compares the latest year's median rate to the long-run median across all years.

## Data

- 8,292 real lane-rate records across 124 lanes, covering 2000 to 2026
- Source: USDA Agricultural Marketing Service refrigerated-produce truck rates, plus the EIA national diesel price for the fuel default
- Rates are medians by lane and are all-in, with fuel included

## Run it

Open `index.html` in any browser. That is the whole app. `broker_quote_tool.html` is the same tool under its original filename.

## Note

This is a prototype and a negotiation aid, not a binding price. The lane rates come from USDA produce data, so they are a strong benchmark for refrigerated produce lanes and a directional guide for other freight.

## Tech

Plain HTML, CSS, and vanilla JavaScript. The rate data is embedded in the page, so there is nothing to install. Hosting the single file is all it takes to put it online.
