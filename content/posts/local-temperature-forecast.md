---
date: '2025-01-09'
title: 'Local Temperature Forecast'
cover:
    image: "/blog/pics/Local-Temperature-Forecast.png"
---

A long time ago, I worked for the Australian Bureau of Meteorology.

While there, I created many internal scripts/apps using weather data, for fun and internal personal use.

One example was a tiny web app that plotted recent temperature observations, forecasts, and in-office temperature using a little USB temperature probe.

It was very cool and a few members of our team kept it terminally open.

Even today, I still leave the [temperature forecast page for my suburb](http://www.bom.gov.au/places/vic/vermont/) open all day long and refresh it before heading out to the gym, supermarket, whatever.

Anyway, with that in mind, I sat down with gpt4o and built out a tiny html + css + js page that grabs temperature observations and forecasts and presets then in a simple one pager.

You can see it here:

* [Temperature Forecast](https://jasonbrownlee.me/Temperature/)

No database needed, it hooks directly into the API.

Here's a screenshot:

![Local Temperature Forecast](/blog/pics/Local-Temperature-Forecast.png)

Initially, we used a GitHub action to download the json/XML products into the repo and then display + plot the relevant data.

We then found a [GitHub repo](https://github.com/tonyallan/weather-au) that summarizes the an unofficial API.

Reading and experimenting with the code lead to a much simpler and cleaner page.

We hosted it on GitHub pages. Here's the code:

* [Local Temperature Forecast (Australia only)](https://github.com/Jason2Brownlee/Temperature)

I shared it with a friend, realized he lives in a different suburb and gave him instructions on how to change the hard coded suburb details.

I then came back from my run and ask gpt4o to add in a suburb selector.

I'm very happy with the final result.

Like the forecast page before it, this one-page-app sits open all day long.

Another successful example of [chat-driven programming](/blog/posts/chat-driven-programming/).