# workshop-Multivariate-analysis

#Aim
To perform multivarient analysis on the given data set.

#Algorithm
1.Clean the data 
2.Remove outliers 
3.Apply the skew function and Kurtosis 
4.Apply Bivariate analysis on numerical and categorical 
5.Apply Multivariate analysis.

#Program
Developed by:HARIHARAN S
Register Number:212221220016

```
Bivariate analysis
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_excel("/content/FlightInformation (1).xlsx")
df
df.info()
df.isnull().sum()
df['Route']=df['Route'].fillna(df['Route'].mode()[0])
df['Total_Stops']=df['Total_Stops'].fillna(df['Total_Stops'].mode()[0])
df.isnull().sum()
df.shape
df.kurtosis()
df.skew()
sns.boxplot(x=df['Price'],y=df['Dep_Time'],data=df)
sns.scatterplot(x=df["Price"],y=df["Source"],data=df)
sns.displot(df,x="Airline",hue="Destination")
sns.barplot(x=df['Price'],y=df['Source'],data=df)

Multivariate analysis
plt.figure(figsize=(17,7))
sns.scatterplot(x=df['Price'], y=df['Source'],hue=df['Source'])
states=df.loc[:,["Dep_Time","Price"]]
states=states.groupby(by=["Dep_Time"]).sum().sort_values(by="Price")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Price",data=states)
states=df.loc[:,["Airline","Price"]]
states=states.groupby(by=["Airline"]).sum().sort_values(by="Price")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Price",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("Airline")
plt.ylabel=("Price")
plt.show()
df.corr(method='pearson')
sns.heatmap(df.corr(),annot=False)
```
#Output
Bivariate analysis

Data set

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/21.png)

Info

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/22.png)


Null values

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/23.png)

After cleaning

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/24.png)

Shape

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/25.png)

Skew

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/26.png)

Kurtosis

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/27.png)


Scatterplot for numerical and numerical

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/28.png)


Boxplot for numerical and catagorical

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/29.png)

Displot

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/30.png)

Barplot

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/31.png)

Multivariate analysis Price and Source

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/32.png)

Price and Dep_Time

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/33.png)

Price and Airline

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/34.png)

Corr()

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/36.png)

Heatmap

![](https://raw.githubusercontent.com/Hariharan5354/workshop-Multivariate-analysis/main/37.png)

#Result

Thus the Bivariate and Multivariate analysis is observerd for the given data set.
