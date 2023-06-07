# Company HR Recruitment Insights

## Introduction
This project focuses on extracting insights from a large dataset related to recruitment and placement activities in companies. The dataset provides valuable information that can be used by the HR department to gain knowledge about the recruitment process and market trends. The project involves several steps, including data scraping, data cleaning, exploratory data analysis (EDA), and building a dashboard using Tableau.

## Project Steps
1. **Scraping Data from LinkedIn:** The data is collected from the professional networking platform LinkedIn using the Python library Beautiful Soup or a similar tool. The scraping script is available in the notebook named `Linkedin.ipynb`.

2. **Data Cleaning:** The collected data is cleaned and preprocessed to ensure its quality and consistency. The data cleaning process is performed in the notebook named `Data_Cleaning.ipynb`.

3. **Exploratory Data Analysis (EDA):** The cleaned data is analyzed to gain insights into various aspects of the recruitment process. The EDA is conducted using Python in the notebook named `EDA_Python.ipynb`.

4. **Dashboard Creation:** A dashboard is built using Tableau to visualize and present the extracted insights in an interactive and informative manner.

## Insights
The following are some of the key insights obtained from the analysis:

### Data Cleaning
- The "total_applicants" column contains noise, such as values like "days," "day," "hour," and "minute."
- The column type is currently Object, and it needs to be converted into a numeric type using the `to_numeric` function.
- The missing values (NaN) in the column are replaced with the mean value.

### Univariate Analysis
In this section, both categorical and numerical columns are analyzed separately.

#### Categorical Columns
- Frequency distribution, count plots, and pie charts are generated for each categorical column.
- For categorical columns with a high number of unique categories, only the top 10 categories are displayed.
- Insights are provided for the columns: "work_type," "involvement," "level," "designation," "Name" (company name), "Industry," "City," and "State."

#### Numerical Columns
- Measures of central tendency (mean, median, mode) are calculated for each numerical column.
- Dispersion measures are obtained using the `describe` function.
- Descriptive statistics such as skewness and kurtosis are analyzed.
- Histograms and KDE plots are generated for each numerical column for visual representation.

#### Work Type and Involvement
- The "work_type" column has three unique categories: Onsite, Remote, and Hybrid.
- The count of onsite and remote jobs is almost the same, with onsite jobs slightly higher.
- The "involvement" column has four unique categories: Full-Time, Part-Time, Internship, and Contract.
- Full-Time has the majority share (93.6%), followed by Contract (3.4%).

#### Level and Designation
- The "level" column has seven unique categories: Associate, Mid-Senior level, Not Available, Entry level, Director, Executive, and Internship.
- Mid-Senior level has the highest share (52.5%), followed by Not Available (36.8%).
- The "designation" column has a high number of unique categories, and the top 10 categories are identified.
- Data Analyst is the most common designation (12.93%), followed by Java Developer (11.97%).

#### Company, Industry, City, and State
- The "Name" column (company name) has a high number of unique categories, and the top 10 companies are identified.
- Epam Anywhere offers the most jobs (11.5%), followed by IBM (10.9%).
- The "Industry" column has a high number of unique categories, and the top 10 industries are identified.
- Information Technology and Services is the most common industry (42.7%), followed by Computer Software (18.9%).
- The "City" column has a high number of unique categories, and the top 10 cities are identified.
- Warsaw has the highest number of job opportunities (12.4%), followed by Bengaluru (11.6%).
- The "State" column has a high number of unique categories, and the top 10 states are identified.
- Maharashtra has the highest number of job opportunities (14.7%), followed by Karnataka (11.6%).

### Bivariate Analysis
In this section, the relationships between different columns are analyzed.

#### Experience vs. Salary
- The "experience" column is divided into four categories: Less than 1 year, 1-3 years, 4-6 years, and 7+ years.
- The salary range for each category is analyzed using box plots.

#### Job Type vs. Salary
- The relationship between "work_type" and salary is analyzed.
- Onsite jobs tend to have higher salaries compared to remote and hybrid jobs.

## Conclusion
This project provides valuable insights into the recruitment process and market trends. The extracted information can be utilized by the HR department to make informed decisions and optimize their recruitment strategies. The interactive dashboard created using Tableau enables easy exploration and visualization of the data.

For more detailed information and visualizations, please refer to the respective notebooks and the final dashboard.

