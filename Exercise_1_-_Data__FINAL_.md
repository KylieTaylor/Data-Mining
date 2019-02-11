Exercise 1 - Data Mining
================
Kylie Taylor, David Fraire, & Larisa Barreto
1/28/2019

Data Visualization 1: Green Buildings
-------------------------------------

The investor is intersted in the return of investment on a new "certified-green building" in Austin, TX. There are inherently many questions that must be answered in order to make a decision on whether to develop or not. In this analysis, we will not be preforming any predictive models through the use of regression. What we will be doing is conducting an analysis based on visualzations of the data at hand.

The data is sourced from a dataset titled "Green Buildings" constructed by real-estate economists, observing 1,360 green-certified buildings throughout the United States. Building characteristics were only available for 685 green buildings. For comparison purposes, the 685 green buildings were clustered with 12 non-green buildings within a quarter-mile radius of the certified green building, using data sourced from the CoStar database. The merged datasets consist of a total of 7,894 observations spanning the entire United States (685 clusters of approximately 12 buildings).

In order to become a certified-green building, a commercial property must fit within specific environmental criteria and is certified by an outside engineer. Some of the criteria a green building must satisfy are energy efficiency, carbon footprint, site selection, and sustainable building materials. Green buildings can be awarded either LEED or EnergyStar certifications.

There are 21 variables in the dataset. A summary of these variables follows:

1.  *CS.PropertyID*: the building's unique identifier in the CoStar database.
2.  *cluster*: an identifier for the building cluster
3.  *size*: the total square footage of available rental space in the building.
4.  *empl.gr*: the year-on-year growth rate in employment in the building's geographic region.
5.  *Rent*: the rent charged to tenants in the building, in dollars per square foot per calendar year.
6.  *leasing.rate*: a measure of occupancy; the fraction of the building's available space currently under lease.
7.  *stories*: the height of the building in stories.
8.  *age*: the age of the building in years.
9.  *renovated*: whether the building has undergone substantial renovations during its lifetime.
10. *class.a, class.b*: These are relative classifications within a specific market. Class A buildings are the highest-quality properties. Class B buildings are a notch down. Class C buildings are the least desirable properties.
11. *green.rating*: an indicator for whether the building is either LEED- or EnergyStar-certified.
12. *LEED, Energystar*: indicators for the two specific kinds of green certifications.
13. *net*: an indicator as to whether the rent is quoted on a "net contract"" basis.
14. *amenities*: an indicator of whether at least one of the following amenities is available on-site: bank, convenience store, dry cleaner, restaurant, retail shops, fitness center.
15. *cd.total.07*: number of cooling degree days in the building's region in 2007.
16. *hd.total07*: number of heating degree days in the building's region in 2007.
17. *total.dd.07*: the total number of degree days (either heating or cooling) in the building's region in 2007.
18. *Precipitation*: annual precipitation in inches in the building's geographic region.
19. *Gas.Costs*: a measure of how much natural gas costs in the building's geographic region.
20. *Electricity.Costs*: a measure of how much electricity costs in the building's geographic region.
21. *cluster.rent*: a measure of average rent per square-foot per calendar year in the building's local market.

The first visualization we will make is a table of summary statisitcs for relevant variables

<table style="width:96%;">
<caption>Table continues below</caption>
<colgroup>
<col width="25%" />
<col width="23%" />
<col width="23%" />
<col width="23%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">GB.size</th>
<th align="center">GB.empl_gr</th>
<th align="center">GB.Rent</th>
<th align="center">GB.leasing_rate</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">Min. : 1624</td>
<td align="center">Min. :-24.950</td>
<td align="center">Min. : 2.98</td>
<td align="center">Min. : 0.00</td>
</tr>
<tr class="even">
<td align="center">1st Qu.: 50891</td>
<td align="center">1st Qu.: 1.740</td>
<td align="center">1st Qu.: 19.50</td>
<td align="center">1st Qu.: 77.85</td>
</tr>
<tr class="odd">
<td align="center">Median : 128838</td>
<td align="center">Median : 1.970</td>
<td align="center">Median : 25.16</td>
<td align="center">Median : 89.53</td>
</tr>
<tr class="even">
<td align="center">Mean : 234638</td>
<td align="center">Mean : 3.207</td>
<td align="center">Mean : 28.42</td>
<td align="center">Mean : 82.61</td>
</tr>
<tr class="odd">
<td align="center">3rd Qu.: 294212</td>
<td align="center">3rd Qu.: 2.380</td>
<td align="center">3rd Qu.: 34.18</td>
<td align="center">3rd Qu.: 96.44</td>
</tr>
<tr class="even">
<td align="center">Max. :3781045</td>
<td align="center">Max. : 67.780</td>
<td align="center">Max. :250.00</td>
<td align="center">Max. :100.00</td>
</tr>
<tr class="odd">
<td align="center">NA</td>
<td align="center">NA's :74</td>
<td align="center">NA</td>
<td align="center">NA</td>
</tr>
</tbody>
</table>

<table style="width:94%;">
<caption>Table continues below</caption>
<colgroup>
<col width="23%" />
<col width="23%" />
<col width="23%" />
<col width="23%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">GB.stories</th>
<th align="center">GB.age</th>
<th align="center">GB.cd_total_07</th>
<th align="center">GB.hd_total07</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">Min. : 1.00</td>
<td align="center">Min. : 0.00</td>
<td align="center">Min. : 39</td>
<td align="center">Min. : 0</td>
</tr>
<tr class="even">
<td align="center">1st Qu.: 4.00</td>
<td align="center">1st Qu.: 23.00</td>
<td align="center">1st Qu.: 684</td>
<td align="center">1st Qu.:1419</td>
</tr>
<tr class="odd">
<td align="center">Median : 10.00</td>
<td align="center">Median : 34.00</td>
<td align="center">Median : 966</td>
<td align="center">Median :2739</td>
</tr>
<tr class="even">
<td align="center">Mean : 13.58</td>
<td align="center">Mean : 47.24</td>
<td align="center">Mean :1229</td>
<td align="center">Mean :3432</td>
</tr>
<tr class="odd">
<td align="center">3rd Qu.: 19.00</td>
<td align="center">3rd Qu.: 79.00</td>
<td align="center">3rd Qu.:1620</td>
<td align="center">3rd Qu.:4796</td>
</tr>
<tr class="even">
<td align="center">Max. :110.00</td>
<td align="center">Max. :187.00</td>
<td align="center">Max. :5240</td>
<td align="center">Max. :7200</td>
</tr>
<tr class="odd">
<td align="center">NA</td>
<td align="center">NA</td>
<td align="center">NA</td>
<td align="center">NA</td>
</tr>
</tbody>
</table>

<table>
<caption>Table continues below</caption>
<colgroup>
<col width="22%" />
<col width="24%" />
<col width="24%" />
<col width="28%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">GB.total_dd_07</th>
<th align="center">GB.Precipitation</th>
<th align="center">GB.Gas_Costs</th>
<th align="center">GB.Electricity_Costs</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">Min. :2103</td>
<td align="center">Min. :10.46</td>
<td align="center">Min. :0.009487</td>
<td align="center">Min. :0.01780</td>
</tr>
<tr class="even">
<td align="center">1st Qu.:2869</td>
<td align="center">1st Qu.:22.71</td>
<td align="center">1st Qu.:0.010296</td>
<td align="center">1st Qu.:0.02330</td>
</tr>
<tr class="odd">
<td align="center">Median :4979</td>
<td align="center">Median :23.16</td>
<td align="center">Median :0.010296</td>
<td align="center">Median :0.03274</td>
</tr>
<tr class="even">
<td align="center">Mean :4661</td>
<td align="center">Mean :31.08</td>
<td align="center">Mean :0.011336</td>
<td align="center">Mean :0.03096</td>
</tr>
<tr class="odd">
<td align="center">3rd Qu.:6413</td>
<td align="center">3rd Qu.:43.89</td>
<td align="center">3rd Qu.:0.011816</td>
<td align="center">3rd Qu.:0.03781</td>
</tr>
<tr class="even">
<td align="center">Max. :8244</td>
<td align="center">Max. :58.02</td>
<td align="center">Max. :0.028914</td>
<td align="center">Max. :0.06280</td>
</tr>
<tr class="odd">
<td align="center">NA</td>
<td align="center">NA</td>
<td align="center">NA</td>
<td align="center">NA</td>
</tr>
</tbody>
</table>

<table style="width:24%;">
<colgroup>
<col width="23%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">GB.cluster_rent</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">Min. : 9.00</td>
</tr>
<tr class="even">
<td align="center">1st Qu.:20.00</td>
</tr>
<tr class="odd">
<td align="center">Median :25.14</td>
</tr>
<tr class="even">
<td align="center">Mean :27.50</td>
</tr>
<tr class="odd">
<td align="center">3rd Qu.:34.00</td>
</tr>
<tr class="even">
<td align="center">Max. :71.44</td>
</tr>
<tr class="odd">
<td align="center">NA</td>
</tr>
</tbody>
</table>

By inspection of the summary statistics, the numerical variables appear to behave well and do not send any alarming signals that there is an error. We have made the assumption that all missing values and non-sensible observations were dealt with during the data cleaning process.

The first mistake the "data guru" made when considering his analysis was dropping observations from buildings that have an occupancy rate less than 10%. After calculating that only 215 buildings of the 7,894 buildings in the data set have low occupancy rates, we conclude that it is neccessary, or adivsed to not drop these buildings from the analysis for two reasons. Their existence in the analysis is likely to have very little effect on our outcomes, and there is likely valid reasons for low occupancy, like renovations, over-priced rent, or other specific factors.

    ## [1] 215

The next statistic the "excel-guru" looked at was the median market rent grouped by green and non-green buildings. The median rent we calculated was the same as the excel guru's calculation, $25 for non-green buildings and $27.60 for green buildings.

![](Exercise_1_-_Data__FINAL__files/figure-markdown_github/unnamed-chunk-4-1.png)

We also thought it would be useful to examine the mean and found that the mean rent for green buildings is $30.02, while the mean rent for nongreen buildings is $28.27. The difference in these means is $1.75.

In the next step of our analysis was to examine the variance of rent of the green and non-green buildings. It is crucial to look at the variance, since the variance will tell us more about how much potential revenue is "garaunteed". This enables us to see the differences between possible profitability for each type of building and estimate the ranges of possible rent prices.

The variance of rent for green buildings was $167.70, or a standard deviation of $12.95. The variance of rent for non-green buildings was $232.70, or a standard deviation of $15.25.

The 95% confidence interval of mean rent for a green building is (4.12, 55.92), while the 95% confidence interval of mean rent for a nongreen building is (-2.24, 58.78). This reveals that rent is highly skewed and that potential revenues can vary greatly. This weakens his analysis of median, or even mean, rent becuase the distributions of rents are hihgly skewed and have high variance. The validity of using this information to preform future calculations on, specifically potential revenues, is inherently flawed.

<table style="width:29%;">
<colgroup>
<col width="20%" />
<col width="8%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">green_rating</th>
<th align="center">Rent</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">0</td>
<td align="center">25</td>
</tr>
<tr class="even">
<td align="center">1</td>
<td align="center">27.6</td>
</tr>
</tbody>
</table>

<table style="width:31%;">
<colgroup>
<col width="20%" />
<col width="9%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">green_rating</th>
<th align="center">Rent</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">0</td>
<td align="center">28.27</td>
</tr>
<tr class="even">
<td align="center">1</td>
<td align="center">30.02</td>
</tr>
</tbody>
</table>

<table style="width:31%;">
<colgroup>
<col width="20%" />
<col width="9%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">green_rating</th>
<th align="center">Rent</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">0</td>
<td align="center">232.7</td>
</tr>
<tr class="even">
<td align="center">1</td>
<td align="center">167.7</td>
</tr>
</tbody>
</table>

    ## [1] 15.25451

    ## [1] 12.9499

    ## [1] 1.75

    ## [1] 4.120193

    ## [1] 55.91981

    ## [1] -2.239015

    ## [1] 58.77902

    ## Warning: `show_guide` has been deprecated. Please use `show.legend`
    ## instead.

![](Exercise_1_-_Data__FINAL__files/figure-markdown_github/unnamed-chunk-6-1.png)

The "data guru" goes on to calculate the extra revenue expected each year for a 250,000 square foot building. He took the difference in median rents, $2.60 and multiplied that by 250,000 sq ft to render extra revenues of $650,000 per year. The first, out of many flaws, of this calculation is that it is unknown as to why he is calculating expected extra revenue for a 250,000 sq ft building, when we only know that the building is 15 stories high. In reality, the expected square feet of a 15 story building is 262,977, refer to the plot below. If using the same difference in median rent to calculate extra revenues, this would render $683,741, which is $33,741 more dollars per year than his original estimate.

    ## (Intercept)     stories 
    ##   -37335.16    20020.83

![](Exercise_1_-_Data__FINAL__files/figure-markdown_github/unnamed-chunk-7-1.png)

    ## [1] 262977.3

    ## [1] 683741

The next very obvious flaw of his calculations is that he does not take into account that less than 100% of the 250,000 (actually 262,977) square feet of the building will even be leasable, meaning the owner will not be collecting rent on every square foot of the building, unless the whole building is leased out. The final calculation for excess revenue per year has the possibility to vary greatly since, as we found above, the average rent of both green and non-green buildings vary an awful lot.

For buildings with rents one standard deviation lower than the average market rent, green buildings can expect an average rent of $17.07 per square foot, while non-green buildings can expect an average rent of $13.02 per square foot. This means that for "lower" end/rent buildings, green buildings still preform better than non-greeen buildings by $4.05 per square foot better to be exact.

For building with rents one standard deviation higher than the average market rent, green buildings can expect an average rent of $42.97 per square foot, while non-green buildings can expect an average rent of $43.52 per square foot. This means that for "higher" end/rent buildings, non-green buildings preform better than greeen buildings by $0.65 per square foot better to be exact.

This is an interesting finding, because it clarifies which market finds greater value in energy-cost reducing measures. We found that a green certification appears to have a higher impact on lower rent buildings. We can derive that these potential tenants, while concerned with associating themselves as "eco-friendly", will more likely still place a higher value on their personal savings by preferring to save money on electricity costs. This is an important insight that the "data guru" did not include in his analysis by failing to take the variance of rent into account.

The next part of the analysis that we found to be misleading was the cost recouperation from the costs associated with obtaining green certification. He estimated that total costs for building a green building will be $105 million, which we cannot verify to be true, but will accept as true. Using the values we have obtained and his methodology, the extra revenue that we expect from obtaining a green rating, of $683,741 would be recouperated in 7.3 years.

This calculation still does not make much sense, because it implies 100% occupancy and does not account for variation in rent prices. As we can see from the plot below, new buildings normally do not have 100% occupancy. From what we can see from the market of buildings similar to ours, less than 10 years old and betwee 10 and 20 stories, average leasing rate does not surpass the 90% occupany until approximately 6 years old. This means that we would not recover green rating certification costs at the rate that he proposed, instead it would be significantly slower.

![](Exercise_1_-_Data__FINAL__files/figure-markdown_github/unnamed-chunk-9-1.png)

He then states that past the 9 year mark, the owner would be making the $650,000 in green certification revenue as profit for the next thirty years. Clearly the owner will be recovering from certification costs much later than 9 years after completion, and the claim that she will collect profit for the next 30 years is also outlandish. The "data guru" clearly did not take renovations or other unexpected costs into consideration when making that statement. The density plot below reveals that green buildings of 32 years have had at least one renovation in the past. This disputes his claim that we will earn profits for 30 years, since some of the profits will be allocated to renovations within those 30 years.

![](Exercise_1_-_Data__FINAL__files/figure-markdown_github/unnamed-chunk-10-1.png)

As an extension to the cost benefit analysis done above, we think it would be important to include how leasing rates are expected to change with employment growth rate. We are not garaunteed a 90% occupancy rate, so we must consider other confounding variables, such as employment growth rates in the region. We are intersted in how the leasing rate will change as the employment growth fluctuates. We notice that for negative employment growth rates, the leasing rate is very high for all buildings. This is interesting because it is not intuitive, this may be because there are such few observations for that employment growth rate. One thing that does stand out is that the leasing rates for green buildings is normally relatively high, it drops below 20 only a few times. This is indicitive that the owners ability to fill spots in the building as employment growth rates fluctuate should not be a major concern to her.

    ## Warning: Removed 74 rows containing missing values (geom_point).

![](Exercise_1_-_Data__FINAL__files/figure-markdown_github/unnamed-chunk-11-1.png)

Data Visualization 2: Flights at ABIA
-------------------------------------

The following visualization shows four different types of delays in minutes for airports on the East coast of the United States. The graphs show us that duration of nearly all delays are low in minutes for flights departing or arriving from Austin International Bergstorm Airport. We also found carrier delays are also very low for airports on the East coast where data was available. The grey points on the graphs signify incomplete observations for those airports, while the colored points are a scale of how long the delay is in minutes. The color green reveals a delay close to zero minutes and the color red is the maximum minutes of delay, which was never reached for this region of the United States.

Overall, the data shows us that, on average, delays on the East coast coming to and from Austin did not comsume many minutes of air-travelers' time and might reveal some information about the efficiency of Austin Bergstorm International Airport.

    ## 
    ## Attaching package: 'maps'

    ## The following object is masked from 'package:purrr':
    ## 
    ##     map

    ## Source : https://maps.googleapis.com/maps/api/staticmap?center=World&zoom=4&size=640x640&scale=2&maptype=terrain&language=en-EN&key=xxx-8XB9V3HPyEo

    ## Source : https://maps.googleapis.com/maps/api/geocode/json?address=World&key=xxx-8XB9V3HPyEo

![](Exercise_1_-_Data__FINAL__files/figure-markdown_github/unnamed-chunk-12-1.png)

Regression vs. KNN
------------------

First, we visualize what our data looks like. From the two scatter plots below, we can deduce that as the mileage of the car increases, the sale price of the car decreases. This is a good finding, because it follows inuition.

![](Exercise_1_-_Data__FINAL__files/figure-markdown_github/unnamed-chunk-13-1.png)

The following tables represent the RMSEs of the the simple linear models, linear model with a polynomial, and the 7 KNN models with varying number of neighbors Mercedes Benz S Class 350. We can see that in this case, the KNN with around 60 neighbors does the best job at predicting price of the S Class 350, with the smallest RMSE of 10721. The plots show the predictions of KNN estimates with varying neighbors and an orange line which is the fit of the linear model with mileage squared as the explanatory variables. We can see that as the number of neighbors increases, the error of the predictions increases. In this case, the optimal value of K is 60.

<table>
<caption>Table continues below</caption>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">rmse.ytest..ypred_lm1.</th>
<th align="center">rmse.ytest..ypred_lm2.</th>
<th align="center">rmse.ytest..ypred_knn4.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">12857</td>
<td align="center">10805</td>
<td align="center">11675</td>
</tr>
</tbody>
</table>

<table>
<caption>Table continues below</caption>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">rmse.ytest..ypred_knn10.</th>
<th align="center">rmse.ytest..ypred_knn30.</th>
<th align="center">rmse.ytest..ypred_knn60.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">10597</td>
<td align="center">10962</td>
<td align="center">11380</td>
</tr>
</tbody>
</table>

<table style="width:75%;">
<caption>Table continues below</caption>
<colgroup>
<col width="37%" />
<col width="37%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">rmse.ytest..ypred_knn80.</th>
<th align="center">rmse.ytest..ypred_knn100.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">12133</td>
<td align="center">13184</td>
</tr>
</tbody>
</table>

<table style="width:38%;">
<colgroup>
<col width="37%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">rmse.ytest..ypred_knn300.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">23590</td>
</tr>
</tbody>
</table>

![](Exercise_1_-_Data__FINAL__files/figure-markdown_github/unnamed-chunk-15-1.png)

The following tables represent the RMSEs of the the simple linear models, linear model with a polynomial, and the 7 KNN models with varying number of neighbors for Mercedes Benz S Class 65 AMG. We can see that in this case, the KNN with 10 neighbors does the best job at predicting price of the S Class 65 AMG, with the smallest RMSE of 23719. The plots show the predictions of KNN estimates with varying neighbors and an orange line which is the fit of the linear model with mileage squared as the explanatory variables. We can see that as the number of neighbors increases, the error of the predictions dramatically increases. In this case, the optimal value of K is approximately 10.

<table>
<caption>Table continues below</caption>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">rmse.ytest..ypred_lm1.</th>
<th align="center">rmse.ytest..ypred_lm2.</th>
<th align="center">rmse.ytest..ypred_knn4.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">45852</td>
<td align="center">33690</td>
<td align="center">28031</td>
</tr>
</tbody>
</table>

<table>
<caption>Table continues below</caption>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">rmse.ytest..ypred_knn10.</th>
<th align="center">rmse.ytest..ypred_knn30.</th>
<th align="center">rmse.ytest..ypred_knn60.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">27284</td>
<td align="center">28797</td>
<td align="center">28875</td>
</tr>
</tbody>
</table>

<table style="width:75%;">
<caption>Table continues below</caption>
<colgroup>
<col width="37%" />
<col width="37%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">rmse.ytest..ypred_knn80.</th>
<th align="center">rmse.ytest..ypred_knn100.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">31363</td>
<td align="center">36999</td>
</tr>
</tbody>
</table>

<table style="width:38%;">
<colgroup>
<col width="37%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">rmse.ytest..ypred_knn300.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">71561</td>
</tr>
</tbody>
</table>

![](Exercise_1_-_Data__FINAL__files/figure-markdown_github/unnamed-chunk-17-1.png)

The two following graphs show the movement of the RMSE as the number of neighbors increases for both types of S Class Mercedes Benz. They appear to move in very similar directions, having RMSE increase with K. Looking at the plot of RMSE against K for the S Class 350, we see that as K approaches 300 and further, the RMSE becomes much larger. Since we are looking for the smallest RMSE, we verify that the optimal K for this class of car is closer to 60.
Looking at the plot of RMSE against K for the S Class 65 AMG's, we see that as the number of neighbors we use to predict price increases, the RMSE also increases. One thing to make note of is the magnitude of the RMSE for this subset of cars. The RMSE is much higher in magnitude than its 350 counterpart. We are able to verify that the optimal K for this class is close to 10. The higher K reveals that we are estimating f(x) using many points, possibly far away (this increases bias), and the lower K reveals that we are using not very many points that are likely close by (this reduces bias).

Each class of car is telling us different stories about what the optimal K is. The S Class 350 is revealing that a slightly larger K is optimal, whereas the S Class 65 AMG is telling us that a small K is optimal. The reason that this may be is becuase of the size, quality and behavior of the data sets. Data sets with large numbers of observations are inherently better and normally behave better than data sets with low numbers of observations. The KNN estimations for the S Class 65 AMG price have quite a few less observations than the S Class 350. Although there is more data for the S Class 350, it appears to contain more clusters than the S Class 65 AMG data. Since the data appears to have clusters, the higher optimal K value for the S Class 350 reveals that the we are likely having to use points slightly further away to estimate f(x), compared to the S Class 65 AMG.

![](Exercise_1_-_Data__FINAL__files/figure-markdown_github/unnamed-chunk-18-1.png)![](Exercise_1_-_Data__FINAL__files/figure-markdown_github/unnamed-chunk-18-2.png)
