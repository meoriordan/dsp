[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (scoring)

>> With a sample size of n=10, the standard error is 0.768 and the 90% confidence interval is (1.236, 3.619). As the sample size gets bigger, the standard error and confidence interval get smaller.

![cdf](https://github.com/meoriordan/dsp/blob/master/statistics/images/8.2.png)

```
lam = 2
    means = []
    for _ in range(1000):
        xs = np.random.exponential(1.0/lam, 1000)
        L = 1 / np.mean(xs)
        means.append(L)

    print('rmse L', RMSE(means, lam))
    
    cdf = thinkstats2.Cdf(means)
    conf_interval_lower = cdf.Percentile(5)
    conf_interval_upper = cdf.Percentile(95)
    
    print(conf_interval_lower, conf_interval_upper)
    
    thinkplot.Cdf(cdf)
    thinkplot.Config(xlabel='estimate',
                     ylabel='CDF',
                     title='Sampling distribution')
 ```
