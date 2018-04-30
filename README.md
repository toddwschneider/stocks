# Stocks!

A free, lightweight, blazing-fast static page to get stock quotes using the [IEX API](https://iextrading.com/developer/). Stocks can be grouped into user-defined portfolios. Quotes update every 10 seconds. No API key required. Everything is contained within index.html, there are no external javascripts or stylesheets to load.

See here for a live demo: http://toddwschneider.com/stocks/

## Motivation

I used to use Google Finance portfolios as a simple way to watch a few baskets of stocks organized along some dimension, typically by sector (banks, tech, etc). Then Google Finance [killed the portfolios feature](https://productforums.google.com/forum/#!category-topic/websearch/uf8q-AaPiyQ), and the new version had no option to view stock quotes organized under subheaders with good information density. I tried [some alternatives](https://www.marketbeat.com/press-room/google-finance-changes-and-alternatives/), but many of them felt too bloated, so I built my own.

## Screenshot

[![sample stocks](https://user-images.githubusercontent.com/70271/39388917-b15dde6e-4a51-11e8-8a30-72c8bd42f50a.png)](http://toddwschneider.com/stocks/)

## Customize

Edit the `PORTFOLIOS` variable within `index.html`. For example, if you wanted to see the collection of bank stocks and tech stocks from the above screenshot, you could do this:

```js
const PORTFOLIOS = [
  {'name': 'Banks', 'symbols': ['GS', 'MS', 'JPM']},
  {'name': 'Tech', 'symbols': ['AAPL', 'GOOGL', 'MSFT', 'AMZN']}
];
```

## Host your own

If you fork this repo on GitHub and edit index.html to reflect the stocks you want to watch, then you can use a [GitHub Pages Project Page](https://help.github.com/articles/user-organization-and-project-pages/) to publish your own version to the web.

You could also save index.html to your local disk and open it in your browser, or upload it to a cloud storage service like S3, GCS, or Azure Storage.

## IEX API

You do not need to sign up for anything or get an API key to use the [IEX API](https://iextrading.com/developer/docs/), but usage is subject to their [terms of service](https://iextrading.com/api-terms/).

## Why aren't the market indices available? (S&P 500, DJIA, NASDAQ)

The IEX API only provides free data for stocks, not indices, so the closest thing is to use ETFs that track the major indices. See here for context: https://github.com/iexg/IEX-API/issues/36. Suggested index ETFs:

- S&P 500: `SPY`
- Dow Jones: `DIA`
- NASDAQ: `QQQ`
- Russell 2000: `IWM`

## Browser compatibility

The page uses the [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API), which means it does not work with Internet Explorer.
