[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

To calculate the percentage of the US male population that is within the range to join the Blue Man Group, I first converted the range to centimeters (1 in = 2.54 cm). Then I subtracted the lower bound (177.8 cm) CDF (assuming a normal distribution with mean=178cm and sd=7.7cm) from the upper bound (185.4). This gives the percentage of the population that falls within this range (34.2%). 

```
import scipy.stats
scipy.stats.norm.cdf(185.4,loc=178,scale=7.7)-scipy.stats.norm.cdf(177.8,loc=178,scale=7.7)
```
