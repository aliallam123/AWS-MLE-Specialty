# Exploratory Data Analysis (EDA) & Python for AWS MLE Specialty

---

### Python's Role in EDA  
- Python is the language of choice for ML and data science but **exam won't expect coding knowledge**  
- Know major Python packages and their high-level purpose  

---

### Key Python Libraries & Concepts  

### Key Python Libraries & Concepts  

| Library/Concept | Purpose & Notes                                  |
|-----------------|------------------------------------------------|
| **pandas**      | Main library for data manipulation & exploration. Uses **DataFrames** (2D tables) and **Series** (1D arrays). Useful to slice, filter, clean data, handle outliers, extract subsets. |
| **NumPy**       | Lower-level library for arrays. Interoperable with pandas. Common format for ML algorithm inputs. |
| **Matplotlib**  | Basic visualization library. Creates plots like box-and-whisker and histograms to show distribution and outliers. |
| **Seaborn**     | Advanced visualization built on Matplotlib. Produces prettier plots, heatmaps, pairplots, jointplots for deeper insight. |
| **scikit-learn**| Popular ML library. Provides consistent interfaces for ML algorithms (classification, regression). Example: Random Forest classifier using `.fit(X, y)` and `.predict()`. |
---

### Important Concepts  

- **DataFrame:** Table-like data structure, manipulate rows/cols like in Excel  
- **Series:** Single column or row extracted from DataFrame  
- **Train/Test Split:** Split data into training & test sets for model validation  
- **Classification vs Regression:**  
  - Classification: Predict categories (e.g., hired or not hired)  
  - Regression: Predict continuous numeric values (e.g., height prediction)  
- **Preprocessing:** Scale features (e.g., normalize distribution) for better ML performance  

---

### Summary  
- Python tools help explore, clean, transform, visualize data before ML  
- pandas + NumPy for data prep  
- Matplotlib + Seaborn for visualization  
- scikit-learn for applying ML algorithms consistently  
- Know concepts but no need to write or deeply understand code for exam
