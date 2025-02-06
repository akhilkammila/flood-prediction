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

Day 3:
- Tried to continue KNN approach, found that it did not lead to improvment
- Baseline approach of using mean X --> floodProbability based on other points with same mean X
    - score 0.865 (better than 0.84x from before)

Looked at official solutions
- top score is 0.869

Findings missed
- original variables are poisson
    - could have done statistical test
- statistical descriptors are relevant
    - median, std
- we are effectively guessing noise (could have tried to model noise)
    - an approach that comes to mind is guess noise function based on floodProbability n(floodProbability)
    - then back out what the optimal guess is based on this function

    - check if it is reasonable that we get our current values from this noise distribution