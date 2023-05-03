# project-1
Burgan, Layla
Sakauye, Clare
Talamantes, Justin
2015 Crime in Los Angeles Report 

Data Summary, Cleaning, and Restrictions (Layla)
	This data proved difficult to work with for a few reasons. Firstly, it is not a sample of crimes in Los Angeles, but a comprehensive population, as the data was taken directly from police reports. This means that it contains every reported crime from 2010-2017, which is over 3 million data points. This alone made the data set difficult to work with as it was so big it could not be uploaded to GitHub or easily examined in Python or Excel. To combat this, our group decided to take a subset of crimes, just from the year of 2015. However, as this was still over 1 million data points, it still proved to be too large to work with for a project. This influenced our decision to subset further to only include 5 “spotlight” crimes, which we will thoroughly investigate. The crimes we decided on were murder, arson, kidnapping, pickpocketing, and “throwing object(s) at a moving vehicle”. These crimes were picked because of their relative ease in understanding (many people know what murder is, while other more specific crimes like “larceny” can be difficult to understand). The last crime, investigate. The crimes we decided on were murder, arson, kidnapping, pickpocketing, and “throwing object(s) at a moving vehicle” was chosen for its perceived humor, and to lighten the tone of an otherwise very dark subject matter.
	While heavily subsetting the data set made it much easier for us to complete our analysis, it does mean that our findings are also just as limited. We can only generalize any findings to these specific crimes, and preferably only to the year 2015. Obviously, our generalizations also only pertain to Los Angeles City.

Question 1: Does Area Affect the Amount of Crime? (Layla)
	In researching this question, I produced a map of Los Angeles using hvplot.points, and plotted the location of each crime along with its type. By observing the map, it was clear that certain crimes were more prevalent in certain places. For example, pickpocketing was more concentrated in touristy areas such as Hollywood, Downtown, and Venice Beach. On the contrary, homicide and arson were found more in the south of L.A. 
I then conducted a Chi-Squared analysis of Goodness of Fit to check if the areas had different proportions of crime happening in them. My hypothesis was that all 21 police-defined areas have the same proportion of crime, and my  alternative Hypothesis was that at least one of the 21 police-defined areas has a different proportion of crime. This resulted in a test statistic of  719.02 and a 
critical value of 31.41 As the test statistics was larger than the critical value, we can conclude that at least one area has significantly different proportions of crime. This was further highlighted in the bar plot of crime by police defined area, which showed 77th street as having far more crime than other areas. 

Question 2: Does sex, age or ethnicity make a person more susceptible to being a victim of a crime? What demographics are most at risk for the specific crimes of focus? (Clare)
To determine whether one's sex, age or ethnicity makes them more susceptible to being a victim of a crime, I first focused on sex. Based on a pie chart of aggregate victim sex, males make up a greater percentage of the victims at 56.3%, while females make up 43.5%. Variable X, which is assumed to mean no reported sex, makes up 0.2%. At less than one percent, X can be considered insignificant compared to males and females. Based on this data, it can be said that males are at a greater risk than females for being victims of a crime. 
A chi-square test was also performed to determine if there was any statistical significance in the distribution of male and female victims. My null hypothesis was that there was no statistical significance in the distribution of male and female victims, while my alternative hypothesis stated that there was statistical significance. The chi-square test yielded a value of 15.93 which was much greater than the critical value of 3.84. Additionally, the p-value of 6.58e-05 was less than 0.05. Therefore, it can be said with a 95% confidence level that the results are statistically significant. 
In order to get further clarity on the influence of victim sex, I divided the crime subset into individual pie charts. The charts highlight that while males may be more at risk of being victim to a crime in general, specific crimes can vary greatly. For criminal homicide, arson and an object being thrown at a moving vehicle the majority of victims are male. But for kidnapping and pickpocketing, the majority of victims are female. 
Looking at victim age next, I calculated the average, median, minimum and maximum along with variance and standard deviation.  Based on the aggregate victim  data and the summary statistics table broken up crime, it is clear that the average and median age of victims falls in the thirties. In some instances, like if the data is normally distributed, it may make more sense to use the mean over the median. However, in this case, the median and mean are pretty similar in value. Based on this data it appears that the age range most affected by crime are those in their thirties. 
There is also quite a spread in the victim ages as seen by the large variances and higher standard deviations. This makes sense as the minimum victim ages can be as young as ten and the eldest as old as 89. Therefore, while it may be more common for a victim to be in their thirties, those younger and older are still at risk.
I also created a box and whisker plot to visualize the age distribution and determine outliers.  From the plot, it can be seen that kidnapping and an object being thrown at a moving vehicle affect younger members of Los Angeles compared to the other crimes. It could be expected that an object being thrown at a moving vehicle affects younger people because those in their eighties or nineties are not driving as much compared to younger groups. Interestingly, the minimum age for an object being thrown at a moving vehicle is well below sixteen. This dataset doesn't specify if the victim listed is the driver or a passenger, which could explain the minimum age of twelve.  Arson and pickpocketing conversely have the highest maximum ages. Pickpocketing may affect an older group of victims because they may be easier to steal from compared to younger groups. In terms of outliers, criminal homicide, arson and kidnapping are the only crimes to yield outlying victim ages.  All three groups have outliers that are older as opposed to younger. 
In regard to victim descent, I created a bar chart to show the groups most affected by crime.  The largest affected descent group is Hispanic followed by Black, White and Other. While other victim descent groups are affected by crime, they are much smaller in comparison to the larger groups. The disproportionate number of Hispanics being victim to crime in Los Angeles could be due in a large part to the population. According to the U.S. Census Bureau, 48.4% of the population in LA is Hispanic or Latino. (https://www.census.gov/quickfacts/losangelescitycalifornia)
I also performed a chi-square test to determine if there was any statistical significance in the distribution of victim descent. With a chi square value of 1,157.91 and a critical value of 12.59, it can be said at a 95% confidence level  that the victim's descents are statistically significant.
Lastly, I evaluated the victim descent for each specific crime. Using bar charts, I saw that for criminal homicide, arson, kidnapping and an object being thrown at a moving vehicle, the most affected group is Hispanics. However, for pickpocketing, the most affected group is White. Like the aggregate data, the most affected groups are Hispanic, Black, White and Other. Additional groups also appear in the bar charts but their quantities are less than half of the majority groups. 
In conclusion, males, those in their thirties and those of Hispanic descent are most at risk for being victims of a crime. If evaluating specific crimes, kidnapping and pickpocketing differ from the general takeaways. Females are more likely to be victims of kidnapping while females and those of White descent are more likely to be victims of pickpocketing. If further data analysis could be performed, it may be beneficial to dive deeper into multiple years to determine if 2015 shares patterns for victim demographics. 




Question 3: What times of day are crimes more common? (Layla)
	To investigate this, first I had to contend with the time format that was provided in the data set. Time was written in military time, as a four-digit integer rather than a string (i.e. 1:00pm was written as 1300). After binning the data both by clock hour and a “time category” ( early morning, morning, afternoon, or night). I could begin answering the question. 
A bar plot ordered from midnight to eleven pm in order shows that crime mostly happens at night, with the least crime happening in the morning. I can surmise that this is because the most activity is happening in the city from 7-9am as people wake up and head to work, so it is not an opportune time for would-be criminals. The graph shows crime steadily increasing through the afternoon (perhaps criminals sleep in?) and peaking at 11pm. This makes sense, as the darkness of night provides cover for nefarious deeds. 
A look at the pie charts of crime times separated by type of crime reveals further insight. Crimes such as pickpocketing are more likely to happen in the afternoon. This makes sense, as pickpocketing usually happens in very crowded areas, and lots of people are on the streets of L.A. in the daytime, especially vulnerable tourists. However, most other crimes like arson, homicide, and kidnapping, mostly happen at night. As these crimes do not require unwitting tourists, it does make sense that they would happen mostly while the city sleeps. 


Question 4: Does the time of year have any effect on the types of crime committed? (Justin)
When analyzing this question, we wanted to take a broader look first to see if there is any relationship between all our crime categories committed throughout the year and look at each month.  To do, so we decided to use a Chi-square test.  Our Hypothesis is for all five crime categories, the time of year has no effect on the level of crime committed. Our alternative hypothesis was that the time of year has an impact on the level of crime committed. We set our confidence level at .95 and degrees of freedom at 11 giving us a critical value of 19.675.  When running our Chi-squared test we got a statistical value of 126.282 and p-value of 9.822515205611252e-22.  Given the statistical value is much greater than our critical value, we can conclude there is a statistically significant difference in the amount of crime being committed between the months.  We used a bar chart illustrating all months of the year and the amount of crime committed for all of our categories per month to help visualize our finding.To help test this hypothesis We used bar charts to see the relationship of each crime being committed and the month it was being committed. 
We found that across all category’s crime was the lowest in November and December. Three out of our five (Kidnapping, Pickpocket, Throwing object at moving vehicle) crime categories tend to have a higher rate during spring and summer time.  
In conclusion we found that the time of year does have an effect on types of crimes committed.  For crime categories Kidnapping, Pickpocketing, and Throwing objects at moving vehicles you can see that there is more potential for these crimes to be committed in spring and summer time.  A possible explanation for this could be that young students are on break around these times and tend to be outside more, as well as more tourists in the spring and summertime for certain locations in LA.



Question 5: What effect does temperature have on the types of crimes being committed?(Layla)
	This investigation required the use of an API to answer. I used the Open Meteo weather API to gather historical data on the temperatures in L.A. when these crimes were being committed. Our thoughts as a group were that the heat can affect peoples’ moods and temperaments, and therefore could have an impact on crime. I created a loop that went through the rows of data, requesting the max temperature for the day of each crime from the endpoint. This was unwise, as the code took a very long time to run. However after about 15 minutes I had the maximum temperature as a new column in the data set. I used this to make a boxplot of temperatures, grouping by the type of crime, in order to see any differences. There were no notable differences in the boxplots, but I performed an ANOVA test anyways.  My hypothesis was that the average temperature at time of crime is equal for each type of crime, and my alternative hypothesis was that the average temperature at time of crime is different between types of crime. After obtaining a p-value of  .47, I concluded that there is not enough evidence to suggest that the mean temperature is different based on the type of crime.  

Question 6: Does Heat affect the amount of crime?(Layla)
	This question proved a lot more difficult to answer than I originally thought. The issue was that I had plenty of data for days where there was crime, but no data for days that there wasn’t any crime. So it wasn’t really possible to compare the two. Finally I was able to sort of flip my question into something that I could study so it became: is the average temperature of the data different from the average temperature in Los Angeles? This was a question within my means. Since our group theory was that more heat = more crime, I decided to look at September. In 2015, September was the hottest month of the year in Los Angeles, according to the L.A. Almanac, with an average of 78.7 degrees fahrenheit. I subsetted the data to only September crimes, found the average temperature which was 87 degrees,, and proceeded with a one sample t-test.  I started with the hypothesis that the average temperature of days with crime is not different from the average temperature of the month of September. The alternative hypothesis was that the average temperature of days with crime is significantly different from the average temperature of september. After obtaining a p-value of .03, we can reject the null hypothesis. There is sufficient evidence to suggest that the mean temperature while crimes were being committed is significantly higher than the average temperature in September. 

Conclusion: 
- As we studied this data, one thing became clear: there is a LOT of crime in Los Angeles. Although the process of cleaning and subsetting the data was arduous, we were still able to reach the following conclusions: 
- Area DOES have an effect on the amount of crime
- The time when crime happens is different based on the TYPE of crime 
- Weather does NOT have an effect on the TYPE of crime happening 
- Crimes DO happen at different average temperatures than the monthly average (for September)
- Males, those in their thirties, and those of Hispanic descent are more likely to be victims of a crime
- Time of year does have an effect on types of crimes committed

