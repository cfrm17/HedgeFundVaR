# Hedge Fund VaR

A model is presented to determine the value at risk (VaR) due to hedge fund volatility during closeout of hedge fund positions, as well as pricing calculations for options written on a basket of funds.

It contains the implemented VaR calculations for callable options written on a basket of hedge funds, with minor changes and the methodology for calculating the VaR of the LTV (loan to value) ratio for loans to funds-of-funds.

The portfolio diversification and leverage limits were found to be consistent with increasing conservatism as the number of funds in a basket decreases. It should be noted that these limits cannot be considered as ‘stand alone’ since the characteristics of hedge funds change with strategy and management style–this table must be used in conjunction with other risk-management tools.

As a first step, we have available the monthly fund returns and want to determine the basket returns (before fees). The second form of which comes from inserting (1) into the first. This allows one to bootstrap to find the basket return, given the previous weightings and the individual fund returns. If we also need to determine how the weightings change, we use a formula to find. 

However, we are interested in determining the volatility of the basket with today’s weightings, not the historical volatility of the basket. These two quantities are typically different as the composition of the basket changes slightly with time, and the funds that dominant the basket volatility one month may have vanishingly small weight the next.

To determine the volatility of today’s basket, we merely replace the historical weightings with today’s and generate a collection of historical returns on today’s basket (this is not really a time-series). The returns (6) are then used to estimate the volatility of the basket: σ_B.

Assuming a sudden drop in the basket value–causing immediate trigger–we want to estimate how much the basket could lose in value at the 99th percentile of its returns distribution. This is complicated by the fact that there is a delay associated with the redemption of each fund. As per standing order S09.01.05, the VaR (and capital) is initially calculated as follows.

The distribution of basket value returns is assumed to be normally-distributed with width _B as calculated above. We want to determine the basket value that corresponds to a drop in value to the 99th percentile of this distribution. That is, the value of the basket when it has moved down in value ~ 2.33 standard deviations, which would be over MR months, which is an average over the fund redemption delays:
 

References:

https://finpricing.com/knowledge.html
