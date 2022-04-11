# MechaCar_Statistical_Analysis

## Overview:
A few weeks after starting his new role, Jeremy is approached by upper management about a special project. AutosRUs’ newest prototype, the MechaCar, is suffering from production troubles that are blocking the manufacturing team’s progress. AutosRUs’ upper management has called on Jeremy and the data analytics team to review the production data for insights that may help the manufacturing team.

In this challenge, you’ll help Jeremy and the data analytics team do the following:

Perform multiple linear regression analysis to identify which variables in the dataset predict the mpg of MechaCar prototypes
Collect summary statistics on the pounds per square inch (PSI) of the suspension coils from the manufacturing lots
Run t-tests to determine if the manufacturing lots are statistically different from the mean population
Design a statistical study to compare vehicle performance of the MechaCar vehicles against vehicles from other manufacturers. For each statistical analysis, you’ll write a summary interpretation of the findings.

The [MechaCar_mpg.csv ](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/MechaCar_mpg.csv) dataset contains mpg test results for 50 prototype MechaCars. The MechaCar prototypes were produced using multiple design specifications to identify ideal vehicle performance. Multiple metrics, such as vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance, were collected for each vehicle. Using your knowledge of R, you’ll design a linear model that predicts the mpg of MechaCar prototypes using several variables from the MechaCar_mpg.csv file. 

## Results

### Linear Regression to Predict MPG 
Using the [MechaCar_mpg.csv ](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/MechaCar_mpg.csv) file and [MechaCarChallenge.Rmd](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/MechaCarChallenge.Rmd) file I got the following out put for linear regression to predict MPG:

MechaCar_mpg_df

![mechaCar_mpg_df](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/Image/mechacar_mpg_df.png)

Linear regression model

![linear regression model](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/Image/linear%20model.png)

summary statistics

![summary statistics](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/Image/linear%20model_summary.png)

* Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?

From the dataset results it can be  predicted that the following variables/coefficients provided a non-random amount of variance to the mpg values:

vehicle weight(0.0776)
spoiler angle(0.3069)
AWD(All Wheel Drive)(0.1852)
The vehicle length, and vehicle ground clearance on the other hand have a significant impact on miles per gallon on the MechaCar prototype.

* Is the slope of the linear model considered to be zero? Why or why not?

p-Value: 5.35e-11, is much smaller than the assumed significance level of 
0.05  . Thus the slope of the linear model is not considered to be zero because the p-value is less than 0.05.


* Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?


This linear model has an r-squared value of 0.7149, which means that approximately 71% of all mpg predictions will be correct when using this linear model. Relatively speaking, this linear model does predict mpg of MechaCar prototypes effectively.

## Summary Statistics on Suspension Coils
The MechaCar[ Suspension_Coil.csv](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/Suspension_Coil.csv) dataset contains the results from multiple production lots. In this dataset, the weight capacities of multiple suspension coils were tested to determine if the manufacturing process is consistent across production lots. Using your knowledge of R, you’ll create a summary statistics table to show:

* The suspension coil’s PSI continuous variable across all manufacturing lots
* The following PSI metrics for each lot: mean, median, variance, and standard deviation.

Using the [ Suspension_Coil.csv](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/Suspension_Coil.csv) file and [MechaCarChallenge.Rmd]() file I got the following out put for Summary Statistics on Suspension Coils:

Total_summary

![total_summary](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/Image/total_summary.png)

linear regression model

![lot_summary ](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/Image/lot_summary.png)




The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?

When looking at the entire population of the production lot, the variance of the coils is 62.29 PSI, which is well within the 100 PSI variance requirement
and we can say that current manufacturing data meet this design specification as a whole.

Individually, Lot 1 and Lot 2 are well within the 100 PSI variance requirement; with variances of 0.98 and 7.47 respectively. However, it is Lot 3 that is showing much larger variance in performance and consistency, with a variance of 170.29. It is Lot 3 that is disproportionately affecting the variance at the full lot level. 

So, lot 1 & lot 2 meet the current design specification perfectly and the lot3 should be more closely examined and fix the mistakes as it doesn't meet the current design specification.


## T-Tests on Suspension Coils

Using the  [MechaCarChallenge.Rmd](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/MechaCarChallenge.Rmd) file I got the following out put for t-test:

t.test
![t.test](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/Image/t_test.png)

Three t.test
![lot_summary_t.test ](https://github.com/NishatSultana3538/MechaCar_Statistical_Analysis/blob/main/Image/lot_summary_t_test.png)

Using your knowledge of R, perform t-tests to determine if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 pounds per square inch.

The results of the t-test analysis reveals that the true mean of the sample is 1498.78, which we also saw in the summary statistics above. With a p-Value of 0.06, which is higher than the common significance level of 0.05 resulting in a confidence interval of 93.972%, there is not sufficient evidence to support rejecting the null hypothesis. It may be stated that the dataset mean and the population mean are statistically similar. Also, the analysis predicts that the suspension coils dataset is statistically representative of the population mean 1500.

Next looking at each individual lots:

Lot 1 sample has the true sample mean of 1500, again as we saw in the summary statistics above. With a p-Value of 1, clearly we cannot reject the null hypothesis that there is no statistical difference between the  sample mean(1500) and the presumed population mean (1500).

Lot 2 has essentially the same outcome with a sample mean of 1500.02, a p-Value of 0.61, we cannot reject the null hypothesis that there is no statistical difference between the  sample mean(1500.02) and the presumed population mean (1500).

However, for Lot 3,  the sample mean is 1496.14 and the p-Value is 0.04, which is lower than the common significance level of 0.05. The mean of this sample is also significantly smaller in comparison to the previous two lots. This indicate that the null hypothesis can be rejected and it can be state that sample mean and the  population mean are statistically different.



## Study Design: MechaCar vs Competition
Using your knowledge of R, design a statistical study to compare performance of the MechaCar vehicles against performance of vehicles from other manufacturers.

1. Write a short description of a statistical study that can quantify how the MechaCar performs against the competition. In your study design, think critically about what metrics would be of interest to a consumer: for a few examples, cost, city or highway fuel efficiency, horse power, maintenance cost, or safety rating.

To compare MechaCar is priced correctly compared to it's competitor I will design a statistical analysis model where I will collect some key feature data to measure the performance and also collect cost (buying price + maintenance) and then perform multiple linear regression would be used to determine the factors that have the highest correlation/predictability with the cost effectiveness.

2. In your description, address the following questions:

* What metric or metrics are you going to test?

The following metrics need to be collected to perform the statistical analysis:
Safety Rating
Price
Maintenance cost
Fuel EfficIency 

* What is the null hypothesis or alternative hypothesis?

Null Hypothesis (Ho): MechaCar is cost effective based on its performance of key factors .

Alternative Hypothesis (Ha): MechaCar is NOT cost effective based on performance of key factors .

* What statistical test would you use to test the hypothesis? And why?
A multiple linear regression would be used to determine the factors that have the highest correlation/predictability with the cost effectiveness of the car; which combination has the greatest impact on price (it may be all of them!)
* What data is needed to run the statistical test?
Ratings on safety feature
Buying price
Average Annual Cost of Ownership(maintenance cost) 
Fuel Efficiency(mpg)
