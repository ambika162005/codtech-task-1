NAME:mocharla ambika INTENSHIP ID:CITS3162 NO:OF:WEEKS:8 weeks PROJECT NAME:data science PROJECT SCOPE:exploratory data analyis(eda)


Dataset: import pandas as pd
data = {
    'Student':['A','B','C','D','E','F','G','H'],
    'Study_Hours':[2,3,4,5,6,7,8,9],
    'Attendance':[70,75,80,85,90,92,95,98],
    'Marks':[50,55,60,68,72,78,85,90]
} df = pd.DataFrame(data) 2)DATAcleaning:
print("Missing Values") print(df.isnull().sum()) df.drop_duplicates(inplace=True) print("Data Cleaning Completed")
3)data analysis: print(df.describe())
#analysis commands: print("Average Marks =", df['Marks'].mean()) print("Highest Marks =", df['Marks'].max()) print("Lowest Marks =", df['Marks'].min()) print("Average Attendance =", df['Attendance'].mean())
print("Average Marks =", df['Marks'].mean()) print("Highest Marks =", df['Marks'].max()) print("Lowest Marks =", df['Marks'].min()) print("Average Attendance =", df['Attendance'].mean()) visualization 2:Marks trend: plt.figure(figsize=(8,5))
plt.bar(df['Student'],         df['Attendance']) plt.title("Attendance Analysis") plt.xlabel("Students") plt.ylabel("Attendance (%)") plt.show()
lt.figure(figsize=(6,6))
plt.pie(     df['Marks'],     labels=df['Student'],     autopct='%1.1f%%'
) plt.title("Marks Distribution") plt.show() prediction model:
from sklearn.linear_model import LinearRegression X = df[['Study_Hours']] y = df['Marks'] model = LinearRegression() model.fit(X,y) prediction = model.predict([[10]]) print("Predicted Marks for 10 Study Hours =", prediction[0]) prediction graph: plt.figure(figsize=(8,5))
plt.scatter(     df['Study_Hours'],     df['Marks']
) plt.plot(     df['Study_Hours'],     model.predict(df[['Study_Hours']])
) plt.title("Study Hours vs Marks Prediction") plt.xlabel("Study Hours") plt.ylabel("Marks") plt.show() Dashboard creation:
fig, axs = plt.subplots(2,2, figsize=(12,8))
axs[0,0].plot(df['Student'], df['Marks']) axs[0,0].set_title('Marks Trend')
axs[0,1].bar(df['Student'], df['Attendance']) axs[0,1].set_title('Attendance')
axs[1,0].hist(df['Marks']) axs[1,0].set_title('Marks Distribution')
axs[1,1].scatter(df['Study_Hours'], df['Marks']) axs[1,1].set_title('Study Hours vs Marks') plt.tight_layout() plt.show()
