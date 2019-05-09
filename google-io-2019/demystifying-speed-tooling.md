# Demystifying Speed Tooling

https://events.google.com/io/schedule/events/8d071906-e971-487d-98b1-33b089a4d462

## Foundations

- they recommended PageSpeed Insights — it's just Lighthouse, right?
  - no, cause it runs remotely and shows comparisons to other sites
- Lighthouse 5.0 is out today; it can now give recommendations based on your stack
  (such as WordPress specific stuff)
  - seems like its internal codename is "dobetterweb" :D
- difficult to measure load, it's not a single metric, you have:
  first paint, first contentful paint, first input delay, time to interactive
- Now developing new metrics:
  layout stability, largest contentful paint

## "Professional Performance Techniques"

- First, you need organizational buy-in
- Nothing more painful than trying to speed up a fundamentally slow site
- Now search console will have a speed report, too
- Calibre, treo, speedcurve are tools for monitoring production
- Firebase Web Performance Monitoring will give you detailed real user monitoring
- You can use https://github.com/googlechrome/crux to keep data on your competitors' performance
- requestmap.webperf.tools, thirdpartyweb.today help track down the cost of 3rd party includes
- you can basically enable feature flags for your hostname here:
  https://developers.chrome.com/origintrials/#/trials/active
- They added a plugin system to Lighthouse
- Lighthouse CI is coming soon
