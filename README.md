# Ex-09-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE

import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

df = sns.load_dataset("tips")

df.head()

df.isnull().sum()

plt.figure(figsize=(5,5))

plt.title("Data with Outliers")

df.boxplot()

plt.show()

plt.figure(figsize=(5,5))

cols = ['size','tip','total_bill']

Q1 = df[cols].quantile(0.25)

Q3 = df[cols].quantile(0.75)

IQR = Q3 - Q1

df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]

plt.title("Dataset after removing outliers")

df.boxplot()

plt.show()

sns.barplot(x=df['day'], y=df['total_bill'])

plt.title("Highest Total Bill Amount by day")

plt.show()

sns.boxplot(x=df['smoker'], y=df['tip'],hue=df['smoker'])

plt.title("Average Tip Amount given by smokers and non-smokers")

plt.show()

df["tip_percent"] = df["tip"] / df["total_bill"]

sns.barplot(x=df['size'],y=df['tip_percent'],data=df)

plt.title("Tip Percentage by Dining Party Size")

plt.show()

sns.barplot(x=df['sex'], y=df['tip'])

plt.title("Highest tips based on gender")

plt.show()

sns.barplot(x=df['day'],y=df['total_bill'])

plt.title("Total bill amount by day of the week")

plt.show()

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

sns.barplotdata=df,(x=df['size'],y=df['total_bill'])

plt.title("Average Total Bill Amount by Dining Party Size")

plt.show()

sns.violinplot(x="day", y="tip", data=df)

plt.title("Tip Amount by Day of Week")

plt.show()

sns.barplot(x="time", y="tip", data=df)

plt.title("Tip Amount by Time of Day")

plt.show()

sns.scatterplot(x="total_bill", y="tip", data=df)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()


# OUPUT
![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/e74eb3d4-d54c-4c5c-ba54-7e9b21905018)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/f7f9103e-c92f-46a7-96dc-c6260d9f2303)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/535d3e2f-04f0-4aab-a591-423d93f4b791)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/ae6198e0-2141-4155-b0f8-a63db4af2509)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/6a567c0a-876a-4cdf-a588-161f3e6b99e3)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/75546fc7-e880-4742-99e2-8dceef03bf96)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/330c2df3-7b0c-41f8-9859-a8cad3727de6)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/5d01a9b8-8657-4c24-8995-86363e4c8783)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/33130e6b-c2a4-4c7b-8dce-65918fc088ab)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/add6e70e-53cb-413d-b1dc-51cf1063e409)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/a1a07cf3-5df3-465a-ade9-7719de2a98d7)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/f5a6f39e-9087-49a3-b2ca-63c8bed6dd2c)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/80e2e66e-9642-4f1b-807c-f99823d343f6)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/cc3e9133-d526-42be-b946-7a3f76723b7d)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/ca4fc979-5a8a-40ae-8c3c-6c72eb507321)

![image](https://github.com/PavithraBarathi/Ex-08-Data-Visualization_1/assets/96919035/0df85b83-1ee5-4497-8069-00a3b6ba5143)

RESULT
Thus data visualization on complex dataset was performed successfully.
