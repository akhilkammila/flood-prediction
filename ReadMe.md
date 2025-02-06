Day 1:
- short day (30 min)
- eda.ipynb notebook
- graphed each column's distribution
- graphing pointplot of each columns values Vs. flood prediction prob.

Day 2:
- tried doing multi LR
- messed up for a while, thinking that train R^2 was near-perfect, but cross-val was 0.84 (both were 0.84)
- found that multi LR is equivalent to single LR on the mean of all X-values
- tried doing k-means, pca, t-sne, to make use of things other than just the mean of Xs (did not find patterns)

What should I investigate?
1. values of 7 vs. 8 in the pointplot of col values Vs. flood prediction prob. are too similar
- they don't follow the upwards trend, investigate

2. Surely the values in the columns of X matter, not just the mean
- extreme vals investigation (but this is a large minority, might not be relevant)

3. Look for interactions
- what if we just spam interaction terms --> ridge/lasso regression
- spam lgbm --> see if it is doing any smart shit or just using the mean

4. Investigate where the distribution of X-vars is different for the high means and low means
- why are the low means even lower than their avg.
- why are the high means even higher than their avg.