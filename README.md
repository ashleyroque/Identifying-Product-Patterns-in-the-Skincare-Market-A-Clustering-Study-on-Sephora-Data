# Market Segmentation of Sephora Skincare Products Using K-Means Clustering
## 📜 Project Overview
The goal of this project is to segment skincare products from the Sephora dataset based on key features such as price, rating, and number of reviews. The primary goal is to understand how different product characteristics relate to each other and identify if products can be grouped into meaningful clusters based on these features.

## 📌 Problem Statement 
### With this project, I am looking to answer these questions:

*1. Can skincare products be grouped based on price and ratings?*

*2. Can products be grouped by number of reviews?* 

*3. What patterns emerge when clustering products based on these factors?* 

## 📊 Introducing the Data   
The dataset used is sourced from [Kaggle: Instagram Data](https://www.kaggle.com/datasets/propriyam/instagram-data).  

### Key Features:
- `product_name`: Name of the product
- `brand`: Product brand
- `category`: Product category
- `price`: Product price in USD
- `rating`: Customer rating (1-5)
- `reviews`: Number of reviews
- `skin_type`: Target skin type
- `ingredients`: Product ingredients
  
The features I used for clustering were primarily price, rating, and reviews, as these variables are crucial for analyzing product popularity, market positioning, and customer preferences. By clustering products based on these attributes, we can uncover patterns and group similar products.


## 💡 What is Clustering and How Does it Work? 
### What is Clustering?
Clustering is an unsupervised machine learning technique used to group similar data points together based on shared features.

#### 💬 Example visualization of clustering 
<img width="945" height="448" alt="Screenshot 2025-09-30 110526" src="https://github.com/user-attachments/assets/546ed4de-31fe-4935-b343-cd9983fb0094" />

🔗 Sourced from: https://developers.google.com/machine-learning/clustering/overview 


### Methods Used:
- **K-means Clustering**: This method assigns each product to a cluster based on the mean of features (e.g., price, rating, reviews). The algorithm iterates to minimize the sum of squared distances from data points to their assigned cluster centers.
- **Agglomerative Clustering**: Creates clusters hierarchically by merging the closest data points or clusters, without requiring a predefined number of clusters.
  
Both methods help reveal insights into how products group together based on similar characteristics.

## 🔧Data Preprocessing
Preprocessing is a crucial step in the OSEMN pipeline, as it involves the “cleaning” of data before any further processing. This step ensures that the errors are addressed and missing or inaccurate values are removed or corrected, providing a solid foundation for meaningful insights.

### Here are the pre-processing steps I took to prepare the data for analysis:

1. **Handling Missing Values**: 
   - Missing values in `price_usd`, `rating`, and `reviews` were filled with column medians
   - Prevents bias or distortion caused by outliers

2. **Standardization**:
   - Features were standardized using `StandardScaler` from scikit-learn
   - Essential for K-means clustering as the algorithm is sensitive to data scale

## 💻 Data Understanding and Visualization

### Initial Analysis (from previous project)
Previous analysis revealed:
- Price may influence purchasing decisions but doesn't strongly affect customer ratings (1-5 scale)
- Moisturizers were the highest-rated category, followed by cleansers and sunscreens
- These insights help understand customer satisfaction and guide business optimization

### Visualization Techniques:
- Histograms and scatter plots for key variables (price, rating, reviews)
- Distribution analysis of important features
  <img width="503" height="478" alt="Screenshot 2025-09-25 105749" src="https://github.com/user-attachments/assets/04ea4551-a9e5-456e-a29b-cd7fd8e9fff0" />
<img width="577" height="358" alt="Screenshot 2025-09-25 110008" src="https://github.com/user-attachments/assets/8d7ff151-d8d3-4c0d-850e-f6729a781adc" />



## 6. Modeling Approach
<img width="613" height="426" alt="Screenshot 2025-09-26 161301" src="https://github.com/user-attachments/assets/5a8b4845-143a-43cf-9fac-d754f4c4627c" />

### Selected Algorithm: K-means Clustering
- **Why K-means?**: Simple and effective for handling continuous numerical data like price, rating, and reviews
- **Number of Clusters**: k=3 selected based on exploratory analysis
- **Algorithm Function**: Minimizes distance between products within each cluster, ensuring similarity in price, rating, and reviews

## 7. Clustering Analysis and Insights :) here
After running the K-means algorithm, I analyzed the resulting clusters to I identify the following: 

### Cluster 0 Characteristics:
- **Average Price**: $55.33 USD
- **Average Rating**: 4.41
- **Average Reviews**: 355.5

### Interpretation:
Cluster 0 contains products that tend to be mid-range priced, with relatively high ratings (around 4.4), and an average number of reviews. These products could be seen as moderate-priced items that are generally well-regarded by customers but don't have the highest volume of reviews compared to other clusters.

### Answers to Research Questions:

**Can skincare products be grouped based on price and ratings?**
- Yes, clustering shows clear grouping based on price (Cluster 1: lower-priced, Cluster 0: mid-range)
- This suggests that price is a significant factor in how the products group together.

**Can products be grouped by number of reviews?**
- Yes, the average ratings for each cluster show that products tend to cluster based on their ratings as well. Cluster 0 has high ratings (around 4.41), Cluster 1 has slightly lower ratings (4.31), and Cluster 2 has even lower ratings (3.46). This indicates that products with similar ratings tend to cluster together.
- The clusters formed reflect how products can be grouped based on price, ratings, and reviews. The analysis reveals that there are clear patterns, such as lower-priced products having more reviews and moderate ratings, while higher-priced products tend to have a smaller number of reviews but higher ratings.


## 8. Impact and Applications
### This project could impact both consumers and businesses and here is how: 
### Consumer Impact:
- Helps consumers make more informed purchasing decisions by understanding product clusters
- Enables better comparison of products within similar price and rating ranges

### Business Impact:
- Identifies market gaps and consumer segments
- Supports targeted product offerings and marketing strategies
- Informs product development and pricing strategies

### Ethical Considerations:
- Potential bias if certain product categories (e.g., luxury items) are overrepresented
- Need to account for diversity in product offerings to avoid reinforcing market inequalities

## 9. References
- [IBM K-means Clustering](https://www.ibm.com/topics/k-means-clustering)
- [Domino AI: K-means in Python](https://domino.ai/blog/getting-started-with-k-means-clustering-in-python)
- [W3Schools Python ML K-means](https://www.w3schools.com/python/python_ml_k-means.asp)
- [Neptune AI K-means Blog](https://neptune.ai/blog/k-means-clustering)

---


