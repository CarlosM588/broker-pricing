# Broker Quote Tool: Pricing a Lane From 8,292 Real Rate Records

**Finding.** Across 124 U.S. refrigerated freight lanes from 2000 to 2026, the median all-in carrier rate is $2.40 per mile, but the middle half of historical rates on a typical lane runs from $2.06 to $2.75. That 69-cent band is the negotiation room. A broker quoting without lane-level data is guessing inside a spread worth hundreds of dollars per load, and lane extremes in the data run from $1.19 to $8.90 per mile.

**Live tool.** [carlosm588.github.io/broker-pricing](https://carlosm588.github.io/broker-pricing/)

## The question

What should a freight broker pay a carrier on a given lane today, and what should they quote the shipper so the margin survives?

## The data

8,292 lane-rate records across 124 lanes, 2000 to 2026, from the USDA Agricultural Marketing Service refrigerated-produce truck rate series, plus the EIA national diesel price for the fuel default. Rates are medians by lane and are all-in, fuel included.

## The method

Rates are aggregated to a benchmark median, a 25th to 75th percentile range, and a market gauge per lane. The gauge compares the latest year's median to the long-run median so you know whether the lane is hot, soft, or normal, and therefore which end of the range to quote. Quote math on top of the benchmark.

- Carrier cost = benchmark rate per mile x miles (fuel already inside the all-in rate)
- Diesel portion = (diesel price / 6 mpg) x miles, broken out so fuel's bite is visible
- Shipper quote = carrier cost / (1 - margin)

## What it changes

The quote conversation starts from the lane's own history instead of a gut number. You see the benchmark, the realistic range, how much of the cost is diesel, and where the market sits right now, before you name a price.

## Run it

Open `index.html` in any browser. That is the whole app. Plain HTML, CSS, and vanilla JavaScript with the rate data embedded, so there is nothing to install. `broker_quote_tool.html` is the same tool under its original filename.

## Note

A prototype and a negotiation aid, not a binding price. The rates come from USDA produce data, so they are a strong benchmark for refrigerated produce lanes and a directional guide for other freight.

Built by Carlos Martinez Jr. More at [carlosmartinezai.com](https://carlosmartinezai.com).
