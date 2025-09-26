# Skincare Product Clustering Analysis

## 1. Problem Statement

### What problem are we trying to solve?
This project aims to segment skincare products from the Sephora dataset based on key features such as price, rating, and number of reviews. The primary goal is to understand how different product characteristics relate to each other and identify if products can be grouped into meaningful clusters based on these features.

### Research Questions:
- Can skincare products be grouped based on price and ratings?
- Can products be grouped by number of reviews?
- What patterns emerge when clustering products based on these factors?

## 2. Understanding Clustering

### What is Clustering?
Clustering is an unsupervised machine learning technique used to group similar data points together based on shared features.

### Methods Used:
- **K-means Clustering**: Assigns each product to a cluster based on the mean of features (price, rating, reviews). The algorithm iterates to minimize the sum of squared distances from data points to their assigned cluster centers.
- **Agglomerative Clustering**: Creates clusters hierarchically by merging the closest data points or clusters, without requiring a predefined number of clusters.

Both methods help reveal insights into how products group together based on similar characteristics.

## 3. Dataset Overview

### Source
The Sephora Products and Skincare Reviews dataset from Kaggle.

### Key Features:
- `product_name`: Name of the product
- `brand`: Product brand
- `category`: Product category
- `price`: Product price in USD
- `rating`: Customer rating (1-5)
- `reviews`: Number of reviews
- `skin_type`: Target skin type
- `ingredients`: Product ingredients

### Features Used for Clustering:
Price, rating, and reviews were selected as these variables are crucial for analyzing product popularity, market positioning, and customer preferences.

## 4. Data Understanding and Visualization

### Initial Analysis (from Project 1)
Previous analysis revealed:
- Price may influence purchasing decisions but doesn't strongly affect customer ratings (1-5 scale)
- Moisturizers were the highest-rated category, followed by cleansers and sunscreens
- These insights help understand customer satisfaction and guide business optimization

### Visualization Techniques:
- Histograms and scatter plots for key variables (price, rating, reviews)
- Distribution analysis of important features

## 5. Data Preprocessing

### Steps Taken:
1. **Handling Missing Values**: 
   - Missing values in `price_usd`, `rating`, and `reviews` were filled with column medians
   - Prevents bias or distortion caused by outliers

2. **Standardization**:
   - Features were standardized using `StandardScaler` from scikit-learn
   - Essential for K-means clustering as the algorithm is sensitive to data scale

## 6. Modeling Approach

### Selected Algorithm: K-means Clustering
- **Why K-means?**: Simple and effective for handling continuous numerical data like price, rating, and reviews
- **Number of Clusters**: k=3 selected based on exploratory analysis
- **Algorithm Function**: Minimizes distance between products within each cluster, ensuring similarity in price, rating, and reviews

## 7. Clustering Analysis and Insights

### Cluster 0 Characteristics:
- **Average Price**: $55.33 USD
- **Average Rating**: 4.41
- **Average Reviews**: 355.5

### Interpretation:
Cluster 0 represents mid-range priced products with relatively high ratings and moderate review counts. These are well-regarded products that don't have the highest volume of reviews.

### Answers to Research Questions:

**Can skincare products be grouped based on price and ratings?**
- Yes, clustering shows clear grouping based on price (Cluster 1: lower-priced, Cluster 0: mid-range)
- Products also cluster by ratings (Cluster 0: 4.41, Cluster 1: 4.31, Cluster 2: 3.46)

**Can products be grouped by number of reviews?**
- Yes, the analysis reveals patterns in review distribution across clusters
- Clear patterns emerge: lower-priced products tend to have more reviews with moderate ratings, while higher-priced products have fewer reviews but higher ratings

## 8. Impact and Applications

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

*Note: This README provides a comprehensive overview of the skincare product clustering analysis project. For detailed code implementation and visualizations, please refer to the Jupyter notebook and supporting files in this repository.*
