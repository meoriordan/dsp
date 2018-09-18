[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> In the below graph, the difference between the actual and observed PMF is evident. If children are asked how many children are in their household, the pmf is biased because households with many children will be over-represented, and households with no children will not appear at all. This is also evident in the different means: 1.02 children per household (actual) vs 2.40 (biased).

![actual_vs_biased](https://github.com/meoriordan/dsp/blob/master/statistics/images/actual%20vs%20biased.png)
```
resp = nsfg.ReadFemResp() #load in data

pmf = thinkstats2.Pmf(resp.numkdhh, label="actual") #create PMF (unbiased)

thinkplot.Pmf(pmf)
thinkplot.Config(xlabel='# of children', ylabel='PMF') #plot PMF

#define Bias function used to create a biased pmf
def BiasPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf

biased_pmf = BiasPmf(pmf, label="observed")
thinkplot.PrePlot(2) #plot both pmfs on one graph
thinkplot.Pmfs([pmf, biased_pmf])
thinkplot.Show(xlabel="household size", ylabel="PMF")

#compute mean of each pmf
pmf.Mean()
biased_pmf.Mean()
```
