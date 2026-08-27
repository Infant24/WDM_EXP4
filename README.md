### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
# Visitor segmentation based on characteristics
# read the data

import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

df = pd.read_csv("clustervisitor.csv")

X = df[['Age']]

kmeans = KMeans(n_clusters=3, random_state=42)

df['Cluster'] = kmeans.fit_predict(X)

print(df)

for i in range(3):
    print(f"\nCluster {i}")
    print(df[df['Cluster'] == i])

# Perform segmentation based on characteristics (e.g., age groups)


```
### Output:
<img width="434" height="527" alt="image" src="https://github.com/user-attachments/assets/326191b0-5ce9-4833-a816-eeb5fd785f6d" />
<img width="419" height="231" alt="image" src="https://github.com/user-attachments/assets/8e63181f-4096-4e50-a5c5-a9d9104d4a97" />
<img width="421" height="217" alt="image" src="https://github.com/user-attachments/assets/81d58686-68d3-444b-a667-c413859b09d7" />
<img width="400" height="196" alt="image" src="https://github.com/user-attachments/assets/b028c143-c878-48b1-862e-b9dcd46acd7b" />

### Visualization:
```python
# Create a list to store counts of visitors in each age group
import matplotlib.pyplot as plt

plt.figure(figsize=(8,5))

for i in range(3):
    cluster = df[df['Cluster'] == i]
    plt.scatter(cluster['Age'], cluster['Cluster'], label=f'Cluster {i}')

plt.scatter(
    kmeans.cluster_centers_,
    range(3),
    color='red',
    marker='X',
    s=200,
    label='Centroids'
)

plt.xlabel("Age")
plt.ylabel("Cluster")
plt.title("Visitor Segmentation using K-Means")
plt.legend()
plt.grid(True)
plt.show()

# Count visitors in each age group

    
# Define age group labels and plot a bar chart


plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:

<img width="692" height="448" alt="image" src="https://github.com/user-attachments/assets/70afc6b3-34d6-4f72-9fa8-158641b54065" />

### Result:

Thus the code has been executed successfully.
