[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

Both the PMF and the CDF indicate that the distribution of these random numbers is uniform. Each number has a probability of 1/1000 (0.001). The CDF is a straight line which also indicates a uniform distribution.

![random_num_pmf](https://github.com/meoriordan/dsp/blob/master/statistics/images/random_num_pmf.png)

![random_num_cdf](https://github.com/meoriordan/dsp/blob/master/statistics/images/random_num_cdf.png)
```
rand_num = np.random.random(1000) #generate 1000 random numbers
rand_pmf = thinkstats2.Pmf(rand_num, label='random_numbers') #create PMF
thinkplot.Pmf(rand_pmf, linewidth=0.1) # plot PMF

rand_cdf = thinkstats2.Cdf(rand_num) #create CDF
thinkplot.Cdf(rand_cdf) #plot CDF

```
