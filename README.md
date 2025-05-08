# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
 ```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
```
```
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
```
```
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/9c827f71-509a-4999-bd12-2ea2048130b8)
```
df = sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/42d646ad-99e6-4cb5-b70b-9075c5ca083b)
```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")

```
![image](https://github.com/user-attachments/assets/bc505503-bf1e-49e6-a11f-2e2fa3bbf8b7)
```
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```
![image](https://github.com/user-attachments/assets/ca8984c9-9bd5-4e3d-8dcb-598be8f70f36)
```
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/c1b44831-e73f-4ba9-b385-a3d8a90aacae)
```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![image](https://github.com/user-attachments/assets/e6569893-5110-4bcb-8527-e9de9173600b)
```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![image](https://github.com/user-attachments/assets/cb5a48dd-fb47-4a0f-8760-647180f4058c)
```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![image](https://github.com/user-attachments/assets/44179f8e-0fdf-448e-8473-3948d048dc67)
```
tit=pd.read_csv("/content/titanic_dataset (1).csv")
tit
```
![image](https://github.com/user-attachments/assets/12b9455e-bbd0-4ec6-b34e-22f616b7608f)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/user-attachments/assets/b3ca24d4-7438-4569-a64b-89e0627666d7)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/user-attachments/assets/3053cd37-2eee-45d7-9f4b-589dd7a607ec)
```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/user-attachments/assets/fdd2548e-6bcd-44c7-a55b-ddadc945e8dc)
```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![image](https://github.com/user-attachments/assets/c10d0e4f-1f62-4db0-94fc-c5c60ca87f93)

```
sns.histplot(data = num_var, kde = True)
```
![image](https://github.com/user-attachments/assets/3a408ed4-e1a1-4ed7-ad3e-3b3d46f0ec7a)
```
df=pd.read_csv("/content/titanic_dataset (1).csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
 ![image](https://github.com/user-attachments/assets/d5376c92-78a3-4cf6-b6a7-3d9bf1c73b13)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/9fb4fe36-12d3-46a4-9256-71456abd0b3f)
```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![image](https://github.com/user-attachments/assets/5ed7c2c6-427a-4451-821c-25c7132228c1)
```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/7f96068e-c6ff-438f-88bc-072d98f0d737)

```
mart=pd.read_csv("/content/titanic_dataset (1).csv")
mart
```
![image](https://github.com/user-attachments/assets/86b793f0-9c67-429a-b672-58cd945447a7)
```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```
![image](https://github.com/user-attachments/assets/c3f1cfb0-a52d-4deb-8f5d-9ae300c07814)
```
sns.kdeplot(data=mart,x='PassengerId')
```
![image](https://github.com/user-attachments/assets/0511d735-0a5f-4db5-8161-8d31e4965e4c)
```
sns.kdeplot(data=mart,x='Age')
```
![image](https://github.com/user-attachments/assets/aac1c7af-3ecd-4d85-90e0-9c5641f443ce)
```
sns.kdeplot(data=mart)
```
![image](https://github.com/user-attachments/assets/ee84e797-da24-41cd-9d5e-d9558d4b6ded)
```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![image](https://github.com/user-attachments/assets/5d4de72e-88b2-4a69-af9d-b23a06ccdc55)
```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![image](https://github.com/user-attachments/assets/2aeeeccb-48cc-44fd-bade-1d464bcc5c5e)
```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/61082f25-cf83-446c-9b75-76696c7fc90b)
```
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/cbbfa8f3-28f9-4d7b-b557-b5528de93e85)
# Result:
 Thus the program is executed successfully.
