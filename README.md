# 📊 Working With Data

> A comprehensive, modular Python toolkit for end-to-end data workflows — from ingestion to feature-ready datasets.

---

## 🗂️ Project Structure

```
Working/
└── working_with_data/
    ├── EDA/                    # Exploratory Data Analysis
    ├── feature_engineering/    # Data Preprocessing & Transformation
    └── read_data/              # Data Ingestion Methods
```

---

## 📁 Modules Overview

### 🔍 1. EDA — Exploratory Data Analysis

Located in `working_with_data/EDA/`

Comprehensive visual and statistical exploration of datasets, covering both **univariate** and **multivariate** analysis.

#### Univariate Analysis
Analyze individual features in isolation to understand distributions and detect anomalies.

| Technique | Description |
|-----------|-------------|
| **Box Plot** | Visualize spread, median, and outliers for a single variable |
| **Histogram** | Frequency distribution of numerical features |
| **Bar Plot** | Count or value comparison across categories |
| **KDE Plot** | Kernel Density Estimation for smooth distribution curves |

#### Multivariate Analysis
Explore relationships and interactions between two or more variables.

| Technique | Description |
|-----------|-------------|
| **Scatter Plot** | Identify correlation and clustering between two numerical features |
| **Pair Plot** | Pairwise relationships across all numeric features |
| **Heatmap** | Correlation matrix visualization |
| **Grouped Bar Plot** | Compare categories across a second dimension |

---

### ⚙️ 2. Feature Engineering — Data Preprocessing & Transformation

Located in `working_with_data/feature_engineering/`

A modular pipeline for transforming raw data into model-ready features.

#### Missing Value Handling
- Mean / Median / Mode imputation
- Forward fill and backward fill strategies
- Dropping rows/columns based on threshold

#### Column Transformation & Scaling
- **StandardScaler** — Zero mean, unit variance normalization
- **MinMaxScaler** — Rescale features to a `[0, 1]` range
- **RobustScaler** — Scaling robust to outliers using IQR
- **Log / Power Transformations** — Reduce skewness in distributions

#### Categorical Encoding
- **One-Hot Encoding (OHE)** — For nominal (unordered) categorical variables
- **Ordinal Encoding** — For ordered categorical variables (e.g., Low → Medium → High)
- **Label Encoding** — For binary or target-mapped categories

#### Outlier Detection
- IQR (Interquartile Range) method
- Z-score based filtering
- Visual detection via box plots and scatter plots

#### Feature Extraction
- Polynomial feature generation
- Date/time decomposition (year, month, day, weekday, hour)
- Text feature extraction (length, word count, etc.)
- Interaction terms between features

---

### 📥 3. Read Data — Data Ingestion Methods

Located in `working_with_data/read_data/`

Flexible, multi-source data loading utilities supporting structured, semi-structured, and remote data formats.

#### File-Based Reading
| Method | Format | Function |
|--------|--------|----------|
| `read_csv()` | `.csv` | Load comma-separated files with pandas |
| `read_json()` | `.json` | Parse flat or nested JSON structures |
| `read_excel()` | `.xlsx / .xls` | Read Excel spreadsheets |
| `read_parquet()` | `.parquet` | Efficient columnar storage format |

#### Web-Based Reading
| Method | Description |
|--------|-------------|
| **URL Reading** | Fetch datasets directly from remote file URLs using `pandas` or `requests` |
| **Web Scraping** | Extract tabular or textual data from HTML pages using `BeautifulSoup` / `lxml` |
| **API Reading** | Connect to REST APIs and paginate through JSON responses |

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn scikit-learn requests beautifulsoup4 openpyxl
```

### Quick Start

```python
# 1. Load your data
from working_with_data.read_data import read_csv
df = read_csv("data/sample.csv")

# 2. Explore it
from working_with_data.EDA import plot_boxplot, plot_scatter
plot_boxplot(df, column="age")
plot_scatter(df, x="income", y="spend")

# 3. Engineer features
from working_with_data.feature_engineering import handle_missing, encode_categorical, scale_features
df = handle_missing(df, strategy="median")
df = encode_categorical(df, method="ohe", columns=["city", "gender"])
df = scale_features(df, method="standard")
```

---

## 🧰 Tech Stack

| Library | Purpose |
|--------|---------|
| `pandas` | Data manipulation and I/O |
| `numpy` | Numerical operations |
| `matplotlib` | Base plotting library |
| `seaborn` | Statistical visualizations |
| `scikit-learn` | Preprocessing and encoding |
| `requests` | HTTP-based data fetching |
| `BeautifulSoup` | HTML parsing for web scraping |

---

## 📌 Contributing

Contributions are welcome! Please follow this structure:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-eda-plot`)
3. Commit your changes (`git commit -m 'Add violin plot to EDA module'`)
4. Push and open a Pull Request

---

## 📄 License

This project is licensed under the MIT License. See [`LICENSE`](./LICENSE) for details.

---

<p align="center">Built for clean, reproducible, and scalable data workflows.</p>
