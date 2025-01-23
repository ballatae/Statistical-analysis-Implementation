# Statistical-analysis-Implementation

## Data Exploration and Visualization
The dataset that was given to analyse represents demographic and employment-related infor-
mation from census data, with 15 features such as ‘Age’, ‘Education’, ‘Occupation’, ‘Hours per
Week’, etc.
Firstly, the dataset went through an in-depth cleaning process to address inconsistencies, handle
missing values and prepare it for further analysis and modelling. Each step was based on logical
assumptions and decisions that were relevant to the area in order to protect the dataset’s integrity
and keep useful data.
1. Identifying Missing and Placeholder Values: Unknown (NaN) numbers and empty strings,
“?”, “Unknown”, and “null” were looked for in each column. The reason for this is that these
placeholder records show that information is missing and needs to be filled in before the data
can be used. As a result, missing or default values were regularly found in columns such as
Native Country, Workclass, and Occupation
2. Handling Missing Values: A method called “logical imputation” was used to deal with
missing values. For instance, when there were blanks in the Workclass and Occupation
fields, the most common value (mode) within the groups set by the Education variable was
used to fill them in. This method made sure that there were logical connections between a
person’s educational past and their job or work class. In the same way, any blanks in the
Native Country column were filled in with the country that was most often linked to each
position. This plan kept important variable interactions while reducing the effect of missing
values.
3. Standardizing and Cleaning Strings: Categorical sections like Workclass, Education
and Household Role were cleaned up to get rid of extra spaces and mistakes. This step
made sure that all string-based fields had the same formatting. Furthermore, the Education
column was changed to a number value, Education Num, to create a standard format for
further research. These changes made sure that information was consistent which made it
easier to model and analyse.
4. Addressing Outliers: Numerical columns like Capital Gain, Capital Loss and
Hours Per Week were analyzed for extreme values using interquartile range thresholds.
Capital Gain and Capital Loss had a lot of 0-values, so there was done filtering that sepa-
rated the non-zero values because they contained important information about outliers. The
number of outliers was limited so that they would not have a big effect on the statistical
analysis or model performance.
5. Addressing Low-Work-Hour Records: Individuals who worked less than 10 hours per
week had their records looked at separately to see how their pay was spread out. Visual
analysis showed that most of these people made less than 50K, which supports a logical
pattern. These records were kept because contained valid data points. This step made sure
that valid observations that did not happen very often were not thrown out by accident.


After the data cleaning phase was done some scripts were run in order to visualize the data and
give back important insights.

-  The study of the dataset shows clear patterns in how income is distributed. An important
number of people make less than 50K a year, and those who make more tend to work longer
hours. People with higher incomes usually work slightly more than 40 hours per week, while
people with lower incomes usually work less. Also, age plays a part; the best years to make
money based on the data are between the ages of 30 and 50. Younger and older people are
less likely to be big earners.
-  Workclass has a big effect on how much money people make. The private industry makes up
most of the data set, followed by self-employed people and government jobs. People who
work for the government or are self-employed tend to work more hours, which means they
make more money. The study also shows that managerial and professional jobs, especially
”Exec-managerial” and ”Prof-specialty” are strongly linked to better salaries. The uneven
division of gender supports this even more. Men are more likely to work in high-paying jobs,
while women are more likely to work as ”handler-cleaners” and ”private house servants”.
-  Going to school is a big way to make money based on the data. Having more education,
like a Master’s degree, a Doctorate, or professional certifications, is highly linked to making
more money. People with less schooling, like those who only finished high school, are more
likely to be in the ”less than 50K” income range. Another thing that capital gains data shows
is that people with more schooling are more likely to have investments or other ways to make
money.
-  Income differences are also shown by marital status. Most people who are married make
more than $50,000 a year and work longer hours. This is especially true for people whose
partner is not in the military. High earners, on the other hand, are less likely to be separated
or never married. A study of work hours in high-income jobs reveals that marital status
affects work habits, with married people working more hours than most other groups. The
pattern here is the same as the trend seen across all jobs.
-  Race affects pay as well. People who identify as “White” and “Asian-Pacific-Islander” are
more likely to make over 50K than people of other races. A more detailed look at race and
income in high-income jobs shows that the number of people of different races in each role
changes a lot. This shows how race and work affect income levels in a complex way.
-  A look at high-income jobs was done to see how marriage status, race and work hours affect
income levels. High earners in the highest-paying job ”Executive-managerial”, were seen to
work longer hours. Married people were more likely to be executives, and their household
roles often aligned with higher earnings. Also, there were differences in the number of
people of different races working in high-income jobs, with some races being more common
in certain roles.
-  The education levels and work hours of high earners were also examined. People with ad-
vanced degrees who make a lot of money tend to work longer hours. This shows that educa-
tion, work ethic and pay are all strongly linked. People with more education are more likely
to work in managerial and professional positions which regularly had a higher percentage of
people making over 50K.

All of these studies show that differences in income are caused by a mix of factors, including
race, gender, marriage status, education level, and job. A high income is often caused by having a
lot of schooling, being a manager, working longer hours, and being married. On the other hand, it
is harder for people in lower-paying jobs or with less schooling to make beyond the 50K income
threshold. The results lay the groundwork for learning more about social differences and how they
affect policymaking and planning the workforce.

The logistic regression model was used to predict if an individual’s annual income surpasses
50K based on specific parameters. The model’s performance was assessed using important mea-
sures such as accuracy, precision, recall, F1-score, and ROC-AUC score.

![image](https://github.com/user-attachments/assets/f738f93b-6a9b-46ae-9391-269dea35143c)

As seen by the figure above the model achieved an accuracy of 79% =, indicating that it correctly 
predicted the income category in most cases. For individuals earning more than 50K, pre-
cision was 62%, and recall was 36%. This highlights that while the model was relatively precise
in identifying higher earners, as seen it missed a significant portion of them. For individuals earning 
less than 50K, precision and recall were significantly higher at 82% and 93%, respectively,
showing strong performance in identifying lower earners.
The F1-score, which balances precision and recall, was 46% for the above 50K category and
87% for the less or equal to 50K category. This shows that the model is more effective at identifying
individuals in the lower-income group.
The confusion matrix showed that the model did a great job of predicting the less or equal
to 50K category but struggled with the larger than 50K category, as evidenced by a higher false
earners were mistakenly labelled as high earners.

![image](https://github.com/user-attachments/assets/de873f39-5ead-4d0a-bba4-0c90987bdc2b)

The area under the curve (AUC) of the ROC curve was 0.81, which means that sensitivity and
specificity were both good. This number shows that the model can tell the difference between the
two types of income pretty well.
The model does a good job of finding people who make less than $50,000, but is not so good
at finding people who make more than $50,000. This might be because the information is not
balanced or because the feature distributions overlap. For improvement could involve engineering,
balancing the dataset, or employing more sophisticated algorithms.

![image](https://github.com/user-attachments/assets/31ec5346-8e83-4ccf-b810-4cb77ae5032f)

