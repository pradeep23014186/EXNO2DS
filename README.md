# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt = pd.read_csv("titanic_dataset.csv")
print(dt.head())
```
![image](https://github.com/user-attachments/assets/cc4be07b-93a7-4143-9640-69284f879e1c)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/306f0a76-b9c3-4a35-8270-ee10fbdd058e)

```
print(f"Number of rows: {dt.shape[0]}")
print(f"Number of columns: {dt.shape[1]}")
```
![image](https://github.com/user-attachments/assets/5de4ca3f-0f92-4173-bed0-14938fc3c44c)

```
dt.set_index('PassengerId', inplace=True)
print(dt.describe())
```
![image](https://github.com/user-attachments/assets/d59851f0-b6d2-4a61-a2db-58824570ff92)

```
print(dt['Sex'].value_counts())
print(dt['Embarked'].value_counts())
```
![image](https://github.com/user-attachments/assets/c7d66d5c-3cad-4035-ba38-3694e6f3c01d)
```
plt.figure(figsize=(6, 4))
sns.countplot(x='Survived', data=dt, palette='coolwarm')
plt.title("Survival Count")
plt.show()
```
![image](https://github.com/user-attachments/assets/8982c201-2819-433e-acd3-b20284c6f578)
```
print("Unique values in 'Pclass':", dt['Pclass'].unique()
```
![image](https://github.com/user-attachments/assets/b662194a-2e51-42be-a13c-14874efa6719)
```
dt.rename(columns={'Sex': 'Gender'}, inplace=True)
print(dt.head())
```
![image](https://github.com/user-attachments/assets/f6b3bbd5-89a2-4667-92a8-35e02760252b)
```
sns.catplot(x="Pclass", hue="Survived", data=dt, kind="count", palette="muted")
plt.title("Survival Count by Passenger Class")
plt.show()
```
![image](https://github.com/user-attachments/assets/72c0b9f6-4ee5-4e88-bcb1-ead3b45448a3)
```
fig, ax1 = plt.subplots(figsize=(8,5))
graph = sns.countplot(x="Gender", hue="Survived", data=dt, palette="pastel")
graph.set_xticklabels(graph.get_xticklabels())
for p in graph.patches:
    height = p.get_height()
    graph.text(p.get_x()+p.get_width()/2, height + 20.8,height ,ha="left")
```
![image](https://github.com/user-attachments/assets/b581f944-c5b8-4102-b51a-1ec4f960ee08)
```
plt.figure(figsize=(8, 5))
sns.boxplot(x='Survived', y='Age', data=dt, palette='coolwarm')
plt.title("Age Distribution by Survival")
plt.show()
```
![image](https://github.com/user-attachments/assets/af6907ba-fbe1-4f31-b355-b94062a80016)
```
plt.figure(figsize=(10, 6))
sns.boxplot(x='Pclass', y='Age', hue='Gender', data=dt, palette='Set2')
plt.title("Age Distribution by Passenger Class and Gender")
plt.show()
```
![image](https://github.com/user-attachments/assets/26e1b4b7-d823-4538-9210-d265a81e32b5)
```
sns.catplot(x='Pclass', hue='Survived', col='Gender', data=dt, kind='count', palette='coolwarm')
plt.show()
```
![image](https://github.com/user-attachments/assets/efbf73ee-84dc-4e52-bbf6-fffeb9d35331)
```
plt.figure(figsize=(10, 6))
sns.heatmap(dt.corr(), annot=True, cmap='coolwarm', linewidths=0.5)
plt.title("Feature Correlation Heatmap")
plt.show()
```
![image](https://github.com/user-attachments/assets/fd49afcc-1b99-4423-9bfd-cb7b6f0e608d)
```
sns.pairplot(dt, hue='Survived', palette='coolwarm')
plt.show()
```
![image](https://github.com/user-attachments/assets/7c77dfa7-48a5-4734-a207-05ad0bf42381)





# RESULT
        Code are sucessfully executed.
