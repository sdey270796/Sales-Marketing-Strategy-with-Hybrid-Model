# 📈 Sales & Marketing Strategy Optimization using Statistical Analysis

> **An End-to-End Sales & Marketing Analytics Project for identifying high-performing campaigns, evaluating sales-contact effectiveness, segmenting clients by facility type, and optimizing resource allocation through correlation and OLS regression analysis.**

This repository presents a comprehensive **Sales & Marketing Strategy Analysis** designed to answer a practical business question:

> **Which sales and marketing activities generate the greatest return for different types of clients, and where should the organization allocate its resources?**

The project analyzes campaign activity, sales contacts, client characteristics, competition levels, monthly patterns, and collected revenue to identify the strategies most strongly associated with sales performance.

Rather than applying machine learning purely for prediction, this project focuses on **statistical inference and business decision-making**. It uses correlation analysis and **Ordinary Least Squares (OLS) regression** to quantify the relationship between marketing/sales activities and the amount collected, both at an overall level and separately for different client segments.

---

# 🚀 Project Highlights

* 📊 Comprehensive Sales & Marketing Analytics
* 🎯 Campaign Effectiveness Analysis
* 👥 Client Segmentation
* 💰 Revenue / Amount Collected Analysis
* 📈 Correlation-Based Strategy Assessment
* 📐 Ordinary Least Squares (OLS) Regression
* 🔬 Statistical Significance Testing
* 🧩 Segment-Specific Regression Models
* 💵 ROI-Oriented Strategy Interpretation
* 📊 Marketing Resource Allocation Analysis
* 📅 Monthly / Temporal Analysis
* 🏢 Competition-Level Analysis
* 📋 Consolidated Strategy Recommendations
* 📁 Exportable Strategy Summary

---

# 📖 Business Problem

Organizations often invest in multiple sales and marketing channels simultaneously:

* Email campaigns
* Flyer campaigns
* Phone campaigns
* Different sales-contact stages

However, simply knowing how much is being spent on each activity does not tell management **which activities are actually associated with higher revenue**.

The challenge becomes even more important when the customer base contains different types of facilities.

A strategy that works well for a **Large Facility** may not work equally well for a **Small Facility** or **Medium Facility**.

This project therefore investigates both:

### Overall Strategy Effectiveness

Which sales and marketing variables have the strongest relationship with **Amount Collected**?

### Segment-Specific Strategy Effectiveness

How does the impact of each strategy change across:

* Small Facilities
* Medium Facilities
* Large Facilities
* Private Facilities

---

# 🎯 Business Objectives

The notebook defines four primary business objectives.

## 1. Evaluate Campaign Effectiveness

Assess the effectiveness of different campaigns and sales contacts based on their relationship with revenue/amount collected.

## 2. Optimize Resource Allocation

Identify high-performing sales contacts and campaigns so that budget, time, and manpower can be directed toward more productive activities.

## 3. Develop Segmented Strategies

Develop different strategies for different client types rather than applying a single marketing strategy across the entire customer base.

## 4. Improve Decision-Making

Provide data-driven evidence to support future sales and marketing decisions.

---

# 💼 Expected Business Impact

The project is designed to support:

### 💰 Increased Profitability

Redirect resources toward activities associated with higher returns.

### 🎯 Better Client Targeting

Identify which strategies work best for different client segments.

### 💵 Cost Reduction

Reduce investment in activities that demonstrate weak or negative relationships with collected revenue.

### ⚡ Improved Sales Efficiency

Enable sales teams to prioritize more productive contact stages.

### 📊 Data-Driven Strategy

Replace purely intuition-based marketing decisions with quantitative analysis.

---

# 🔄 Analytical Workflow

```text
                    Raw Campaign Data
                           │
                           ▼
                   Data Quality Checks
                           │
                           ▼
                 Feature Understanding
                           │
                           ▼
               Feature Engineering
                           │
                 ┌─────────┴─────────┐
                 ▼                   ▼
          Overall EDA          Client Segmentation
                 │                   │
                 ▼                   ▼
        Distribution Analysis   Segment Analysis
                 │                   │
                 └─────────┬─────────┘
                           ▼
                 Correlation Analysis
                           │
                           ▼
                OLS Regression Model
                           │
                 ┌─────────┴─────────┐
                 ▼                   ▼
          Overall Regression    Segment Regression
                 │                   │
                 └─────────┬─────────┘
                           ▼
                  Significant Variables
                           │
                           ▼
              ROI / Impact Interpretation
                           │
                           ▼
              Strategic Recommendations
```

---

# 📂 Dataset

The notebook imports the dataset from the project's GitHub repository:

```text
Sales-Marketing-Strategy/Campaign-Data.csv
```

The dataset contains information about sales, marketing activities, client characteristics, competition, and revenue collected.

The final analysis contains **297,600 observations** across the broader dataset, while the regression models operate on an analytical sample of **2,976 observations**.

---

# 🧾 Dataset Features

The notebook documents the following major variables:

| Feature                 | Description                                    |
| ----------------------- | ---------------------------------------------- |
| `Client ID`             | Unique identifier for each client              |
| `Client Type`           | Facility/client category                       |
| `Number of Customers`   | Number of customers associated with the client |
| `Monthly Target`        | Monthly sales target                           |
| `Zip Code`              | Geographic identifier                          |
| `Calendardate`          | Date associated with the observation           |
| `Amount Collected`      | Revenue/amount collected — target variable     |
| `Unit Sold`             | Number of units sold                           |
| `Campaign (Email)`      | Email campaign activity                        |
| `Campaign (Flyer)`      | Flyer campaign activity                        |
| `Campaign (Phone)`      | Phone campaign activity                        |
| `Sales Contact 1`       | First sales-contact activity                   |
| `Sales Contact 2`       | Second sales-contact activity                  |
| `Sales Contact 3`       | Third sales-contact activity                   |
| `Sales Contact 4`       | Fourth sales-contact activity                  |
| `Sales Contact 5`       | Fifth sales-contact activity                   |
| `Number of Competition` | Competition level                              |

---

# 🏢 Client Segmentation

One of the most important aspects of the project is segmentation by **Client Type**.

The dataset contains four client categories:

* 🏢 **Large Facility**
* 🏢 **Small Facility**
* 🏢 **Medium Facility**
* 🏠 **Private Facility**

The distribution reported in the notebook is:

| Client Type      | Approx. Share |
| ---------------- | ------------: |
| Large Facility   |           46% |
| Small Facility   |           28% |
| Medium Facility  |           17% |
| Private Facility |            9% |

This segmentation allows the analysis to move beyond an "average customer" strategy.

---

# 🧹 Data Preparation

The notebook performs several data-quality and feature-engineering operations.

## Basic Data Checks

The following checks are performed:

* Dataset dimensions
* Data types
* Missing values
* Descriptive statistics
* Numeric feature identification
* Categorical feature identification
* Unique-value analysis

---

# 🧩 Feature Engineering

## Removing Identifier Variables

The following columns are removed from the main analytical dataset:

```text
Client ID
Zip Code
```

These identifiers are not directly useful for the primary sales-strategy analysis.

---

## 📅 Month Extraction

The `Calendardate` field is converted into a month-based feature.

The notebook creates:

```text
Month
```

and maps numerical month values to:

```text
Jan, Feb, Mar, ..., Dec
```

The original calendar date is then removed from the analysis.

This allows the project to investigate potential temporal patterns without directly using the raw date.

---

# 📊 Exploratory Data Analysis

The project performs extensive exploratory analysis before statistical modeling.

---

## 1. Client-Type Distribution

The analysis shows that **Large Facilities form the largest share of the dataset**, followed by Small, Medium, and Private Facilities.

This provides the first indication that client segmentation should be an important part of the strategy.

---

## 2. Competition Analysis

The notebook analyzes the distribution of:

```text
Number of Competition
```

across client types.

The dataset contains:

* Low Competition
* High Competition

and the analysis uses cross-tabulation to examine their relationship with client categories.

---

## 3. Numerical Feature Distributions

Distribution plots are generated for the numerical variables.

These include:

* Number of Customers
* Monthly Target
* Amount Collected
* Units Sold
* Campaign activity
* Sales Contact activity

The analysis highlights considerable skewness and the presence of extreme values in several business variables.

---

## 4. Categorical Feature Distributions

Count plots are generated for categorical variables including:

* Client Type
* Number of Competition
* Month

These visualizations help understand the composition of the dataset before analyzing strategy effectiveness.

---

# 📦 Outlier Analysis

Boxplots are used to examine numerical variables for extreme observations.

The notebook identifies substantial outliers in variables such as:

* Number of Customers
* Monthly Target
* Amount Collected
* Units Sold
* Campaign activity
* Sales Contact activity

The `Amount Collected` distribution is particularly skewed, with observations reaching very high values relative to the majority of the dataset.

This is an important characteristic to consider when interpreting the regression results.

---

# 💰 Revenue Analysis by Client Type

The notebook compares **Amount Collected** across client categories.

One notable observation is that:

* **Medium Facilities** exhibit a relatively high median amount collected.
* **Large Facilities** also contribute substantial revenue.
* **Small Facilities** and **Private Facilities** generally show lower central revenue levels.

The analysis also identifies significant high-value outliers.

---

# 🏁 Revenue vs Competition

The project examines how `Amount Collected` varies according to competition level.

The notebook observes that:

* Low-competition environments have a broad revenue range with substantial high-value outliers.
* High-competition environments show a higher median and relatively more compressed distribution.

This suggests that competition level may interact with client and strategy characteristics and deserves consideration when designing marketing strategies.

---

# 📈 Correlation Analysis

Correlation analysis is performed to quantify the **linear relationship between sales/marketing activities and Amount Collected**.

The strongest overall correlations reported in the notebook include:

| Variable         | Correlation with Amount Collected |
| ---------------- | --------------------------------: |
| Sales Contact 2  |                          **0.55** |
| Campaign (Flyer) |                          **0.44** |
| Sales Contact 3  |                          **0.36** |
| Sales Contact 1  |                          **0.28** |
| Campaign (Email) |                          **0.25** |
| Sales Contact 4  |                          **0.24** |
| Sales Contact 5  |                          **0.10** |

The interpretation is directional rather than causal: a positive correlation indicates that higher activity in the variable is associated with higher collected amounts in the observed data.

---

# 🔬 Ordinary Least Squares Regression

The project then moves from simple correlations to multivariate statistical analysis.

The dependent variable is:

```text
Amount Collected
```

The explanatory variables are:

```text
Campaign Email
Campaign Flyer
Campaign Phone
Sales Contact 1
Sales Contact 2
Sales Contact 3
Sales Contact 4
Sales Contact 5
```

The model is fitted using:

```python
statsmodels.formula.api.ols()
```

---

# 📊 Overall Regression Results

The overall OLS model reports:

| Metric        |       Value |
| ------------- | ----------: |
| R²            |   **0.480** |
| Adjusted R²   |   **0.478** |
| F-statistic   |   **342.1** |
| Observations  |   **2,976** |
| Model p-value | **< 0.001** |

The model therefore explains approximately **48% of the observed variance in Amount Collected** within this analytical sample.

---

# 🔎 Statistically Significant Overall Drivers

According to the notebook's OLS results, the following predictors are statistically significant at the 5% level:

| Variable         | Coefficient |
| ---------------- | ----------: |
| Sales Contact 4  | **10.9478** |
| Sales Contact 1  |  **4.2368** |
| Sales Contact 2  |  **3.6382** |
| Sales Contact 3  |  **2.3432** |
| Campaign (Flyer) |  **3.3376** |

The following variables were not statistically significant at the 5% level in the overall model:

* Campaign (Email)
* Campaign (Phone)
* Sales Contact 5

---

# 🏢 Segment-Specific Regression

A major strength of the project is that the regression analysis is repeated independently for each client type.

This recognizes that:

> **The same marketing strategy may have very different effectiveness across different customer segments.**

Separate OLS models are estimated for:

* Small Facility
* Large Facility
* Private Facility
* Medium Facility

---

# 📊 Segment-Level Model Performance

| Client Type      |        R² | Adjusted R² | Observations |
| ---------------- | --------: | ----------: | -----------: |
| Small Facility   | **0.054** |       0.046 |          840 |
| Large Facility   | **0.371** |       0.367 |        1,368 |
| Private Facility | **0.346** |       0.326 |          264 |
| Medium Facility  | **0.437** |       0.428 |          504 |

The models therefore differ considerably in explanatory power.

The **Medium Facility** model has the highest R² among the four segment-specific models, while the **Small Facility** model explains substantially less of the observed variation.

---

# 🎯 Segment-Level Strategy Findings

## 🟢 Small Facilities

Statistically significant variables include:

| Variable        |   Coefficient |
| --------------- | ------------: |
| Sales Contact 2 |   **+0.8101** |
| Campaign Phone  | **−0.000003** |

The notebook therefore identifies **Sales Contact 2** as a positive significant driver for this segment, while Campaign Phone has a very small negative coefficient.

### Strategic Interpretation

Prioritize Sales Contact 2 for Small Facilities and carefully evaluate the cost-effectiveness of phone campaigns.

---

# 🔵 Large Facilities

The significant variables include:

| Variable        |  Coefficient |
| --------------- | -----------: |
| Sales Contact 1 | **+11.6731** |
| Sales Contact 4 | **+10.6145** |
| Sales Contact 2 |  **+4.0031** |
| Campaign Flyer  |  **+2.7204** |
| Sales Contact 3 |  **+2.0316** |
| Campaign Phone  |  **−3.5361** |

### Strategic Interpretation

Large Facilities show the strongest positive relationships with:

1. **Sales Contact 1**
2. **Sales Contact 4**
3. **Sales Contact 2**
4. **Campaign Flyer**
5. **Sales Contact 3**

The model also associates Campaign Phone negatively with Amount Collected for this segment.

---

# 🟣 Private Facilities

The only statistically significant variable identified in the segment-specific model is:

| Variable        | Coefficient |
| --------------- | ----------: |
| Sales Contact 2 | **+6.6223** |

### Strategic Interpretation

Sales Contact 2 is the clearest statistically supported sales activity for Private Facilities in the notebook's regression analysis.

---

# 🟠 Medium Facilities

Statistically significant positive variables include:

| Variable        | Coefficient |
| --------------- | ----------: |
| Campaign Flyer  | **+4.1059** |
| Sales Contact 2 | **+3.5778** |
| Sales Contact 1 | **+3.1365** |
| Sales Contact 3 | **+2.1174** |

### Strategic Interpretation

The notebook particularly highlights **Campaign Flyer** and **Sales Contact 2** for Medium Facilities, followed by Sales Contact 1 and Sales Contact 3.

---

# 💵 ROI-Oriented Strategy Summary

The project converts the statistically significant coefficients into a consolidated strategy table and labels the resulting metric as:

```text
Return on Investment
```

The notebook interprets these values as the estimated amount generated per dollar of investment.

Key reported values include:

| Client Type      | Strategy        | Reported Return |
| ---------------- | --------------- | --------------: |
| Large Facility   | Sales Contact 1 |       **$11.7** |
| Large Facility   | Sales Contact 4 |       **$10.6** |
| Private Facility | Sales Contact 2 |        **$6.6** |
| Large Facility   | Sales Contact 2 |        **$4.0** |
| Medium Facility  | Campaign Flyer  |        **$4.1** |
| Medium Facility  | Sales Contact 2 |        **$3.6** |
| Medium Facility  | Sales Contact 1 |        **$3.1** |
| Medium Facility  | Sales Contact 3 |        **$2.1** |
| Large Facility   | Campaign Flyer  |        **$2.7** |
| Large Facility   | Sales Contact 3 |        **$2.0** |
| Small Facility   | Sales Contact 2 |        **$0.8** |

> **Important:** These values are derived from regression coefficients and are therefore best interpreted as model-based impact estimates under the notebook's formulation. They should not automatically be treated as experimentally measured causal ROI without a properly defined cost variable, controlled experimentation, or causal design.

---

# 🧠 Key Strategic Insights

The analysis points toward a **segment-specific marketing strategy** rather than a universal strategy.

### 🏢 Large Facilities

Focus on:

* Sales Contact 1
* Sales Contact 4
* Sales Contact 2
* Flyer Campaigns
* Sales Contact 3

while reassessing Phone Campaign investment.

### 🏢 Medium Facilities

Focus on:

* Flyer Campaigns
* Sales Contact 2
* Sales Contact 1
* Sales Contact 3

The notebook specifically highlights flyer campaigns as particularly effective for this segment.

### 🏢 Private Facilities

Focus primarily on:

* Sales Contact 2

based on the statistically significant relationship identified.

### 🏢 Small Facilities

Prioritize:

* Sales Contact 2

while reviewing the economics of Phone Campaigns.

---

# 📋 Consolidated Strategy Framework

```text
                    CLIENT SEGMENT
                          │
       ┌──────────────────┼──────────────────┐
       ▼                  ▼                  ▼
    Small              Medium             Large
       │                  │                  │
       ▼                  ▼                  ▼
Sales Contact 2    Campaign Flyer     Sales Contact 1
                   Sales Contact 2    Sales Contact 4
                   Sales Contact 1    Sales Contact 2
                   Sales Contact 3    Campaign Flyer
                                      Sales Contact 3
```

Private Facilities can be handled separately with **Sales Contact 2** as the primary statistically significant driver.

---

# 📊 Analytical Techniques Used

This project combines several levels of business analytics.

## Descriptive Analytics

* Dataset profiling
* Counts
* Percentages
* Descriptive statistics
* Distribution analysis

## Diagnostic Analytics

* Correlation analysis
* Cross-tabulation
* Boxplots
* Segment comparison

## Statistical Analytics

* OLS regression
* Coefficients
* p-values
* R²
* Adjusted R²
* F-statistics

## Prescriptive Analytics

* Strategy prioritization
* Resource allocation
* Segment-specific recommendations
* ROI-oriented decision support

This makes the project a useful example of moving from:

**Data → Analysis → Statistical Evidence → Business Strategy**

---

# 📈 Visualizations

The notebook contains several visualization categories.

### Distribution Analysis

* Numerical feature distributions
* Categorical distributions

### Outlier Analysis

* Numerical boxplots
* Revenue by client type
* Revenue by competition level
* Revenue by month

### Relationship Analysis

* Correlation matrices
* Correlation with Amount Collected
* Segment-level correlation analysis

### Strategy Analysis

* Highlighted coefficient tables
* Consolidated strategy summaries

---

# 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* SciPy
* Statsmodels
* Scikit-learn
* Google Colab
* GitHub

---

# 🧠 Concepts Demonstrated

This project demonstrates practical knowledge of:

* Business Analytics
* Sales Analytics
* Marketing Analytics
* Exploratory Data Analysis
* Feature Engineering
* Client Segmentation
* Correlation Analysis
* Statistical Inference
* Linear Regression
* Ordinary Least Squares
* Hypothesis Testing
* p-value Interpretation
* R² and Adjusted R²
* Coefficient Interpretation
* ROI-Oriented Decision Making
* Resource Optimization
* Data-Driven Strategy Development

---

# ⚠️ Statistical Considerations

The project is primarily an **observational analysis**.

Therefore, correlation and regression coefficients should be interpreted as **associations within the observed data**, not automatically as causal effects.

There are also several diagnostic considerations visible in the regression output:

* The overall model has a relatively large condition number.
* The residuals show substantial skewness.
* The Durbin-Watson statistic is below 1 in the overall model.
* Some segment models show extremely large condition numbers.
* The Small Facility model has relatively low explanatory power.
* The `Amount Collected` variable contains substantial outliers.

These observations suggest that future versions could benefit from additional statistical diagnostics and more rigorous modeling.

---

# 🚀 Future Improvements

## 1. Causal Impact Analysis

Move beyond observational regression using:

* A/B testing
* Randomized campaign experiments
* Difference-in-differences
* Propensity-score methods

to estimate causal campaign effectiveness.

---

## 2. Proper Cost-Based ROI

Introduce explicit cost variables for:

* Email campaigns
* Flyer campaigns
* Phone campaigns
* Sales contacts

Then calculate:

```text
ROI = (Incremental Revenue − Campaign Cost) / Campaign Cost
```

rather than using regression coefficients as an ROI proxy.

---

## 3. Predictive Modeling

Extend the project with:

* Random Forest
* XGBoost
* LightGBM
* Gradient Boosting

to predict future revenue/amount collected.

---

## 4. Time-Series Analysis

Since the dataset contains dates, future analysis could investigate:

* Seasonality
* Monthly revenue trends
* Campaign timing
* Lag effects
* Long-term sales trends

---

## 5. Interaction Effects

Investigate whether the effectiveness of one strategy depends on another.

For example:

```text
Campaign Flyer × Sales Contact 2
```

or:

```text
Client Type × Campaign Type
```

---

## 6. Regularized Regression

Explore:

* Ridge Regression
* Lasso Regression
* Elastic Net

to address potential multicollinearity and improve model stability.

---

## 7. Robust Regression

Given the extreme skewness and outliers in `Amount Collected`, robust methods could be investigated, including:

* Huber Regression
* Quantile Regression
* Log-transformed target modeling

---

## 8. Interactive Business Dashboard

Deploy the analysis through:

* Streamlit
* Power BI
* Tableau

with interactive controls for:

* Client Type
* Campaign Type
* Sales Contact
* Competition
* Month

---

# 📁 Repository Structure

A clean repository could be organized as:

```text
Sales-Marketing-Strategy/
│
├── Sales_Marketing_Strategy_Making.ipynb
├── Campaign-Data.csv
├── consolidated_summary.csv
├── README.md
│
├── visualizations/
│
└── requirements.txt
```

---

# ▶️ Getting Started

## 1. Clone the Repository

```bash
git clone <repository-url>
cd Sales-Marketing-Strategy
```

## 2. Install Dependencies

```bash
pip install pandas numpy seaborn matplotlib scipy scikit-learn statsmodels
```

## 3. Open the Notebook

Open:

```text
Sales_Marketing_Strategy_Making.ipynb
```

using:

* Google Colab
* Jupyter Notebook
* JupyterLab

## 4. Run the Analysis

Execute the notebook sequentially to reproduce:

* Data preparation
* EDA
* Correlation analysis
* OLS regression
* Client-level regression
* Strategy analysis
* Consolidated recommendations

---

# 📄 Output

The notebook exports the final consolidated strategy table as:

```text
consolidated_summary.csv
```

The output contains:

```text
Variable
Return on Investment
Account Type
```

and provides a compact representation of the statistically significant strategy recommendations identified by the analysis.

---

# 🎓 Learning Outcomes

After completing this project, readers will understand how to:

* Translate a real-world marketing problem into a data analytics problem.
* Perform systematic exploratory analysis on business data.
* Segment customers according to business characteristics.
* Quantify relationships between marketing activities and revenue.
* Interpret regression coefficients and statistical significance.
* Compare strategy effectiveness across customer segments.
* Convert statistical findings into actionable business recommendations.
* Recognize the limitations of observational ROI analysis.
* Move from descriptive analytics toward prescriptive decision-making.

---

# 🤝 Contributions

Contributions are welcome!

Potential areas for contribution include:

* Advanced causal inference
* Predictive modeling
* Campaign optimization
* Time-series analysis
* ROI measurement
* Interactive dashboards
* Customer-level targeting
* A/B testing frameworks

Feel free to fork the repository, improve the analysis, and submit a pull request.

---

# ⭐ Support the Project

If you found this project useful for learning **Business Analytics**, **Marketing Analytics**, **Statistical Modeling**, or **Data-Driven Strategy**, consider giving the repository a **⭐ Star**.

---

# 📌 Conclusion

This project demonstrates how a relatively simple business dataset can be transformed into a **strategic decision-support framework**.

The analysis progresses from:

**Data Exploration → Client Segmentation → Correlation Analysis → OLS Regression → Segment-Level Statistical Analysis → ROI-Oriented Interpretation → Marketing Strategy**

The central finding is that **marketing effectiveness is not uniform across client types**. Different segments respond differently to campaigns and sales contacts, making **segmented resource allocation** more appropriate than applying a single strategy across the entire customer base.

The strongest relationships identified in the notebook include **Sales Contact 1 and Sales Contact 4 for Large Facilities, Sales Contact 2 across multiple segments, and Flyer Campaigns particularly for Medium Facilities**.

The project therefore provides a practical example of how **statistical analysis can be translated into actionable sales and marketing strategy**, while also establishing a strong foundation for future work involving causal inference, predictive modeling, experimentation, and automated campaign optimization.
