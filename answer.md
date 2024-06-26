Problem 1

Based on Table in above Scenario, estimate the expected win rate for a bid repsonse at a given price (prices are listed in table). State your assumptions clearly and provide the steps on how you arrived at your answer.

Answer 1

The table contains the number of won or lost events for each bidding price.
To calculate the win rate at a given price we should take the number of won bids and divide it by total number of events at that price (e.g. won + lost events).
After doing this we end up with a dictionary where key is a bidding price and value is win rate at that price. (For example for the bid price 2 the win rate is 0.7)

```
{
 0.01: 0.0,
 0.1: 0.3,
 0.2: 0.2,
 0.4: 0.3,
 0.5: 0.2,
 0.75: 0.3,
 1.0: 0.6,
 2.0: 0.7,
 5.0: 0.8,
 9.0: 1.0
}
 ```


Problem 2

We receive money from our advertisers if we deliver them a win. Lets say that our advertiser is willing to pay $0.50 per win. This then becomes the upper bound for the bid valuation that we can submit in response to the publisher. For example, if we submit a bid response of $0.40 and we win, then the advertiser pays us $0.50, we pay $0.40 to the publisher and we made a net revenue of $0.10 .

If our goal was to maximize net revenue, what is the most optimal bid valuation we should send in our response? Use your estimations from Problem1 and all other available information.

Answer 2

For any given bid we can desribe net revenue as the difference between what our advirtiser gives us (in this case $0.50) and what we bid.
We can choose what we bid, but for different bid prices we have different probability of winning.
So the estimated net revenue can be written like this:

($0.50 - bid_price) * probability_of_winning_at_bid_price

For probability_of_winning_at_bid_price we can take the value from the dictionary above. 
Then we can calculate the estimated net revenue for each bidding price in our dataset:

```
price   revenue
0.01    0.0
0.1     0.12
0.2     0.06
0.4     0.029
0.5     0.0
0.75    -0.075
1.0     -0.3
2.0     -1.049
5.0     -3.6
9.0     -8.5
```

From here we should just the maximum estimated net revenue which is 0.12 at the bid price of $0.10. So the answer is $0.10.