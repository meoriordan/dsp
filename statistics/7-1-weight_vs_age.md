[Think Stats Chapter 7 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2008.html#toc70) (weight vs. age)

>> The correlation between mother's age and birth weight is not very strong. Pearson's correlation is 0.069 and Spearman's correlation is slightly higher at 0.095. This could be due to a non-linear relationship or the presence of outliers as Spearman's correlation is more robust in those cases.

The percentile graph shows a non-linear relationship between the variables.The birth weight increases for ages 15-25, stays relatively level up until 37 and then starts decreasing.

![corr_graph](https://github.com/meoriordan/dsp/blob/master/statistics/images/7.1_corr.png)
![corr_perc](https://github.com/meoriordan/dsp/blob/master/statistics/images/7.1_corr_perc.png)
```
#import data & create data frames
import first
live, firsts, others = first.MakeFrames()
live = live.dropna(subset=['agepreg', 'totalwgt_lb'])

#create scatter plot
birth_wgt = live.totalwgt_lb
mother_age = live.agepreg
thinkplot.Scatter(mother_age, birth_wgt, alpha=0.08)
thinkplot.Config(xlabel='mother_age (yr)',
                 ylabel='birth_wgt (lb)',
                 axis=[10, 45, 0, 15],
                 legend=False)
                 
#bin age data 
bins = np.arange(10,50, 5)
indices = np.digitize(live.agepreg, bins)
groups = live.groupby(indices)
mean_age = [group.agepreg.mean() for i, group in groups]
cdfs = [thinkstats2.Cdf(group.totalwgt_lb) for i, group in groups]

#plot weight percentiles against binned age data
for percent in [75, 50, 25]:
    weight_percentiles = [cdf.Percentile(percent) for cdf in cdfs]
    label = '%dth' % percent
    thinkplot.Plot(mean_age, weight_percentiles, label=label)
    
thinkplot.Config(xlabel='Mother Age (yr)',
                 ylabel='Weight (kg)',
                 axis=[10, 45, 6, 8.5],
                 legend=False)
