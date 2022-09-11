# Mecha_Car_Statistical_Analysis
## Project Overview
The purpose of this project is to conduct a statistical analysis to summarize vehicle performance of an upcoming car model. The project will look at what factors predict mpg performance as well as how the prototype compare with other cars on the market.

## Resources
Data Source: MechaCar_mpg.csv, Suspension_Coil.csv

Software: R 4.2.1

## Linear Regression to Predict MPG
The MechaCar_mpg dataset includes the vehicle's weight, length, spoiler angle, ground clearance, whether it has AWD or not, and the miles per gallon achieved. After running a multiple regression analysis where the mpg is dependent on the other five variables, R provides the following output:

![This is an image](https://github.com/EricaEidelman/Mecha_Car_Statistical_Analysis/blob/main/mecha_car_multiple_regression.png)

The analysis shows that there are two variables - vehicle length and ground clearance - which provide a non-random amount of variance to the miles per gallon values. This can be concluded from the coefficient amounts, which are a lot smaller than the p-value of 0.05 assumed with a 95% confidence level. Given that there are two variables which provide a non-random amount of variance and the p-value of the model is less than 0.05, the slope of the linear regression model can be said to be non-zero. Otherwise, with a slope of zero we could conclude that miles per gallon are not affected by any other variable, which is not the case in this scenario. This model can be said to predict mpg values relatively well. The multiple r-squared value is 0.7149, which means that about 71% of the variability is explained by the model.

## Summary Statistics on Suspension Coils
The Suspension_Coil dataset provides information on suspension coil PSI for vehicles produced in three different manufacturing lots. A summary of the mean, median, variance and standard deviation across all three lots is provided below.

![This is an image](https://github.com/EricaEidelman/Mecha_Car_Statistical_Analysis/blob/main/total_summary.png)

According to the data, the variance in PSI across all three lots is 62.29, which is in accordance with the manufacturing specifications of no more than 100 PSI. However, the data in each lot individually tells a different story, as seen in the image below.

![This is an image](https://github.com/EricaEidelman/Mecha_Car_Statistical_Analysis/blob/main/lot_summary.png)

According to the summary above, at 170.29 PSI the variance in lot 3 significantly exceeds the cutoff of 100 PSI. Lots 1 and 2 have variances of 0.98 and 7.47, respectively, and so the significantly higher variance in lot 3 contributes to the overall variance across all three lots. 

## T-Tests on Suspension Coils
A third analysis done was on whether the mean PSI values across all three lots and in the lots individually are in line with an expected population mean of 1,500 PSI. Results of a t-test done on the mean across all three lots can be seen below.

![This is an image](https://github.com/EricaEidelman/Mecha_Car_Statistical_Analysis/blob/main/ttest_psi_all.png)

The result of the t-test done on all three lots shows that we cannot reject the null hypothesis that the means are the same. The p-value is 0.06028, which is greater than the p-value of 0.05 associated with a 95% confidence level. The data also shows that the mean PSI across all three lots is 1,498.78, with confidence interval cutoffs of 1,497.507 and 1,500.053. Given that the expected mean of 1,500 falls within those confidence intervals, that is further proof that the null hypothesis cannot be rejected.

T-tests were also conducted on the three manufacturing lots below, as seen in the following summary images.

![This is an image](https://github.com/EricaEidelman/Mecha_Car_Statistical_Analysis/blob/main/ttest_psi_lot1.png)

![This is an image](https://github.com/EricaEidelman/Mecha_Car_Statistical_Analysis/blob/main/ttest_psi_lot2.png)

![This is an image](https://github.com/EricaEidelman/Mecha_Car_Statistical_Analysis/blob/main/ttest_psi_lot3.png)

According to the t-tests, the mean of the PSI at lot 1 is exactly the same as the expected population mean of 1,500. This is shown in the t-test's statement that mean of x is 1,500 and in the p-value of 1. Given this, we cannot reject the null hypothesis that the PSI of lot 1 and the population are the same. The p-value of the t-test conducted on lot 2 is 0.6072, which is greater than the p-value of 0.05 and so the null hypothesis that the means of lot 2 and the population are the same also cannot be rejected. We can also see that the population mean of 1,500 falls within the confidence intervals surrounding the mean of lot 2. On the other hand, there is evidence to reject the hypothesis that the means of lot 3 and the population are the same, given that the p-value of the t-test for lot 3 is 0.04168 and thus lower than the p-value cutoff of 0.05. Additionally, the confidence intervals surrounding the lot 3 mean value of 1,496.14 are 1,492.431 and 1,499.849, which does not include the expected population mean of 1,500.
