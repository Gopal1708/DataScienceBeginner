# Statistics Project

# Read in the data set
workers <- read.csv("Workers.csv")

# Command to view data set in the new tab
View(workers)

# Structure of the data set
str(workers)

#>> 'data.frame':	500 obs. of  6 variables:
#   $ ID  : int  1 2 5 6 7 8 9 10 11 12 ...
#   $ AGE : int  25 25 25 25 25 25 25 25 25 25 ...
#   $ EDUC: int  2 5 4 4 4 5 3 5 3 1 ...
#   $ GEN : int  2 1 1 1 2 2 1 2 2 2 ...
#   $ EARN: int  7234 37413 17660 37250 20005 50602 10400 24960 4200 17002 ...
#   $ JOB : int  2 2 1 2 2 1 2 1 2 2 ...

# The workers data set consists of 500 obs of 6 variables.
# And all variables are of type "int".

# Some changes to the variables:

# Variable "GEN" consists of 2 values that is 1 or 2, which makes them categorical.
# Hence, attaching labels "Male" for 1 and "Female" for 2 and making them as factors.
workers$GEN <- factor(workers$GEN,
                      levels = c(1,2),
                      labels = c("Male", "Female"))

# Simialrly "JOB" consists of 3 values that is 1/2/3 which makes them categorical as well.
# Hence, attaching labels 1 = Public, 2 = Private and 3 = Self-Employed
workers$JOB <- factor(workers$JOB,
                      levels = c(1,2,3),
                      labels = c("Public", "Private", "Self-Employed"))

str(workers)
# Hence, now we see that the two variables ("GEN" and "JOB") are made categorical.

# >> 'data.frame':	500 obs. of  6 variables:
#   $ ID  : int  1 2 5 6 7 8 9 10 11 12 ...
#   $ AGE : int  25 25 25 25 25 25 25 25 25 25 ...
#   $ EDUC: int  2 5 4 4 4 5 3 5 3 1 ...
#   $ GEN : Factor w/ 2 levels "Male","Female": 2 1 1 1 2 2 1 2 2 2 ...
#   $ EARN: int  7234 37413 17660 37250 20005 50602 10400 24960 4200 17002 ...
#   $ JOB : Factor w/ 3 levels "Public","Private",..: 2 2 1 2 2 1 2 1 2 2 ...

# Some descriptive stats on the data set
table(workers$GEN)

#>> Male Female 
#   263    237 

# The above output shows that there are 263 males and 237 females workers
# The following is the proportion of males and females workers

prop.table(table(workers$GEN))
#>> Male Female 
#   0.526  0.474
# This figure shows that there are 53% male and 47% female workers

table(workers$EDUC, workers$JOB)

# >>      Public Private Self-Employed
#     1      0      10             2
#     2      6      34             2
#     3     27     112            26
#     4     20      83            13
#     5     24      73            11
#     6     19      27            11

# The above output shows the stats for 2 variables "EDUC" and "JOB"
# The number of workers with Education 1 are: 0 in Public Job , 10 in Private Job and 2 are Self-Employed.
# The number of workers with Education 2 are: 6 in Public Job , 34 in Private Job and 2 are Self-Employed.
# Similar explanation for rest.
# From the above table, it is evident that there are maximum number of workers in all types of JOB for workers whose EDUC value is 3.

# load libraries
library(summarytools)
# summarytools provides functions to neatly and quickly summarize numerical and categorical data.


# freq() functions states the count, percentage of each category in a variable.
# It can also state the same for numerical variable. 
freq(workers$GEN)
# Frequencies  
# workers$GEN  
# Type: Factor  
# 
#               Freq   % Valid   % Valid Cum.   % Total   % Total Cum.
# ------------ ------ --------- -------------- --------- --------------
#   Male        263     52.60          52.60     52.60          52.60
# Female        237     47.40         100.00     47.40         100.00
# <NA>            0                               0.00         100.00
# Total         500    100.00         100.00    100.00         100.00


# ctable() functions provides the cross-table of two variables of the data
# It entails the count and percemtage of each category of one variable with respect to a category of another variable.
# For eg. The output shows that there are 10 workers employed in private job having education value to be 1.
# The row states the count and percentage of people have a particular education in different jobs;
# while the column states the count and percentage of people have a particular job with different education.
ctable(workers$EDUC, workers$JOB)
# Cross-Tabulation, Row Proportions  
# EDUC * JOB  
# Data Frame: workers  
# 
# ------- ----- ------------ ------------- --------------- --------------
#         JOB       Public       Private   Self-Employed          Total
# EDUC                                                                
# 1                 0 ( 0.0%)    10 (83.3%)       2 (16.7%)    12 (100.0%)
# 2                 6 (14.3%)    34 (81.0%)       2 ( 4.8%)    42 (100.0%)
# 3                 27 (16.4%)   112 (67.9%)      26 (15.8%)   165 (100.0%)
# 4                 20 (17.2%)    83 (71.6%)      13 (11.2%)   116 (100.0%)
# 5                 24 (22.2%)    73 (67.6%)      11 (10.2%)   108 (100.0%)
# 6                 19 (33.3%)    27 (47.4%)      11 (19.3%)    57 (100.0%)
# Total             96 (19.2%)   339 (67.8%)      65 (13.0%)   500 (100.0%)
# ------- ----- ------------ ------------- --------------- --------------

# Some statistics on "EARN" variable

mean(workers$EARN)
# [1] 38497.84
# The mean or average earning variable of 500 workers is $ 38497.84 

median(workers$EARN)
# [1] 30259
# The median of earning variable is $ 30259

var(workers$EARN)
# [1] 1459842455
# Variance measures how far each number in the set is from the mean. 
# The variance of earning variable is 1459842455.
# It is very high indicating that the data points are very spread out from the mean and one another. 

sd(workers$EARN)
# [1] 38207.88
# The standard deviation of earning variable is 38207.88.
# This tells us how spread out the values of earning variable are.
# It is square-root of variance.

min(workers$EARN)
# [1] 541
# The minimum earning variable is $ 541.

max(workers$EARN)
# [1] 349879
# The maximum earning variable is $ 349879

quantile(workers$EARN)
# 0%       25%       50%       75%      100% 
# 541.00  17159.25  30259.00  45182.50 349879.00
# The quantiles states the value of earning variable at every quarters.
# The first and last value denotes the min and max of earning variable.
# The rest are the three quartile values i.e. 1st quartile - Value that corresponds to the 25% of data points
# 2nd quartile i.e. the median value (mid-point) of the data points
# 3rd quartile states the value that corresponds to the 75% of data points,

IQR(workers$EARN)
# [1] 28023.25
# Inter quartile range is the difference between the upper (3rd) quartile and lower (1st) quartile.
# It states the range of the points lying in the centre of the data points.

summary(workers$EARN)
# summary() functions states the min, max, mean and quartile values
# Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
# 541   17159   30259   38498   45183  349879 

descr(workers$EARN)
# It gives the detailed descriptive statistics of the data.

# Descriptive Statistics  
# workers$EARN  
# N: 500  
# 
#                         EARN
# ----------------- -----------
#             Mean    38497.84  
#          Std.Dev    38207.88
#              Min      541.00
#               Q1    17152.50
#           Median    30259.00
#               Q3    45205.00
#              Max   349879.00 
#              MAD    20385.75    Median absolute deviation* (mad() function)
#              IQR    28023.25
#               CV        0.99
#         Skewness        3.73
#      SE.Skewness        0.11
#         Kurtosis       20.19
#          N.Valid      500.00
#        Pct.Valid      100.00

# Creating a new variable "AgeGroup" by grouping AGE variable
workers$AgeGroup[workers$AGE < 35 ] <- "25-34"
workers$AgeGroup[workers$AGE >= 35 & workers$AGE < 45] <- "35-44"
workers$AgeGroup[workers$AGE >= 45 & workers$AGE < 55] <- "45-54"
workers$AgeGroup[workers$AGE >= 55] <- "55+"

freq(workers$AgeGroup)
# Frequencies  
# workers$AgeGroup  
# Type: Character  
# 
#               Freq   % Valid   % Valid Cum.   % Total   % Total Cum.
# ----------- ------ --------- -------------- --------- --------------
#       25-34    115     30.83          30.83     23.00          23.00
#       35-44    130     34.85          65.68     26.00          49.00
#         55+    128     34.32         100.00     25.60          74.60
#        <NA>    127                              25.40         100.00
#       Total    500    100.00         100.00    100.00         100.00

ctable(workers$JOB, workers$AgeGroup)
# Cross-Tabulation, Row Proportions  
# JOB * AgeGroup  
# Data Frame: workers  
# 
# --------------- ---------- ------------- ------------- ------------- ------------- --------------
#                 AgeGroup         25-34         35-44           55+          <NA>          Total
#             JOB                                                                                  
#           Public               14 (14.6%)    21 (21.9%)    26 (27.1%)    35 (36.5%)    96 (100.0%)
#          Private               91 (26.8%)    97 (28.6%)    75 (22.1%)    76 (22.4%)   339 (100.0%)
#    Self-Employed               10 (15.4%)    12 (18.5%)    27 (41.5%)    16 (24.6%)    65 (100.0%)
#            Total              115 (23.0%)   130 (26.0%)   128 (25.6%)   127 (25.4%)   500 (100.0%)
# --------------- ---------- ------------- ------------- ------------- ------------- --------------

tapply(workers$Age, workers$JOB, summary)

# $Public
# Length     Class      Mode 
# 96 character character 
# 
# $Private
# Length     Class      Mode 
# 339 character character 
# 
# $`Self-Employed`
# Length     Class      Mode 
# 65 character character
