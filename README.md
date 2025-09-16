# EX NO:2 EDA
### NAME : DHINESH M

### REG NO : 212223040040
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
df=pd.read_csv("C:\\Users\\admin\\Downloads\\Into to ds\\titanic_dataset.csv")
df
```
<img width="1363" height="550" alt="Screenshot 2025-08-22 214820" src="https://github.com/user-attachments/assets/885c5543-444e-4115-87ac-3ce1df55e8f8" />

```
df.shape
```
<img width="1347" height="90" alt="Screenshot 2025-08-22 214924" src="https://github.com/user-attachments/assets/0b97b8fd-cc3b-4672-94e9-256f2b11d788" />

```
df.set_index("PassengerId", inplace=True)
df
```
<img width="1373" height="558" alt="Screenshot 2025-08-22 215122" src="https://github.com/user-attachments/assets/22bac935-fee4-4335-a204-87efb3050ff6" />

```
df.nunique()
```
<img width="1382" height="327" alt="Screenshot 2025-08-22 215219" src="https://github.com/user-attachments/assets/8554f7b3-ed7a-459c-a4a1-61d0d0a56322" />

```
df['Survived'].value_counts()
```
<img width="1390" height="138" alt="Screenshot 2025-08-22 215322" src="https://github.com/user-attachments/assets/418aae3c-c963-41ff-99d4-ce7863e674bf" />

```
df['Sex'].value_counts()
```
<img width="1401" height="127" alt="Screenshot 2025-08-22 215458" src="https://github.com/user-attachments/assets/cf741988-a563-4acd-9720-ae780e2764c2" />

```
df.Pclass.unique()
```
<img width="1395" height="87" alt="Screenshot 2025-08-22 215602" src="https://github.com/user-attachments/assets/c471e945-e5e1-4afc-b849-a90029983e54" />

```
df.Survived.unique()
```
<img width="1393" height="80" alt="image" src="https://github.com/user-attachments/assets/b65f24bf-2049-4dc1-af28-46370869d06a" />

```
df.rename(columns={"Sex":"Gender"},inplace=True)
df
```
<img width="1552" height="626" alt="image" src="https://github.com/user-attachments/assets/e759ff21-7ea7-4615-bb57-2b2de0b6be1e" />

```
df.rename(columns={"Parch":"Pitch"},inplace=True)
df
```
<img width="1561" height="629" alt="image" src="https://github.com/user-attachments/assets/5723cbea-e116-4294-b016-3ab7a1e35faa" />

```
import seaborn as sns
sns.countplot(data=df)
```
<img width="1385" height="670" alt="image" src="https://github.com/user-attachments/assets/2b8d56b7-890d-425b-8737-49e3ee890797" />

```
sns.countplot(x="Survived",hue="Gender",data=df)
```
<img width="1387" height="643" alt="image" src="https://github.com/user-attachments/assets/9f459fc4-01e5-44fd-ad3f-73e3603ed29a" />

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
<img width="1378" height="709" alt="Screenshot 2025-08-22 220428" src="https://github.com/user-attachments/assets/b04ee248-2248-4786-9f6b-e9dfae55beec" />

```
sns.boxplot(data=df)
```
<img width="1388" height="626" alt="Screenshot 2025-08-22 220915" src="https://github.com/user-attachments/assets/47138cdc-5c77-403f-8eb3-4b79699dc016" />

```
df.boxplot(column="Survived",by="Gender")
```
<img width="1387" height="673" alt="image" src="https://github.com/user-attachments/assets/2b9e24bd-4d1c-4519-b99f-9db68d508fc4" />

```
sns.scatterplot(data=df)
```
<img width="1388" height="647" alt="Screenshot 2025-08-22 221212" src="https://github.com/user-attachments/assets/555123c6-be61-445f-b92a-5b37cd6a9f58" />

```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
<img width="1393" height="648" alt="image" src="https://github.com/user-attachments/assets/9a6bac7b-3227-4690-867b-4faf36a132cb" />

```
sns.jointplot(x='Age',y='Fare',data=df,kind="hist")
```
<img width="1239" height="758" alt="image" src="https://github.com/user-attachments/assets/99dae92e-3c15-4638-8b1f-63a07ac7e6c3" />

```
sns.jointplot(x='Age', y='Fare', data=df, kind='kde')
```
<img width="1241" height="777" alt="Screenshot 2025-08-22 221610" src="https://github.com/user-attachments/assets/b42aac42-4b88-43c3-bc7d-e889d9f8366f" />

```
sns.pairplot(data=df)
```
<img width="892" height="859" alt="Screenshot 2025-08-22 221928" src="https://github.com/user-attachments/assets/008fea79-dfe8-4ae2-93ca-0b2aee888667" />

```
corr1=df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1,annot=True)
```
<img width="1387" height="643" alt="image" src="https://github.com/user-attachments/assets/ab9c1180-2b6f-468f-bc0c-78fdecbb3466" />

```
cols = ['Survived', 'Pclass', 'Age', 'Fare']
corr1 = df[cols].corr()
sns.heatmap(corr1, annot=True)
```
<img width="1388" height="674" alt="image" src="https://github.com/user-attachments/assets/2ca66271-2fe6-4b10-bbc9-a70d11174d67" />

# RESULT
## SUMMARY:
I explored the Titanic dataset to understand what the data looks like and find patterns. I checked the size of the data, looked at missing values, and renamed some columns to make them clearer. Then I used plots to see how many people survived, how gender and passenger class affected survival, and how numerical features like Age and Fare were distributed. Boxplots and scatterplots helped me spot outliers and relationships between variables, and heatmaps showed how numerical columns were correlated. Overall, the EDA gave a good idea of the data’s structure, patterns, and relationships, which can help in further analysis or building a prediction model.

