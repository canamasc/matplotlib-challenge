# matplotlib-challenge
Georgia Tech Data Science Bootcamp


This code examines statistics and trends for data related to a drug trial done on mice with tumors.

 FINAL OBSERVATIONS

 1. Average tumor volume and mouse weight are correlated, so final
 tumor volume alone is not enough to decide which drug regimen is best.
 It would be better to consider total % size reduction of tumor instead.

 2. Ramicane had mice with smallest tumors at the end 
 of treatment and has relatively small spread of results, so it could be
 a good drug.

 3. It may be wise to extend time period of the study, as we can see from
 the line plot that reduction in tumor size is not monotonically
 decreasing - so there is a chance that the tumor sizes could increase again even with continued
 drug use.

First we import the 2 csv files and examine their shapes and columns before merging them on shared column 'Mouse ID' and cleaning the resultant data frame (get rid of mice with duplicate time points).

Summary statistics (mean, median, variance, standard deviation, SEM) found of tumor volumes found for each drug regimen. This can be done using .groupby() method on the data frame.

A bar plot is generated to show the total number of mice on each drug regimen.

A pie plot is generated to show the mice population distribution of sex.

We find the final tumor volume for each mouse by using the last available time point, and add this info for to a list object corresponding to that mouse's drug regimen. For each drug, we find the Quartile 1 and Quartile 3 info along with the IQR. We point out potential outliers by using the rule: Outliers are either less than Q1 - 1.5 * IQR or are greater than Q3 + 1.5 * IQR

A box plot is generated to show the above results graphically - Infubinol is the only drug regimen with an outlier for final tumor volume, which is seen as a red square on the plot and is on the low side.

A mouse on the Capomulin regimen (j246) is picked and a line plot is generated showing the change in its tumor volume over time.

A scatter plot is generated showing the relationship between a mouse's weight and their average tumor volume. They appear to be pretty strongly correlated, with a correlation coefficient of 0.84. A line of best fit is found using linregress and plotted on top of the scatter plot. The line equation is y = 0.95x + 21.55, and the r-squared value is 0.709. 





