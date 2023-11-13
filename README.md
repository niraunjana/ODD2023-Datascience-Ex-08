# Ex-08-Data-Visualization-

# AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM

## STEP 1
Read the given Data

## STEP 2
Clean the Data Set using Data Cleaning Process

## STEP 3
Apply Feature generation and selection techniques to all the features of the data set

## STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE
# OUTPUT
```
import pandas as pd
df=pd.read_csv("/content/Superstore.csv",encoding='unicode_escape')
df.head()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/bc3615fc-c5db-4006-8ab0-83c540fe1398)
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/fbc920cf-0663-48e7-8851-25b8222ec6ef)


#DATA VISUALIZATION USING SEABORN :
```
import seaborn as sns
from matplotlib import pyplot as plt
```
#LINE PLOT:
# Line plot - Sales trends over time (using Order Date)
```
plt.figure(figsize=(9, 6))
sns.lineplot(x='Order Date', y='Sales', data=df)
plt.title('Sales Trends Over Time')
plt.xticks(rotation=45)
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/de4bd1b5-4d25-41e2-a07e-422c00e14af6)


#SCATTERPLOT:
# Scatter plot - Comparing Sales and Profit based on Ship Mode
```
plt.figure(figsize=(10, 7))
sns.scatterplot(x='Ship Mode', y='Sales', hue='Category', data=df)
plt.title('Sales and Profit Comparison based on Ship Mode')
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/7e7a46f4-b629-42ae-91df-4b90898edc63)


#BOXPLOT:
# Box plot - Analyzing the distribution of Sales in different Categories
```
plt.figure(figsize=(9, 6))
sns.boxplot(x='Category', y='Sales', data=df)
plt.title('Distribution of Sales in different Categories')
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/563e087d-d52a-410e-bc69-1ed99b75abc3)


#VIOLIN PLOT:
# Violin plot - Examining the distribution of Sales in different Sub-Categories
```
plt.figure(figsize=(9, 6))
sns.violinplot(x='Sub-Category', y='Sales', data=df)
plt.title('Distribution of Sales in different Sub-Categories')
plt.xticks(rotation=45)
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/fdb5f2eb-9a22-4ad5-ab63-baedf490554a)


#BARPLOT
# Bar plot - Comparing Sales across different Regions
```
plt.figure(figsize=(9, 6))
sns.barplot(x='Region', y='Sales', data=df, hue='Segment')
plt.title('Sales Comparison across Regions by Segment')
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/36b6d831-8372-4312-96b8-6eeb16338e8a)


#POINTPLOT
# Point plot - Comparing Sales for a specific Category
```
plt.figure(figsize=(10, 6))
sns.pointplot(x='Category', y='Sales', data=df)
plt.title('Comparison of Sales for each Category')
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/546d9f84-14a1-42c0-b13e-37cb038c4d8e)


#COUNT PLOT
# Count plot - Count of orders in each Category
```
plt.figure(figsize=(10, 6))
sns.countplot(x='Category', data=df, hue='Region')
plt.title('Count of Orders in each Category by Region')
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/b33da1ef-407a-44a1-aea3-0408c36744da)


#HISTOGRAM
# Histogram - Ship Mode
```
plt.figure(figsize=(10, 6))
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/70d7f2f6-04cf-4b41-aa7e-0c4baf35fa91)


#KDE PLOT
# KDE plot - Kernel Density Estimate for Sales
```
plt.figure(figsize=(10, 6))
sns.kdeplot(x='Sales', data=df, hue='Category', fill=True)
plt.title('Kernel Density Estimate for Profit by Category')
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/3a71211c-1a21-47b0-9388-170a3a621389)


#DATA VISUALIZATION USING MATPLOTLIB :
PLOT
# PLOT
```
plt.plot(df['Category'], df['Sales'])
plt.title('Line Plot of Sales by Category')
plt.xlabel('Category')
plt.ylabel('Sales')
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/c6c1934b-9192-455c-ae9c-eb21048ac85a)


#PIECHART:
# PIE CHART - Ship Mode Sales
```
df_ship_mode = df.groupby('Ship Mode')['Sales'].sum()
plt.figure(figsize=(8, 8))
plt.pie(df_ship_mode, labels=df_ship_mode.index, autopct='%0.0f%%', startangle=90)
plt.title('Sales Distribution by Ship Mode')
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/41e683e8-0182-4c04-a6fe-3f8e2f24c317)


#HISTOGRAM:
# HISTOGRAM - Sub-Category Sales
```
plt.figure(figsize=(10, 6))
plt.hist(df['Sub-Category'], facecolor="peru", edgecolor="blue", bins=10)
plt.title('Histogram of Sub-Category Sales')
plt.xlabel('Sub-Category')
plt.ylabel('Frequency')
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/89d12cd1-90bd-4532-aab7-cc817c1a8e7d)


#BARGRAPH:
# BAR GRAPH - Sales by Category
```
plt.bar(df['Category'], df['Sales'])
plt.title('Bar Graph of Sales by Category')
plt.xlabel('Category')
plt.ylabel('Sales')
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/c069e800-4bc4-4025-869d-9ec33e81286b)


#SCATTERPLOT:
# SCATTER PLOT - Region vs Profit
```
plt.scatter(df['Region'], df['Sales'], c="blue")
plt.title('Scatter Plot of Region vs Sales')
plt.xlabel('Region')
plt.ylabel('Sales')
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/48052c82-8c98-423a-8f29-275b57f27c17)


#BOXPLOT:
# BOX PLOT - Sales
```
plt.boxplot(df['Sales'])
plt.title('Box Plot of Sales')
plt.ylabel('Sales')
plt.show()
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/1abfd04a-76fd-48a4-96ee-c86493d029d3)


#HEATMAP:
# HEATMAP
```
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
```
![image](https://github.com/niraunjana/ODD2023-Datascience-Ex-08/assets/119395610/67602489-3df4-4560-b85f-fa7bd32ccdae)


### RESULT:
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
