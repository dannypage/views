---
layout:	post
title:	"How To Evaluate Prediction Models By Comparing to Betting Markets"
date:	2016-11-07
---

  #### A.K.A Put your money where your mouth is!

As we get closer to the U.S. Presidential election, there has been a large divergence between popular prediction models. Nate Silver’s FiveThirtyEight, arguably the most famous prediction model, has upset the conventional wisdom of a very likely Hillary Clinton victory. His three models have converged around 65%. Meanwhile, the [New York Time’s Upshot](http://www.nytimes.com/interactive/2016/upshot/presidential-polls-forecast.html), [David Rothschild’s PredictWise](http://predictwise.com/), and [Princeton Election Consortium ](http://election.princeton.edu/electoral-college-map/)have her chances of winning at 84%, 88%, and a very confident >99%, respectively.

![](/views/assets/img/1*mqT8BTN36NKKeyxsnIMosg.png)From NYT. As of 2016/11/06–8:00 PM ESTThere are many reasons why the models diverge so much. Each model weighs polls differently, uses economic indicators, correlates state polls with neighboring states, or uses current betting numbers. But we only get to run the election one time. (Thank goodness!) But how are we to tell the difference between them? After the election, we’ll be able to check all the different states against the given predictions, increasing the number of trials. There’s also Senate races too. But in the meantime, let’s put some money down and compare the models against betting markets. The idea was inspired by [this blog post by Rothschild](http://predictwise.com/blog/2016/10/comparing-forecasts/), but instead of comparing models directly against each other, I’ll be pretending as though the models are placing bets on one of the largest public betting markets in the world. Think of this as **a way of measuring prediction models against the conventional wisdom of the day** and finding out if they can highlight something that the wisdom of the crowds could not.

#### Betting Procedures

For the purposes of this article, I’m going to be using Betfair’s data, helpfully captured often in PredictWise’s data. I’ve gotten daily updates from FiveThirtyEight, PredictWise, and Upshot. Each time each model updates, it will look at the price on the Betfair Exchange**. If the model likes Trump more than Betfair, it’ll make a bet. Likewise for Clinton. Because Betfair doesn’t allow you “cash in,” it won’t be like trading shares of a stock, but instead placing many bets. If you were ahead of the market, you could win either way, but most likely the models will be hoping for a Trump or a Clinton victory.

I experimented with a couple of different ideas on how much to bet, including $100 per bet, regardless if the model liked the candidate by 0.1% or 25%. I also wanted to use the [Kelly criterion](https://en.wikipedia.org/wiki/Kelly_criterion) to take advantage of that difference in probabilities, but didn’t want the model to bet everything on Day 1 (in this case, July 8th, 2016) if it was extremely confident. So my preferred method is adding $100 to the model’s bank each day, and betting “Half-Kelly,” or half of the advised bet.* For example: If a model put Clinton’s chances at 60%, and the market offered odds at 50%, a “Full-Kelly” bet would be for 20% of the bankroll of $100. This can lead to wild variance, so many investors will halve the bet from $20 to $10.

#### The Results

Now that we’ve gotten the procedures out of the way, who won? Well, this is preliminary, and makes some assumptions that might not work for the people behind the models on how to bet. So this is not the end-all-be-all of the analyzing these 3 models, but a start on how to analyze a model over a period of time that hangs on one event. Therefore, take it all with a grain of salt.

#### **Okay, Seriously Though, Give Me The Results**

Impatient, eh? Alright, here you go.

![](/views/assets/img/1*lrRAvVQrv4Mt969OSkYvag.png)<https://docs.google.com/spreadsheets/d/1nmq37NCqq6XiYistGcAsnfLxwL9y01lP6LUbAf6tVIg/edit?usp=sharing>Expected Return on Investment is measured against the current betting odds (Clinton 83% — Trump 17%). This will change as we get closer and results start following in, but I thought it might be illustrative of how models have done against the “Closing Line”.

By this measure, both NYT Upshot and Predictwise have done well. They have been consistently bullish on Hillary Clinton and it looks to pay off. It would cost a lot, but they could successfully hedge and call it a day, especially in the case of a Trump upset. If Trump were to win, NYT would lose 99.96% of their bankroll, while Predictwise would lose 84.70%. That being said, if they hold out, they will be handsomely rewarded for being right on Clinton before the betting markets caught up.

If I were to pick just one of them, **I think PredictWise has done the best in this market.** It updated the most out of all the models, and thus had more potential money on the line. It also wouldn’t go dead broke if Trump were to win either, which means it would live to see another day, while NYT would only have $4.30 to their name. Great job to David Rothschild.

![](/views/assets/img/1*RQ38FhJeN-TltGQNzmWtdw.png)Predictwise and NYT may be similarly profitable come Tuesday, but Predictwise had more on the line.Some notes about FiveThirtyEight models, which are all currently behind the market:

* It’s no wonder that FiveThirtyEight’s readers, a majority who lean towards Clinton, have been very concerned by its numbers. FiveThirtyEight would triple its money with the Polls-Plus model… if Trump wins.
* Nate Silver is wrong about being [aligned with or beating the betting markets](https://twitter.com/search?q=from%3Anatesilver538%20betting&src=typd). Not a single one of his models in any format that I tested have a positive Expected ROI. Only one of them had a positive outcome for Clinton, while many are very heavily betting on Trump. And no matter what happens on Tuesday, FiveThirtyEight’s NowCast will lose money.
* In betting tout-like fashion, Nate Silver willing to bring up markets [the moment it syncs](https://twitter.com/DavMicRot/status/792009213035720704). But that does not hold up over the long haul. The betting markets stayed steady during the conventions and debates, but the models varied wildly during these times.
![](/views/assets/img/1*uR_qxrQfx8wpsDuLoS8Kcw.png)#### Conclusion

Beating the markets is a tricky thing. I’m very sure the smart developers behind the models spent many hours tinkering and working with old data to come up with models that could try to predict one of the most absurd elections on record, and only a few of them will be profitable on Tuesday. If Clinton loses, a lot of confident models that I didn’t analyze would be broke, and FiveThirtyEight will be vindicated in their Trump-favoring model.

No matter the result, I hope that my work can give you a better idea about what to look for in a successful model over a time-series of projections. Prediction models are going to be more prevalent, and we need to be able to judge them as to know which models are best. It could be predicting temperature rises over the next 10 years for climate change, or projecting the opening weekend success of the next big movie; hopefully this article sparks a way to do so.

Thank you very much for reading, and please let me know if you have any comments or questions. You can reach me [on Twitter](http://twitter.com/dannypage), and please share if helped you understand prediction models a little more! All of my code is free and open here: <https://github.com/dannypage/2016-election-analysis> — Please let me know if you do anything with it or have programming questions!

#### Footnotes

* More about the Betfair Exchange: <https://medium.com/@jdh/betfair-and-the-2016-presidential-election-6833849e4549#.h3akp798o>

** Half-Kelly bet explained: <http://thehackensack.blogspot.com/2009/11/half-kelly-bet.html>

#### Further Charts

Didn’t know where to stick these, but wanted to give some context into how often the models picked a side, and the results of those picks.

![](/views/assets/img/1*segV2rjAxLCZSmPgLgcD3Q.png)![](/views/assets/img/1*SWr05hnNb0zw8FaxgOXZqg.png)  