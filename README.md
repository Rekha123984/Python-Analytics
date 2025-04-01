# Data Analytics Project

## Project Overview
This project focuses on analyzing different datasets to derive insights using various statistical techniques and visualization methods. Multiple datasets were used to address different analytical scenarios, and various charts and hypothesis tests were applied to uncover meaningful patterns.

## Tools & Libraries Used
- **Python** (for data manipulation, analysis, and visualization)
- **Pandas** (for data cleaning and processing)
- **Matplotlib** (for data visualization)
- **Seaborn** (for advanced visualizations)
- **Statistics** (for mathematical calculations)
- **Scipy** (for statistical hypothesis testing)

## Data Analysis Techniques Used
1. **Data Cleaning & Preprocessing**
   - Handling missing values
   - Data transformation
   - Removing duplicates

2. **Exploratory Data Analysis (EDA)**
   - Summary statistics
   - Data distribution analysis
   - Correlation matrix
   - Feature relationships

3. **Data Visualization**
   - Bar charts
   - Line charts
   - Scatter plots
   - Heatmaps

4. **Hypothesis Testing**
   - **Z-Test**: Used to compare sample means with a known population mean. This is useful when the sample size is large, and the population standard deviation is known.
   - **T-Test**: Applied to compare means between two independent or paired samples. It helps in determining if there is a significant difference between the means of two groups.
   - **Chi-Square Test**: Used to check the association between categorical variables. This test is beneficial for analyzing survey results or customer segmentation data.
   - **ANOVA (Analysis of Variance)**: Applied to compare means across multiple groups. It is used when analyzing differences across multiple categories, such as comparing sales performance across different regions.

## Analytics & Insights
The project leverages statistical analysis and visualization to interpret different datasets effectively. Key analytical steps include:
- Identifying trends in numerical and categorical data.
- Performing hypothesis tests to validate assumptions about data relationships.
- Using correlation analysis to determine dependencies between variables.
- Visualizing data patterns through charts and graphs to enhance understanding.
- Deriving business insights, such as customer behavior patterns, market trends, and operational efficiencies.

Each dataset was analyzed based on its specific context. For instance, sales data was explored to find revenue patterns, while demographic data was examined for population insights. The use of hypothesis testing helped in making data-driven decisions by validating statistical significance.

## Charts & Code Implementation
Different methods were used to generate charts based on the dataset structure:
- **Using Pandas to Read Data:**
  - For structured datasets like CSV files, `pandas.read_csv()` was used to load data before visualization.
  - Example:
    ```python
    import pandas as pd
    import matplotlib.pyplot as plt
    
    df = pd.read_csv("data.csv")
    df.plot(kind='bar', x='Category', y='Value')
    plt.show()
    ```
- **Using `with open` for File Handling:**
  - When working with JSON or csv, data was loaded using `with open()`.
  - Example:
    ```python
    import pandas as pd
    import csv
    from collections import defaultdict

    Education_sum=defaultdict(int)
    Education_count=defaultdict(int)

    with open("HR-Employee-Attrition.csv","r") as csvfile:
      plot=csv.reader(csvfile,delimiter=",")

      next(plot)

      for rows in plot:
        EducationField=(rows[7])
        Education=int(rows[6])
        Education_sum[EducationField]+=Education
        Education_count[EducationField]+=1

    # Calculate the average education level per field
    Average_Education= {field: Education_sum[field] / Education_count[field] for field in Education_sum}

    x=list(Average_Education.keys())
    y=list(Average_Education.values())

    plt.figure(figsize=(10,6))
    plt.plot(x,y,color="blue",marker="o",label="HR-Employee-Attrition")
    plt.xlabel("EducationField")
    plt.ylabel("Education_count")
    plt.title("HR-Employee-Attrition")
    plt.xticks(rotation=45)
    plt.grid(True)
    plt.show()

    ```
- **Seaborn for Advanced Visualization:**
  - Heatmaps, scatter plots, and density plots were created using Seaborn.
  - Example:
    ```python
    import seaborn as sns
    
    sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
    plt.show()
    ```

These different approaches allowed flexibility in visualizing structured and unstructured data efficiently.

## How to Run the Project
1. Install the required libraries using:
   ```bash
   pip install pandas matplotlib seaborn scipy
Open and run the Jupyter Notebook (Python_Analytics.ipynb).

Follow the step-by-step analysis provided in the notebook.

## Conclusion
This project demonstrates the power of data analytics in uncovering insights from diverse datasets. By leveraging visualization and hypothesis testing, significant patterns and business-relevant conclusions can be drawn.
