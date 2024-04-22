# EX-08 Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program 
 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: PRADEEP V 
RegisterNumber: 2122223240119 
*/
```

```
# Implementation-of-K-Means-Clustering-for-Customer-Segmentation
### NAME : S.Sanjay Balaji
### REGISTER NUMBER : 212223240149
## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program

## Program:

/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: S.Sanjay Balaji
RegisterNumber:  212223240149
*/


import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("C:/Users/admin/Downloads/Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
    kmeans=KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No.of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"],c="red", label="cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"],c="blue", label="cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"],c="green", label="cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"],c="magenta", label="cluster4") 
plt.legend()
plt.title("Customer Segments")






```

## Output:
![image](https://github.com/velupradeep/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150329341/439e81f1-6c01-4d7f-8e5b-d035f767fef8)
![image](https://github.com/velupradeep/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150329341/5757ea60-3f3a-4d77-b104-8e812469080e)
![image](https://github.com/velupradeep/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150329341/0c14a581-1744-48a7-8d9d-090be96e3301)
![image](https://github.com/velupradeep/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150329341/505b2f6f-bfd0-47de-b1c5-66093209cc00)
![image](https://github.com/velupradeep/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150329341/7035be24-fdaf-4250-b8a4-e5332edc2820)
![image](https://github.com/velupradeep/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150329341/be041ebb-4ca3-4bba-b9b9-807683e19d4c)
![image](https://github.com/velupradeep/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150329341/445088f0-b905-423d-9cef-2109b87234e6)









## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
