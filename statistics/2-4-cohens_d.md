[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> In this data set, first babies are lighter than other babies by .12 pounds. Cohen's d, which measures the effect size, is -0.089 meaning the difference in means is .089 standard deviations. While larger than the difference in pregnancy lengths, this difference is still small.

```
preg = nsfg.ReadFemPreg() #read data into dataframe
live = preg[preg.outcome == 1] #separate out only live births
firsts = live[live.birthord == 1] #separate first births from others
others = live[live.birthord != 1]

print((firsts.totalwgt_lb.mean(),others.totalwgt_lb.mean())) #first birth avg weight, other birth avg weight
firsts.totalwgt_lb.mean()-others.totalwgt_lb.mean() #difference between first and other weight

#compute Cohen's d
diff = firsts.totalwgt_lb.mean()-others.totalwgt_lb.mean()

var1 = firsts.totalwgt_lb.var()
var2 = others.totalwgt_lb.var()
n1,n2 = len(firsts.totalwgt_lb),len(others.totalwgt_lb)

pooled_var = (n1*var1 + n2*var2)/(n1+n2)

d = diff/np.sqrt(pooled_var)
