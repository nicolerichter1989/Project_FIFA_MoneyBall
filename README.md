# FIFA_21_MoneyBall

![FIFA text](FIFA.jpeg)

## Objective

Use a Linear Regression Model to predict the Value of FIFA players.

## Data

### Data Source

The dataset was provided by Ironhack instructional staff as part of the first project for my Data Analytics course.
Dataframe: https://www.kaggle.com/ekrembayar/fifa-21-complete-player-dataset

### Shape of the Data

The datasat contains 10.125 rows and 107 columns.

### The Data
1. Case Number
2. Date
3. Year
4. Type

### Workflow

#### Load, First Review and Clean


#### Deep Dive Python


#### Deep Dive Tableau


#### EDA


#### Creating the Model


#### Evaluating the Model


### Conclusion

![Alt Text](https://media2.giphy.com/media/Qwtw3GTvRg8LxKaUet/giphy.gif?cid=ecf05e47u9osjc1n30c9g0ord37ktiu96kgidz253dc6fq49&rid=giphy.gif)

## Python Libraries
- [pandas](https://pandas.pydata.org/)
- [numpy](https://numpy.org/)
- [seaborn](https://seaborn.pydata.org/)
- [matplotlib](https://matplotlib.org/)
- [statsmodels](https://www.statsmodels.org/stable/index.html)
- [scipy](https://www.scipy.org/)
- [sklearn](https://scikit-learn.org/stable/)


OLD NOTES

To understand the data I used several functions, some might not be displayed within my jupyter file.
As I am personally not very familiar with FIFA jargon I had to spend a lot of time understanding what the different columns actually stand for.
After understanding the data I was able to chose which columns I want to use for my analysis and prediction.

### Cleaning the Data

Before cleaning FIFA 21 dataset contains 107 columns and 17,125 rows

### change format and rename
all lower string
spaces replaced with underscore
clean up €,K,M formats from value, wage, release_clause and hits columns

### drop columns
I decided to drop following columns from the dataframe
images/links: player_photo, club_logo, flag_photo
gender: only one gender represented in the data
position columns: to evaluate the value of the player I only considered the best position to be important

### set player ID as index

### add calculated columns
I decided to add 2 rankings:
- potential within best position
- potential within age

### null values
check and deal with null and zero values

After cleaning FIFA 21 dataset contains 28 columns and 17,125 rows

### The prediction model
my prediction model is greatly based on the end to end class we covered together during our Ironhack remote course

### Summary of the results

#### Quesiton 1: Does the foot make a difference in other player attributes?

I wanted to start of with an easy analysis that does not involve to many complex parameters.
My approach was to first compare all data based on the dominant foot of the players.
I split this player attribute in two rows for better readability and added calculations to see the absolute and % difference between the performance´.
The result was that there are actually attributes that seem to be higher for players that are right or left footed.
Best example would be goalkeeping with 19 points difference (23%)

#### Question 2: Who are the the 5 highest valued players within each 10 year age group?

Within questions 2 and 3 I wanted to already dig deeper in the value of the player to gain a better understanding for my prediction model.
First I wanted to know who are the 5 highest valued players within each 10 year age group.
I created age_groups and applied them on a new column.
Next I selected my data I wanted to have displayed in jupyter, followed by the grouping, sorting and resetting of the index.
What can be seen in the data is a drop in value over the years. Also from 40 years on it is only goalkeepers within a high value.
Which makes sense as most other positions retire a lot earlier. I guess because of injuries or higher physical pressure.

#### Question 3: Who are the highest valued players per best position? (most expensive team)

For the 3rd question I used the same approach but went for the highest valued player for each position.
Here I gained further insights on the few clubs that own all the most valuable players. (I actually wanted to include this in my model but ran out of time)

### Sources

Dataframe: https://www.kaggle.com/ekrembayar/fifa-21-complete-player-dataset

### List of libraries

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import scipy.stats as stats
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score
import statsmodels.api as sm
from statsmodels.formula.api import ols
from sklearn.preprocessing import Normalizer
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import OneHotEncoder, Normalizer, LabelEncoder
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import r2_score, mean_squared_error, mean_absolute_error
import math
import warnings
warnings.filterwarnings('ignore')
>>>>>>> 94181690c2f8ac34f4e7f579b14d9989f0b25c35
