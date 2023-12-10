# Diabetes Dataset Analysis

# #Importing Libraries

# In[1]:

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

import warnings

#ignore warnings
warnings.filterwarnings('ignore')

#seaborn visualization set up

sns.set_style('darkgrid')

# #reading dataset

# In[2]:

data=pd.read_csv(r'C:\Users\WINDOWS 10\Documents\Meri SKILL Dataset\Project 2 - Diabetes Data-20231206T150410Z-001\Project 2 - Diabetes Data\Project 2 MeriSKILL\diabetes.csv')
data.head(10)

# In[3]: find how much column and row in dataset:

data.shape

# In[4]:Check for null values in dataset:

data.info()

# In[6]: counting of outcome:

#plotting of distribution of outcome
sns.countplot(x ='Outcome',data=data)

# In[7]: Box plot for glucose :

plt.figure(1)
plt.subplot(121),sns.displot(data['Glucose'])
plt.subplot(122),data['Glucose'].plot.box(figsize=(16,5))
plt.show

# In[8]: Box plot for pregnancies:

plt.figure(2)
plt.subplot(121),sns.displot(data['Pregnancies'])
plt.subplot(122),data['Pregnancies'].plot.box(figsize=(16,5))
plt.show

# In[9]: Box plot for BMI:

plt.figure(3)
plt.subplot(121),sns.displot(data['BMI'])
plt.subplot(122),data['BMI'].plot.box(figsize=(16,5))
plt.show

# In[10]: Box plot for Age:

plt.figure(4)
plt.subplot(121),sns.displot(data['Age'])
plt.subplot(122),data['Age'].plot.box(figsize=(16,5))
plt.show

# In[11]: Box plot for Blood Pressure:

plt.figure(5)
plt.subplot(121),sns.displot(data['BloodPressure'])
plt.subplot(122),data['BloodPressure'].plot.box(figsize=(16,5))
plt.show

# In[12]: Box plot for skinthickness:

plt.figure(6)
plt.subplot(121),sns.displot(data['SkinThickness'])
plt.subplot(122),data['SkinThickness'].plot.box(figsize=(16,5))
plt.show

# In[13]: Box plot for Insulin:

plt.figure(7)
plt.subplot(121),sns.displot(data['Insulin'])
plt.subplot(122),data['Insulin'].plot.box(figsize=(16,5))
plt.show

# In[14]: check for missing values in column data:

#check missing values
data.isnull().sum()

# PLot the heat map to check null values:
sns.heatmap(data.isnull())

# In[15]: Pair plot for paired column of dataset:

sns.pairplot(data)

# In[16]: Check correlation between all column of dataset:

#check correlation
correlation = data.corr()
print(correlation)
plt.figure(figsize=(10, 8))
sns.heatmap(correlation, annot=True, cmap='coolwarm', fmt=".2f", linewidths=.5)
plt.title("Correlation Matrix")
plt.show()

# In[17]: Simple correlation heatmap between all column of dataset: 

matrix = data.corr()
ax = plt.subplots(figsize=(9,6)),sns.heatmap(matrix,vmax=.8,square=True,cmap='coolwarm')

