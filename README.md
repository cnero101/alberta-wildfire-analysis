# 🔥 Alberta Wildfire Data Story (2006-2025)

**A comprehensive data science investigation of 26,551 wildfire incidents across two decades**

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![License](https://img.shields.io/badge/License-MIT-green)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-red)
![geopandas](https://img.shields.io/badge/geopandas-GIS-purple)

---

## 📊 Project Overview

This project analyzes **26,551 wildfire incidents** from Alberta, Canada (2006-2025) using advanced data science techniques to answer critical questions about fire patterns, causes, and predictability.

### 🎯 Research Questions

| # | Question | Methods | Key Finding |
|---|----------|---------|-------------|
| **1** | Are wildfires increasing? | Linear regression, trend analysis | High variability, no simple trend |
| **2** | Where do fires concentrate? | Geospatial clustering (EPSG:3403) | Three distinct regions identified |
| **3** | What causes fires by region? | Chi-square test, contingency analysis | Causes vary significantly N→S |
| **4** | Does fast response reduce size? | Correlation analysis | Weak correlation (r≈0.3) |
| **5** | What weather predicts fire behavior? | Pearson correlation, scatter analysis | Combinations matter most |
| **6** | Can ML predict fire types? | K-means, Random Forest | 87% accuracy, 5 fire types |

### 💡 Key Insights

✅ **87% ML prediction accuracy** for fire size classification  
✅ **5 distinct fire behavior types** identified through clustering  
✅ **Regional differences** support tailored management strategies  
✅ **High year-to-year variability** dominates temporal patterns  
✅ **Weather combinations** predict risk better than individual variables  

---

## 🚀 Quick Start

### Prerequisites
- Python 3.12 or higher
- Jupyter Notebook
- 4GB+ RAM recommended

### Installation

```bash
# Clone repository
git clone https://github.com/yourusername/alberta-wildfire-analysis.git
cd alberta-wildfire-analysis

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook Wildfire_DataStory_Enhanced.ipynb
```

### Get the Data

**Option 1: Download from Source**
1. Visit [Alberta Wildfire Historical Data](https://wildfire.alberta.ca/resources/historical-data/)
2. Download complete dataset (2006-2025)
3. Save as `data/wildfire_data.csv`

**Option 2: Use Sample Data**
- Sample dataset available in `/data` folder (10% random sample for testing)

---

## 📁 Repository Structure

```
alberta-wildfire-analysis/
│
├── Wildfire_DataStory_Enhanced.ipynb    # Main analysis notebook ⭐
├── README.md                             # This file
├── requirements.txt                      # Python dependencies
├── LICENSE                               # MIT License
├── .gitignore                           # Git ignore rules
│
├── data/
│   ├── README.md                        # Data source info
│   └── wildfire_data.csv                # Dataset (download separately)
│
├── images/                              # Visualizations
│   ├── eda_*.png                       # Exploratory charts
│   ├── q1_*.png                        # Question 1 visuals
│   ├── q2_*.png                        # Question 2 visuals
│   └── ...                             # All generated charts
│
└── docs/                               # Additional documentation
    ├── methodology.md                  # Detailed methods
    └── data_dictionary.md              # Variable definitions
```

---

## 🛠️ Technical Stack

### Data Science & ML
| Library | Purpose | Version |
|---------|---------|---------|
| **pandas** | Data manipulation | 2.0+ |
| **numpy** | Numerical computing | 1.24+ |
| **scipy** | Statistical analysis | 1.10+ |
| **scikit-learn** | Machine learning | 1.3+ |

### Visualization
| Library | Purpose | Version |
|---------|---------|---------|
| **matplotlib** | Static plots | 3.7+ |
| **seaborn** | Statistical graphics | 0.12+ |
| **plotly** | Interactive charts | 5.14+ |

### Geospatial
| Library | Purpose | Version |
|---------|---------|---------|
| **geopandas** | Geographic data structures | 0.13+ |
| **pyproj** | Coordinate transformations | 3.5+ |
| **contextily** | Basemap tiles | 1.3+ |
| **shapely** | Geometric operations | 2.0+ |

**Coordinate System:** EPSG:3403 (NAD83 Alberta 10-TM Forest)

---

## 📈 Analysis Workflow

### 1. Data Loading & Profiling
- Import 26,551 fire records
- Assess data quality (completeness, types, distributions)
- Identify missing data patterns

### 2. Data Preparation
- Handle missing values appropriately
- Engineer features (Fire Weather Index, periods, regions)
- Convert dates and categorize variables

### 3. Exploratory Data Analysis
- Visualize distributions
- Identify temporal and spatial patterns
- Compute initial correlations

### 4-9. Six Research Questions
- Each question follows: Motivation → Methods → Analysis → Findings → Implications
- Statistical rigor: hypothesis tests, significance levels, confidence intervals
- Multiple visualization types for each question

### 10. Machine Learning
- **Unsupervised:** K-means clustering (k=5) to discover fire types
- **Supervised:** Random Forest to predict fire size categories
- **Validation:** Silhouette scores, confusion matrices, precision/recall

### 11. Synthesis & Conclusions
- Connect findings across questions
- Identify actionable insights
- Acknowledge limitations
- Recommend next steps

---

## 📊 Sample Visualizations

### Temporal Trends (Question 1)
Annual fire frequency shows high year-to-year variability with extreme years (2016, 2019, 2023) rather than consistent linear increase.

### Spatial Clustering (Question 2 & 6)
Geographic analysis reveals three distinct fire environments: Northern boreal (remote, lightning-caused), Central transition zone, and Southern grassland (human-caused).

### Machine Learning Results (Question 6)
K-means clustering identified 5 fire behavior types with 87% Random Forest classification accuracy.

*Note: All visualizations generated automatically when running the notebook*

---

## 🎓 Methodology Highlights

### Statistical Methods
- **Linear Regression** - Trend detection (coefficients, R², p-values)
- **Pearson Correlation** - Association strength and significance
- **Chi-Square Test** - Independence testing (categorical variables)
- **Hypothesis Testing** - α = 0.05 significance level throughout

### Machine Learning
- **K-Means Clustering**
  - Optimal k selection via elbow method and silhouette scores
  - Feature standardization (StandardScaler)
  - 9 variables: weather, location, timing, fire characteristics
  
- **Random Forest Classification**
  - 70/30 train/test split
  - Hyperparameter tuning via grid search
  - Performance metrics: accuracy, precision, recall, F1
  - Feature importance analysis

### Geospatial Analysis
- **Projection:** EPSG:3403 (NAD83 Alberta 10-TM Forest)
- **Grid Resolution:** 5km × 5km cells
- **Smoothing:** Gaussian kernel (σ=2.5 cells)
- **Density Mapping:** 2D histograms with interpolation

---

## 💡 Key Findings & Implications

### For Fire Managers
✅ Pre-position resources based on identified geographic hotspots  
✅ Use cluster profiles for initial fire risk assessment  
✅ Differentiate strategies by region (North vs. Central vs. South)  
✅ Peak suppression capacity needed June-August  

### For Policy Makers
✅ Evidence supports regional (not province-wide) strategies  
✅ Invest in northern detection (helicopters, remote sensing)  
✅ Invest in southern prevention (public education, fuel mgmt)  
✅ Climate adaptation: prepare for high-variability future  

### For Researchers
✅ Demonstrates ML feasibility for fire classification  
✅ Identifies data gaps (fuel moisture, suppression effort)  
✅ Provides baseline for climate change studies  
✅ Methodology transferable to other regions  

---

## ⚠️ Limitations & Caveats

### Data Quality
- **60% missing environmental data** (weather measurements)
  - Small fires receive abbreviated assessments
  - May over-represent larger fires in correlations
  - Complete case analysis is valid but introduces bias

### Analytical Scope
- **Correlation ≠ Causation** - We show associations, not proven causes
- **20-year window** - May be too short for climate trend detection
- **Suppression effects** - Final fire size reflects both behavior AND firefighting
- **Missing variables** - Fuel moisture, suppression effort, economic costs

### Model Limitations
- **87% accuracy** - Means 13% error rate (168 large fires misclassified)
- **Cannot replace experts** - Models support, don't replace human judgment
- **Temporal validity** - Patterns may shift with climate change

*See notebook for complete limitations discussion*

---

## 🤝 Contributing

Contributions welcome! Please follow these guidelines:

### How to Contribute
1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/improvement`)
3. **Commit** your changes (`git commit -m 'Add improvement'`)
4. **Push** to branch (`git push origin feature/improvement`)
5. **Open** a Pull Request

### Areas for Contribution
- 🔬 **Additional analyses** - Temporal forecasting, fuel type deep-dive
- 📊 **New visualizations** - Interactive dashboards, animated maps
- 🤖 **Model improvements** - Alternative ML algorithms, ensemble methods
- 📝 **Documentation** - Data dictionary expansion, methodology details
- 🐛 **Bug fixes** - Code optimization, error handling

### Code Style
- Follow PEP 8 guidelines
- Add docstrings to functions
- Include comments for complex logic
- Update requirements.txt if adding dependencies

---

## 📧 Contact & Support

**Questions?** Open an [issue](https://github.com/yourusername/alberta-wildfire-analysis/issues)

**Project Maintainer:**  
- **Name:** Ifeanyi Njoku
- **Email:** ifeanyinjoku2@gmail.com
- **LinkedIn:** [www.linkedin.com/in/ifeanyi-e-njoku](https://www.linkedin.com/in/ifeanyi-e-njoku/)
- **Portfolio:** [https://github.com/cnero101/alberta-wildfire-analysis.git](https://yourportfolio.com)

**Want to collaborate?** Reach out directly or open a discussion!

---

## 📜 License

This project is licensed under the **MIT License** - see [LICENSE](LICENSE) file for details.

### Data License
Alberta Wildfire data is **public domain** (Government of Alberta).  
Attribution required: *"Data provided by Alberta Wildfire Management"*

---

## 🙏 Acknowledgments

### Data Source
- **Alberta Wildfire Management** for maintaining comprehensive public records
- **Government of Alberta** for open data commitment

### Inspiration & Support
- **Fire management professionals** whose expertise keeps communities safe
- **Data science community** for tools and best practices
- **Open source contributors** for excellent libraries

### Tools & Technologies
- Python ecosystem (pandas, scikit-learn, matplotlib, geopandas)
- Jupyter Project for notebook environment
- GitHub for version control and collaboration

---

## 📚 References & Resources

### Data Source
- Alberta Wildfire Historical Data: https://wildfire.alberta.ca/resources/historical-data/
- Canadian Wildland Fire Information System: https://cwfis.cfs.nrcan.gc.ca/

### Relevant Literature
1. Flannigan, M., et al. (2013). Global wildland fire season severity in the 21st century. *Forest Ecology and Management*.
2. Rodrigues, M., & de la Riva, J. (2014). An insight into machine-learning algorithms to model wildfire susceptibility. *Environmental Modelling & Software*.
3. Tymstra, C., et al. (2010). Development of Prometheus: Canadian Wildland Fire Growth Model. *Natural Resources Canada*.

### Related Projects
- FireSmart Canada: https://www.firesmartcanada.ca/
- NASA FIRMS (Fire Information for Resource Management): https://firms.modaps.eosdis.nasa.gov/

---

## 📈 Project Stats

![GitHub stars](https://img.shields.io/github/stars/yourusername/alberta-wildfire-analysis?style=social)
![GitHub forks](https://img.shields.io/github/forks/yourusername/alberta-wildfire-analysis?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/yourusername/alberta-wildfire-analysis?style=social)
![GitHub issues](https://img.shields.io/github/issues/yourusername/alberta-wildfire-analysis)
![GitHub last commit](https://img.shields.io/github/last-commit/yourusername/alberta-wildfire-analysis)

---

## 🌟 Support This Project

If you found this analysis useful:

⭐ **Star this repository**  
🔀 **Fork for your own use**  
📢 **Share with colleagues**  
💬 **Provide feedback**  
🤝 **Contribute improvements**  

Every star helps make data science research more visible!

---

## 📅 Version History

### v1.0.0 (February 2026)
- Initial release
- Complete 6-question analysis
- Machine learning implementation
- EPSG:3403 geospatial visualization
- Comprehensive documentation

---

**🔥 Analyzing wildfires with data science to build a more resilient Alberta**

*Last Updated: February 2026*
