# Unlabeled Image Clustering Using EfficientNet and Dimensionality Reduction Techniques

## Project Overview <a name="overview"></a>

This project demonstrates the powerful capabilities of modern image classification models, such as EfficientNet, to extract meaningful features from unlabeled image data and use them for clustering. By leveraging feature extraction and clustering techniques, we can group images with similar characteristics, even without having predefined labels. We further visualize the resulting clusters in 2D and 3D spaces using dimensionality reduction methods like PCA (Principal Component Analysis) and t-SNE (t-distributed Stochastic Neighbor Embedding).

## Table of Contents
* [Project Overview](#overview)
* [Dataset](#data)
* [How EfficientNet Works](#en)
* [Principal Component Analysis](#pca)
* [t-Distributed Stochastic Neighbor Embedding (t-SNE)](#tsne)
* [Setup and Usage](#use)
* [Feature Extraction and Clustering](#fec)
* [References and Interesting Links](#ref)

## Dataset <a name="data"></a>

Link for the dataset I used is in the references below [1]

## How EfficientNet Works <a name="en"></a>

EfficientNet is a family of convolutional neural networks that scales up in a more efficient way than traditional architectures. It introduces a compound scaling method, which uniformly scales network depth, width, and resolution using a simple yet highly effective principle: balancing all three dimensions instead of arbitrarily scaling one. This leads to superior performance with fewer parameters.

EfficientNet achieves state-of-the-art results on multiple image classification benchmarks while maintaining efficiency in terms of computational cost. It is ideal for feature extraction because of its ability to learn deep, meaningful representations of images in a scalable way.

**Why EfficientNet?**
* Efficiency: Fewer parameters and operations than similar-performing models.
* Scalability: Scales depth, width and resultion uniformly.
* Performance: Delivers better results across a wide variety of image recognition tasks.

## Principal Component Analysis (PCA) <a name="pca"></a>
Principal Component Analysis (PCA) is a widely used technique for reducing the dimensionality of data, especially when the original data has a large number of features. PCA works by finding the directions (principal components) in which the data varies the most and projecting the data onto these new directions.

**Explained Variance**

The "explained variance" refers to how much information (or variance) each principal component captures from the original data. The goal is to reduce the number of dimensions while preserving as much variance as possible. The first principal component captures the largest variance, the second captures the second largest, and so on.

![image](https://github.com/user-attachments/assets/1031715d-51e4-4168-9b77-7f40d3ef06b0)


**Cumulative Explained Variance**

Cumulative explained variance shows the total variance explained by the first few principal components. It is important because it tells us how much information is retained as we reduce the number of dimensions. For instance, we might retain the first two or three principal components if they explain a significant portion of the variance (e.g., 95%).

![image](https://github.com/user-attachments/assets/c9321d45-b0b6-4f55-88ca-b9e9520a888e)


PCA allows us to compress data and visualize clusters in 2D or 3D while keeping most of the essential structure.

![image](https://github.com/user-attachments/assets/94598e0e-8718-4441-8178-6d3fd09f1ab3)

![image](https://github.com/user-attachments/assets/6034bb2c-fccc-4a26-91d5-1d6ccb66c302)



## t-Distributed Stochastic Neighbor Embedding (t-SNE) <a name="tsne"></a>

t-Distributed Stochastic Neighbor Embedding (t-SNE) is a powerful non-linear dimensionality reduction technique specifically designed for high-dimensional data visualization. Unlike PCA, which focuses on preserving the global structure, t-SNE excels at capturing the local relationships between data points.

![image](https://github.com/user-attachments/assets/194529f0-f311-43f2-bf2e-9344ecc0346d)


**Why t-SNE?**

* Preserves local structure: t-SNE ensures that similar data points stay close to each other in the reduced dimension.
* Great for visualization: t-SNE is well-suited for creating 2D and 3D plots of complex, high-dimensional datasets, such as image features extracted by a deep learning model.

In this project, we used t-SNE to project the extracted features into a low-dimensional space for cluster visualization, enabling us to observe how well the model has grouped similar images together.

## Setup and Usage <a name="use"></a>

To set up this project locally, follow these steps:

### 1. Clone the repository

```bash
git clone https://github.com/peksikeksi/uic-efficientnet.git
cd uic-efficientnet
```

### 2. Install required dependencies
Install the necessary packages listed in the `requirements.txt` using `pip`:

```bash
pip install -r requirements.txt
```

## Feature Extraction and Clustering <a name="fec"></a>
1. Feature Extraction: We use EfficientNet as a feature extractor to obtain high-level representations of images. The model is pre-trained on ImageNet and used to transform each image into a feature vector.

2. Clustering: After extracting the features, KMeans is applied to group similar images into clusters. We experimented with different numbers of clusters to find the best grouping.



### Visualization
We use PCA to project the high-dimensional feature vectors into a lower-dimensional space (2D or 3D), which allows us to visualize the clusters. t-SNE is also used to capture the local structure of the data and provide an intuitive 2D visualization of how images are grouped based on their features.

Feel free to modify or update the project as necessary. 🙂

For a more detailed explanation i encourage you to read the article from Gabe Flomo [3].

## References and Interesting Links <a name="ref"></a>
[1]  [Cats-vs-Dogs](https://www.kaggle.com/datasets/shaunthesheep/microsoft-catsvsdogs-dataset/data)

[2]  [Unsupervised feature extraction of aerial images for clustering and understanding hazardous road segments](https://www.nature.com/articles/s41598-023-38100-1)

[3]  [How to cluster images based on visual similarity](https://towardsdatascience.com/how-to-cluster-images-based-on-visual-similarity-cd6e7209fe34)
