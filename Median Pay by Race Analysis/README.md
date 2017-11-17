# Racical Pay Gap Visualization
[**Tableau Public Link To The Deceptive Claim** ](https://public.tableau.com/views/Deceptive/Discrimination?:embed=y&:display_count=yes&publish=yes&:toolbar=no)

[**Tableau Public Link To The Rebuttal Claim** ](https://public.tableau.com/views/Deceptive/NoDiscrimination?:embed=y&:display_count=yes&publish=yes&:toolbar=no) 

 
[**Jupyter Notebook Link**](https://github.com/meiyuanli312/Dashboard/blob/master/Redesign/Redesign%20-%20Meiyuan%20Li.ipynb)

This README file contains the following project delieverables

1. [Project statement](#1)
2. ['Making-of' documentation](#2)
3. [Intermediate visualization prototypes](#3)
4. [Final data visualization](#4)
5. [Road map with future features](#5)
6. [Showcase video](#6)

## <a name="1"></a>Project Statment 
### Motivation 
Gender pay gap is a hot issue and we have examined it closely more than once already.We found out that women need to take a step back to support their children therefore less working hour for them. Also, women tend to choose and stay on jobs that pay lower like health-care aides, receptionists, cashiers and food servers. There are other causes that I can’t list them all here but all this discussion got me thinking, what about race? Does race have anything to do with our paycheck?    
Furthermore, as a woman myself, is it being minority worsen my situation or improve it? So, I want to add the ‘race’ card into the play so that women or minority group can have an understanding where they should stand.

### Objective
By explore the factor 'race', I shall present how 'race' have decreased or widen the pay gap.

Another objective is trying to purposefully distort the data and deceive the audience.  If this objective is successfully achieved, we  will examine future visualization objectively and take great caution when developing our own visualization product.


### Data
I found a spread sheet on the Internet titled 'Salary By Race and Sex'  
[Link to the the data source](http://maamodt.asp.radford.edu/HR%20Statistics/Salary%20by%20Sex%20and%20Race.htm
)

### Project Plan

1. Search data for related visualization topic 'Racial Pay Gap'
1. Get the data and develop the intermediate deceptive claim and the opposite claim
1. Data Wrangling
1. Final Visualization for deceptive claim and the opposite


 
## <a name="2"></a>'Making-of' Document
### 1. Development Proces
1.1 The data I collected is from 2002 to 2011 US Median Salary by SEX and Race.First I extracted the data I needed in excel and add a new row 'All Minority' for every year.  
It looks like this:
![](pics/1.png)
![](pics/2.png)
![](pics/3.png)

1.2 Load this data into Tableau1.3 Data Wrangling in Jupyter Notebook1.4 Reload saved csv file into Tableau and refine the visualization

### 2. Data Wranging Steps
After searching 'Race Pay Gap' on google, I found this spreadsheet on this website.  

[Link to the data source](http://maamodt.asp.radford.edu/HR%20Statistics/Salary%20by%20Sex%20and%20Race.htm.)

![](pics/4.png)
![](pics/5.png)
![](pics/6.png)
![](pics/7.png)

Since this is a HTML page, web crawling on a HTML table is not much of help. So, I just copied and pasted this table into an excel spreadsheet.Then load it into a Jupyter notebookRead the data in:![](pics/8.png)From the first 10 rows, we can see that we only need those without 'NaN' data
![](pics/9.png)

Row 3 to Row 6 are the four races' income in 2011.So, all we need is to extract these four lines for every year.We can drop all NaN rows now, but if we drop them all, the 'Year' information will be lost, i.e., we wouldn't be able to know these four lines are which year's number.So, before we can remove all 'NaN', I will add ‘Year’ for each group.
![](pics/10.png)
To add the correct 'Year' for each group, we noticed that two rows after every Year-included-row such as '2011: Median U.S. Annual Salary by Race and Sex', it will be the start of four group 'Asian’.   So, we use this pattern to add 'Year' information for each group.
![](pics/11.png)

Drop any rows that has ‘NaN’ in it

![](pics/12.png)

What the original table looks like:![](pics/13.png)The first number column is for men, the second column is for women, and the third one is for all.All we need is the third column. So, drop first, second number and the percentage columns.![](pics/14.png)

Insert an 'All Minority' row for every year for later tableau use![](pics/15.png)

Fill the Median Salary and Year information for 'All Minority' rows.![](pics/16.png)

Rearrange the columns![](pics/17.png)

### 3. Reasoning

Reading the raw data only, I found that the Asian American earn the most. Then White, African American, Hispanic/Latino follow for all the years that I have collected data for.![](pics/18.png)It appears to me that there must be some reason behind the differences and the reason is not discrimination because clearly Asian as one of the minority groups outearn White American.And it didn’t happen for just one year but (at least) for the years I’ve collected data for.So, the deceptive/opposite claim would be ‘There is discrimination among races when it comes to your paycheck.To achieve this purpose, I would average all three minority groups’ salary and compare it with 'White'.Like this table:![](pics/19.png)Now White has more salary than all minority groups.The other side of claim would be what the original data suggested 'There is no discrimination among races when it comes to your paycheck'.
### 4. Detours

I felt that I was not confident enough to say 'There is absolutely no discrimination' because even though Asian outearn White, there are still two minority groups make less money than White. What if the discrimination lies just in these two groups?  I dug a little deeper and found out some article saying that because Asian are more likely to stay at Management job whereas the other two stayed at relatively low-paying jobs. The reason behind this is probably education. I tried to incorporate this data in but didn’t succeed.Instead, I pivoted the focus to 'Gender'.  After rearranging data Tableau, I was able to detect that 'Race matters less when it comes to your paycheck'.![](pics/20.png)

Later I realized it still says 'Race matters'! Hence, discrimination still exists.So, this is removed from the final visualization.


## <a name="3"></a> Intermediate Visualization Prototypes

### 1. Deceptive Claim: 'RACE MATTERS A LOT WHEN IT COMES TO YOUR PAYCHECK(White outearn minority groups)'

The visualization itself is not difficult to achieve.I put year on the X axis and Salary on the Y axis and plot lines for the groups.At the very first stage, I thought about removing Asian completely from the chart.![](pics/21.png)

Then I thought the audience would've asked the question 'Where did the Asian go'? So, I averaged these three minority groups.![](pics/22.png)

Then I realized that showing 'All Minority' with 'African American' and 'Hispanic/Latino' would have the audience suspect these must be a minority earn a higher income than these two, otherwise the line would be higher than those two. I wonder what other groups are behind this line chart?So, for the final Visualization, I removed 'African American' and 'Hispanic/Latino' too and left 'White' and 'All Minority' only.### 2. Opposite Claim: There Is No Discrimination Against Minority Groups When It Comes To Your Paycheck Per Se Because White Doesn’t Outearn All Minority GroupsCorresponding with the deceptive claim, my initial attempt for this claim would be leaving only Asian and White on the chart.![](pics/23.png)

The same question applies here. Where are the African American and Latino group?So, for the final visualization, I put all groups on the chart and used a very long and descriptive title 'There is no discrimination against minority groups when it comes to your paycheck per se because White group doesn't out earn all minority groups.'
## <a name="4"></a> Final Data Visualization
### The deceptive claim: 'RACE MATTERS A LOT WHEN IT COMES TO YOUR PAYCHECK (White out earn minority groups)'
![](pics/24.png)

### The rebuttal claim: There Is No Discrimination Against Minority Groups When It Comes To Your Paycheck Per Se Because White Doesn't Outearn All Minority Groups![](pics/25.png)



## <a name="5"></a>Road map with future features

For the opposite claim, I will collect the education background for each group and present the findings.Ideally, I would be able to create this table for each group:

![](pics/26.png)
Then I should list the  median salary for each group:
![](pics/27.png)

Then multiply these two tables
![](pics/28.png)

And finally, use the number  for each group and divide the total median pay:
![](pics/29.png)

And do the above for year 2002 to 2001.If the proportion of Asian's and White's at Bachelor’s Degree and Advanced Degree are higher than African American and Hispanic/Latino, then we can confidently see there is no racial discrimination when it comes to your paycheck. The difference is caused by education background and occupation selection which is also majorly caused by education.

## <a name="6"></a>Showcase video 
[Youtuble link](https://youtu.be/wJ1aC84UQs4)

