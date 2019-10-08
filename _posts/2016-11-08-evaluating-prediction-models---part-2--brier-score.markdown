---
layout:	post
title:	"Evaluating Prediction Models — Part 2: Brier Score"
date:	2016-11-08
---

  A follow-up from yesterday’s post about using [betting markets to evaluate prediction models](https://medium.com/@dannypage/how-to-evaluate-prediction-models-comparing-to-betting-markets-39161f2686a3#.ilil72x7e); today’s post will be using the [Brier Score](https://en.wikipedia.org/wiki/Brier_score) calculation on a state-by-state basis. It’s used very often in [weather forecasting ](http://www.eumetcal.org/resources/ukmeteocal/verification/www/english/msg/ver_prob_forec/uos2/uos2_ko1.htm)to see measure how often it predicts rain and scores it based on confidence. A perfect score is zero, a perfect fail is one.

If the model thinks a state goes red 99% of the time and it actually goes blue, that result in a poor score of 0.98. Some models very confident on a lot of states, so if there’s a miss, it’ll hurt. On the flip side, D.C. will very, very likely go for Clinton. Calling it with a 100% certainty rewards the model with a 0.0. It’s like golf, you want to have the lowest possible score!

I’ll do this for every state and every model. I’ll also be using a weighted Brier score, which rewards calling a large state like Florida correctly with confidence (up to 29 points!), while that correct DC call is worth only up to 3 points. This, of course, wants to have the highest score. The max possible score will be 538, meaning the model called every state correctly with extreme confidence. (The 2012 Map might do well here if the 2016 Map doesn’t change much.)

Lastly, I’ll be using the models in aggregate to create a timeline of Optimistic, Pessimistic, and Mean expected electoral votes. As of right now:

* Optimistic Clinton prediction is 341.17–196.83
* Mean: **313.81–224.19**
* Minimum: 280.68–257.32
As states are called, the bounds of the prediction will narrow toward the eventual number. An example of what that graph will look like:

![](/img/1*Dx87sLSYRj-s4vPnf4lVqw.jpeg)Just an example, but wouldn’t it be nice if it was over that quickly?The models included are:

* [FiveThirtyEight, Polls-Only](http://projects.fivethirtyeight.com/2016-election-forecast/?ex_cid=rrpromo)
* [New York Times, Upshot](http://www.nytimes.com/interactive/2016/upshot/presidential-polls-forecast.html)
* [Huffington Post](http://elections.huffingtonpost.com/2016/forecast/president)
* [PredictWise](http://predictwise.com/)
* [Princeton Election Consortium](http://election.princeton.edu/2012/09/29/the-short-term-presidential-predictor/)
* [PollSavvy — A high school student and his teacher](https://twitter.com/PollSavvy)
* [Daily Kos](http://elections.dailykos.com/app/elections/2016)
* [G. Elliott Morris](https://twitter.com/gelliottmorris/status/795804115939061762)
* [Pierre-Antoine Kremp](http://www.slate.com/features/pkremp_forecast/report.html), hosted by Slate
#### Wrap Up

You can see [all the data here](https://docs.google.com/spreadsheets/d/1WZdg3fcvK_J-XRtN8WpEb9nRB9nF-gi6DRDYINku_PU/edit?usp=sharing). The graph will update in the Google Spreadsheet, and also on [my personal website](http://dannypage.github.io/election). I’ll also include updates on my Twitter account: [@dannypage ](http://twitter.com/dannypage)— Hope you’ll follow along!

  