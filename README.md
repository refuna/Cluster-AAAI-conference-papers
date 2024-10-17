# Cluster-AAAI-conference-papers

# Paper Clustering for AAAI 2014 Accepted Papers

## Overview
This project aims to cluster academic papers from AAAI 2014 based on their topics and contents. Each year, numerous academic conferences present hundreds of papers, often across a variety of topics and subfields. Clustering papers can help researchers and professionals efficiently find and categorize papers based on their topics.

The dataset used for this project includes around 400 papers from the AAAI 2014 conference, which provides details such as titles, authors, keywords, and abstracts. By constructing feature vectors from the textual data and applying clustering algorithms, this project aims to group the papers into meaningful clusters, making it easier to identify common themes and topics across the published work.

## Dataset
The dataset for this project comes from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/AAAI+2014+Accepted+Papers!). It includes:
- **Title**: The title of each paper
- **Authors**: Names of the authors
- **Keywords**: Important keywords associated with the paper
- **Abstract**: A summary of the paper's content
- **Other fields**: Year, affiliations, etc.

The dataset contains 400 papers published at AAAI 2014.

## Project Goals
- **Feature Extraction**: Convert text data (e.g., titles, abstracts, keywords) into numerical feature vectors using techniques like TF-IDF.
- **Clustering**: Apply clustering algorithms such as KMeans to group the papers by their topics.
- **Analysis**: Examine the resulting clusters to observe which types of papers fall into each category and identify any dominant themes or trends.

## Methods
### 1. **Text Preprocessing**
   - Remove stop words (e.g., using the English stop words list).
   - Tokenize the text data.
   - Apply **TF-IDF** (Term Frequency-Inverse Document Frequency) to convert the abstract texts into numerical vectors for clustering.

### 2. **Clustering Algorithm**
   - **KMeans Clustering**: Used to group papers based on the extracted feature vectors.
     - **`n_clusters`**: Number of clusters (topics) was experimentally determined.
     - **`init="k-means++"`**: Smart initialization method to ensure faster convergence.
     - **`max_iter=300`**: Maximum number of iterations for KMeans.
     - **`random_state=42`**: Ensures consistent results across runs.

### 3. **Dimensionality Reduction**
   - Used **TruncatedSVD** to reduce the dimensionality of the feature space, making clustering more efficient and interpretable.

### 4. **Evaluation and Analysis**
   - After clustering, we examined the papers in each cluster to identify the major topics and themes.
   - For visual analysis, techniques like PCA were applied to plot the clusters in a 2D space.

