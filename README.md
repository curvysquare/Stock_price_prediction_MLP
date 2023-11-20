# Investment Strategy 

The investment strategy implemented here is based on long term price reversal. This pricing anomaly was first suggested by Thaler (1985) and observes that for the bottom 35 stocks, ranked by cumulative abnormal return (CAR), over the course of 3 years there is an increase in CAR for this loser portfolio Similarly, the winner portfolio experiences a declining CAR across the same three year holding period.

This suggests a possible long term investment strategy to which a the start of the three year holding period, the stocks predicted to be losers should be subject to a long position to capitalize on the expected increase in CAR over the holding period. In contrast, stocks identified to be winners should be shorted over the 3 years to benefit from the expected decline in returns.

There is therefore a potential relationship between a stocks ranking, determined by its previous 3 year CAR (Thaler, 1985) and the returns it experiences over the next 3 years. Bearing this in mind, it is possible to teach a machine learning model this long term price reversal relationship. It is important to note this forms a long term investment strategy, and one which is different to a momentum-based strategy: typically a long position is entered on the winner portfolio for approximately 12 months, as opposed to the short position for 36 months found here.

With the reversal stratergy, each position has a holding period. Our stratergy says that the current loosers should become the winners in the next period. Therefore if the predicted target label is between 5 and 10, we begin the holding period with a long postiion. Natrually the oppposite occurs, if the predicted target label is between 0, 5 we begin the holding period with a short position.


# MLP design 


The MLP will take the form of a classifier as opposed to a regression model. The assigned class label is derived from a ranking of cumulative returns and is associated with the class given for the ranking of the same stock at the end of the period.

The nature of this problem means the specific MLP classification model implemented is regarded as a multiclass problem since the classes given to the ranked stocks are mutually exclusive, in contrast to a multilabel problem.

Whilst deep learning internalizes the feature extraction process, it is alternatively done here through intuition and knowledge of financial price activity. As such, the input features of cumulative return and momentum factors are chosen as we estimate that they will contain some informational content regarding the long term reversal process. Additionally, different forms of these features with varying lengths are also included to capture price action patterns across multiple time spans.

Hyperparameters are tunned using a cross validation Grid search approach

## Features:
- Momentum
- 6-month momentum
- 1year momentum
- 3 year momentum
- 5 year momentum





