# BootCampDS.py
Respository for data science boot camp

We will put the exercise for data science boot camp (in Python) going to do on April 21 

In this Exercise, you performed web scraping using Python. You used the Beautiful Soup library to parse html data and convert it into a form that can be used for analysis. You performed cleaning of the data in Python and created useful plots (box plots, bar plots, and distribution plots) to reveal interesting trends using Python's matplotlib and seaborn libraries.

Step 1 ----Import all required libraries -----


import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

import seaborn as sns

%matplotlib inline

from urllib.request import urlopen

from bs4 import BeautifulSoup

Step 2----- open the url http://www.hubertiming.com/results/2017GPTR10K and get the soup


Step 3 get the title


Step 4 get all the links on page


/results/2017GPTR
https://www.hubertiming.com/
#individual
#team
mailto:timing@hubertiming.com
#tabs-1
None
None
https://www.hubertiming.com/
https://facebook.com/hubertiming/


step 5

Find all the rows using the element tr and td

[<td>14TH</td>, <td>INTEL TEAM M</td>, <td>04:43:23</td>, <td>00:58:59 - DANIELLE CASILLAS</td>, <td>01:02:06 - RAMYA MERUVA</td>, <td>01:17:06 - PALLAVI J SHINDE</td>, <td>01:25:11 - NALINI MURARI</td>]

Step 6

Get the clean data out of it -

[14TH, INTEL TEAM M, 04:43:23, 00:58:59 - DANIELLE CASILLAS, 01:02:06 - RAMYA MERUVA, 01:17:06 - PALLAVI J SHINDE, 01:25:11 - NALINI MURARI]


Step 7

Print all the rows using regual expression


Step 8. 

create a data frame and put all the rows there


Step 9

Split the data frame using comma (,) use split function


Step 10

Clean up the data , strip [ from the first column


Step 11.

print all the header after taking out soup.find_all('th')


Step 12.

Split all the header using comma from header frame


Step 13:

Concatenate header frame and other row detail frame


step 14:

Put this header frame as header


Step 15:

Drop the row 0 from frame as header is repeated , data should look like this now

[Place	Bib	Name	Gender	City	State	Chip Time	Chip Pace	Gender Place	Age Group	Age Group Place	Time to Start	Gun Time	Team]
4	1	814	JARED WILSON	M	TIGARD	OR	00:36:21	05:51	1 of 414	M 36-45	1 of 152	00:00:03	00:36:24	]
5	2	573	NATHAN A SUSTERSIC	M	PORTLAND	OR	00:36:42	05:55	2 of 414	M 26-35	1 of 154	00:00:03	00:36:45	INTEL TEAM F]
6	3	687	FRANCISCO MAYA	M	PORTLAND	OR	00:37:44	06:05	3 of 414	M 46-55	1 of 64	00:00:04	00:37:48	]
7	4	623	PAUL MORROW	M	BEAVERTON	OR	00:38:34	06:13	4 of 414	M 36-45	2 of 152	00:00:03	00:38:37	]

Step 16

Correct the place and Team by stripping []

step 17

Also, strip ] from the Team column


DATA ANALYSIS & VISUALIZATION
Step 18

Find out the 'runner_mins' using chip_time column

Step 19

Find out the stat as below


runner_mins
count	577.000000
mean	60.035933
std	11.970623
min	36.350000
25%	51.000000
50%	59.016667
75%	67.266667
max	101.300000


Interestingly, the average chip time for all runners was ~60 mins. The fastest 10K runner finished in 36.35 mins, and the slowest runner finished in 101.30 minutes.
A boxplot is another useful tool to visualize summary statistics (maximum, minimum, medium, first quartile, third quartile, including outliers).
Step 20 

Draw a boxplot now 

from pylab import rcParams
rcParams['figure.figsize'] = 15, 5

df7.boxplot(column='runner_mins')
plt.grid(True, axis='y')
plt.ylabel('Chip Time')
plt.xticks([1], ['Runners'])


Step 21

Draw a distribution plot of runners' chip times plotted using the seaborn library. The distribution looks almost normal.


Step 22

Draw The third question deals with whether there were any performance differences between males and females of various age groups. 


Step 23

The distribution indicates that females were slower than males on average. You can use the groupby() method to compute summary statistics for males and females separately as shown below.

Step 24

The average chip time for all females and males was ~66 mins and ~58 mins, respectively. Below is a side-by-side boxplot comparison of male and female finish times.


*****. Completed . WELL DONE !  *****




