# Task 07 – Standard Deviation

## Problem Statement

Eleven students received the following test scores:

$$
88,\ 92,\ 79,\ 85,\ 95,\ 81,\ 86,\ 90,\ 83,\ 77,\ 89
$$

Find the mean and standard deviation.

Then remove the highest and lowest scores and calculate the new mean and standard deviation.

## Theory

The mean of $N$ measurements is

$$
\bar{x} = \frac{1}{N}\sum_{i=1}^{N}x_i
$$

The sample standard deviation is

$$
\sigma = \sqrt{\frac{1}{N-1}\sum_{i=1}^{N}(x_i-\bar{x})^2}
$$

The standard deviation measures the spread of the scores around the mean.

## Step-by-Step Solution

### Original Data Set

The scores are

$$
88,\ 92,\ 79,\ 85,\ 95,\ 81,\ 86,\ 90,\ 83,\ 77,\ 89
$$

The number of scores is

$$
N = 11
$$

The sum of the scores is

$$
\sum x_i = 945
$$

The mean is

$$
\bar{x} = \frac{945}{11}
$$

$$
\bar{x} = 85.91
$$

Using the sample standard deviation formula,

$$
\sigma = \sqrt{\frac{1}{10}\sum_{i=1}^{11}(x_i-85.91)^2}
$$

The result is

$$
\sigma = 5.70
$$

### Removing the Highest and Lowest Scores

The highest score is

$$
95
$$

The lowest score is

$$
77
$$

The remaining scores are

$$
88,\ 92,\ 79,\ 85,\ 81,\ 86,\ 90,\ 83,\ 89
$$

The number of remaining scores is

$$
N = 9
$$

The new sum is

$$
945 - 95 - 77 = 773
$$

The new mean is

$$
\bar{x} = \frac{773}{9}
$$

$$
\bar{x} = 85.89
$$

The new standard deviation is

$$
\sigma = \sqrt{\frac{1}{8}\sum_{i=1}^{9}(x_i-85.89)^2}
$$

$$
\sigma = 4.14
$$

## Final Result

For the original data set:

$$
\bar{x} = 85.91
$$

$$
\sigma = 5.70
$$

After removing the highest and lowest scores:

$$
\bar{x} = 85.89
$$

$$
\sigma = 4.14
$$

## Interpretation

Removing the highest and lowest values barely changes the mean, because the removed scores are roughly balanced around the center of the data. However, the standard deviation decreases because the most extreme values are removed, making the remaining scores less spread out.
