# Ex-04-Multivariate-Analysis

# AIM

To perform Multivariate EDA on the given data set.

# Explanation:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:

### STEP 1

Import the built libraries required to perform EDA and outlier removal.

### STEP 2

Read the given csv file

### STEP 3

Convert the file into a dataframe and get information of the data.

### STEP 4

Return the objects containing counts of unique values using (value_counts()).

### STEP 5

Plot the counts in the form of Histogram or Bar Graph.

### STEP 6

Use seaborn the bar graph comparison of data can be viewed.

### STEP 7

Find the pairwise correlation of all columns in the dataframe.corr()

### STEP 8

Save the final data set into the file

# Program:

```py
Name : K.NAGUL
Register Number : 212222230089

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_csv("/content/SuperStore.csv")
df.head()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(x=df['Row ID'],y=df['Postal Code'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("State")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(x=df['Sales'],y=df['Ship Mode'],hue=df['Category'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```

# OUTPUT:

## DF
![Screenshot 2023-05-29 221523](https://github.com/Nagul71/Ex-04-Multivariate-Analysis/assets/118661118/575a5384-b077-44df-b0fa-94f65cfa6048)



## DF.INFO

![Screenshot 2023-05-29 221528](https://github.com/Nagul71/Ex-04-Multivariate-Analysis/assets/118661118/1ef80e34-6135-4b1c-9861-325ca68ba4b6)


## NULL.SUM()

![Screenshot 2023-05-29 221533](https://github.com/Nagul71/Ex-04-Multivariate-Analysis/assets/118661118/2cc6ca6b-5845-4642-a7d7-5f447d2ee459)


## AFTER CLEANING

![Screenshot 2023-05-29 221537](https://github.com/Nagul71/Ex-04-Multivariate-Analysis/assets/118661118/b232c05d-f749-4cd6-bf1b-cda721215b5d)


## DATA TYPES

![Screenshot 2023-05-29 221543](https://github.com/Nagul71/Ex-04-Multivariate-Analysis/assets/118661118/76135a34-d20e-4fdd-a4fd-20148884cd3c)


## SCATTER PLOT

![Screenshot 2023-05-29 221554](https://github.com/Nagul71/Ex-04-Multivariate-Analysis/assets/118661118/7937009f-1074-4acf-91ec-bc3de72a7f48)


## BARPLOT

![output](g.png)
![output](h.png)
![output](i.png)
![output](j.png)

## CORRELATION COEFFICIENT INTERPRETATION

![Screenshot 2023-05-29 221657](https://github.com/Nagul71/Ex-04-Multivariate-Analysis/assets/118661118/5c0a6765-8c65-4d9f-acd5-fa88d9e00bc4)


## HEATMAP

![output](j.png)

# RESULT:

Thus we have read the given data and performed the multivariate analysis with different types of plots.
