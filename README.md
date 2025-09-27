# Restaurant Recommendation System

A machine learning project that analyzes restaurant data and provides personalized restaurant recommendations using clustering algorithms and sentiment analysis.

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Data Processing Pipeline](#data-processing-pipeline)
- [Machine Learning Models](#machine-learning-models)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This project implements a comprehensive restaurant recommendation system using the Zomato dataset. It combines various machine learning techniques including:
- Data preprocessing and cleaning
- Sentiment analysis of customer reviews
- Feature engineering with multi-hot encoding
- K-means clustering for restaurant segmentation
- Interactive recommendation system

## ✨ Features

- **Data Cleaning & Preprocessing**: Handles missing values, data type conversions, and outlier removal
- **Sentiment Analysis**: Analyzes customer reviews to extract sentiment polarity using TextBlob
- **Cuisine Encoding**: Multi-hot encoding for restaurant cuisines
- **Weighted Rating System**: Creates normalized ratings based on votes and original ratings
- **Restaurant Clustering**: Groups similar restaurants using K-means clustering
- **Interactive Recommendation**: Provides personalized restaurant suggestions based on user preferences
- **Comprehensive Visualizations**: Statistical plots and cluster visualizations

## 📊 Dataset

The project uses the Zomato restaurant dataset containing the following key features:
- Restaurant names and locations
- Cuisine types
- Ratings and votes
- Cost for two people
- Online ordering availability
- Table booking options
- Customer reviews

## 🚀 Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd restaurant-recommendation-system
```

2. Install required dependencies:
```bash
pip install pandas numpy matplotlib seaborn textblob nltk scikit-learn
```

3. Download NLTK data:
```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
```

4. Ensure you have the Zomato dataset (`zomato.csv`) in your project directory.

## 💻 Usage

### Running the Notebook

1. Open the Jupyter notebook:
```bash
jupyter notebook "ml2 code.ipynb"
```

2. Run all cells sequentially to:
   - Load and preprocess the data
   - Perform exploratory data analysis
   - Train the clustering model
   - Generate recommendations

### Using the Recommendation System

The interactive recommendation system will prompt you for:
- **Cuisine preferences**: Enter comma-separated cuisine types (e.g., "Italian, Chinese")
- **Price range**: Minimum and maximum cost for two people
- **Online ordering**: Whether you prefer restaurants with online ordering
- **Minimum rating**: Your preferred minimum restaurant rating

Example interaction:
```
Welcome to the Restaurant Recommender!
Enter preferred cuisine(s) (comma separated, e.g., Italian, Chinese): Italian, Continental
Enter minimum cost for two people (e.g., 200): 300
Enter maximum cost for two people (e.g., 1000): 800
Do you prefer restaurants that offer online orders? (Yes/No): Yes
Enter minimum rating preference (e.g., 3.5): 4.0
```

## 🔄 Data Processing Pipeline

### 1. Data Cleaning
- Remove null values
- Handle duplicate entries
- Convert data types (string to float for costs and ratings)
- Remove invalid rating entries

### 2. Feature Engineering
- **Weighted Rating Calculation**: Combines rating and vote count with smoothing
- **Normalization**: Scales weighted ratings to 0-5 range
- **Binary Encoding**: Converts Yes/No columns to 1/0
- **Multi-hot Encoding**: Creates binary features for each cuisine type

### 3. Text Processing
- Clean review text by removing ratings and special characters
- Remove stop words using NLTK
- Apply sentiment analysis using TextBlob
- Create TF-IDF vectors from cleaned reviews

### 4. Feature Scaling
- StandardScaler normalization for clustering features
- Combines numerical and encoded categorical features

## 🤖 Machine Learning Models

### K-Means Clustering
- **Elbow Method**: Determines optimal number of clusters (K=85)
- **Features Used**: 
  - Normalized rating
  - Sentiment score
  - Approximate cost
  - Online ordering availability
  - Table booking availability
  - Cuisine encodings

### Dimensionality Reduction
- **PCA**: Reduces features to 2D for visualization
- **Visualization**: Scatter plot showing cluster distributions

### Model Evaluation
- **Silhouette Score**: Measures clustering quality
- **Cluster Analysis**: Examines cluster centers and characteristics

## 📈 Results

### Key Insights
1. **Most Popular Cuisines**: North Indian, Chinese, Fast Food
2. **Restaurant Types**: Casual Dining, Quick Bites, Cafe
3. **Rating Distribution**: Most restaurants rated between 3.5-4.5
4. **Clustering Quality**: Silhouette score indicates good cluster separation

### Visualizations Generated
- Distribution of restaurant ratings
- Cost distribution analysis
- Top 15 most common cuisines
- Top 15 restaurant types
- Cluster visualization using PCA
- Elbow curve for optimal cluster selection

## 🛠️ Technical Stack

- **Python 3.x**
- **pandas**: Data manipulation and analysis
- **NumPy**: Numerical computations
- **Matplotlib/Seaborn**: Data visualization
- **scikit-learn**: Machine learning algorithms
- **TextBlob**: Sentiment analysis
- **NLTK**: Natural language processing
- **Collections**: Data structure utilities

## 📁 Project Structure

```
restaurant-recommendation-system/
├── ml2 code.ipynb          # Main Jupyter notebook
├── README.md               # Project documentation
├── zomato.csv             # Dataset (not included)
└── requirements.txt       # Python dependencies
```

## 🤝 Contributing

Contributions are welcome! Please feel free to:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Zomato for providing the restaurant dataset
- scikit-learn community for machine learning tools
- NLTK team for natural language processing capabilities

---

**Note**: Make sure to have the Zomato dataset (`zomato.csv`) in your project directory before running the notebook. The dataset should contain columns like 'name', 'cuisines', 'rate', 'votes', 'approx_cost(for two people)', 'online_order', 'book_table', 'reviews_list', etc.
