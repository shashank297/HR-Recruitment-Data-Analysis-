# Company HR Recruitment Insights

## Introduction
This project focuses on extracting insights from a large dataset related to recruitment and placement activities in companies. The dataset provides valuable information that can be used by the HR department to gain knowledge about the recruitment process and market trends. The project involves several steps, including data scraping, data cleaning, exploratory data analysis (EDA), and building a dashboard using Tableau.

## Project Steps
1. **Scraping Data from LinkedIn:** The data is collected from the professional networking platform LinkedIn using the Python library Beautiful Soup or a similar tool. The scraping script is available in the notebook named `Linkedin.ipynb`.

## Data Info
## Data Summary
The provided LinkedIn dataset consists of 7,927 rows and 15 columns, offering a comprehensive overview of job postings available on the platform. This dataset can be utilized for data analysis, visualization, and research purposes. The job postings encompass various roles such as Data Analyst, Machine Learning Engineer, IT Services, and IT Consulting, located in diverse locations worldwide, with varying salaries and work hours. The dataset provides information about the company, role responsibilities, and required skills for each job. It serves as a valuable resource for understanding job opportunities in different industries and locations.

## Column Descriptions
The dataset contains the following columns:

- `job_ID`: Unique identifier for each job posting.
- `job`: The title of the job posting.
- `location`: The location of the job posting.
- `company_id`: The unique identifier for the company offering the job.
- `company_name`: The name of the company offering the job.
- `work_type`: The type of work offered (e.g., full-time, part-time, etc.).
- `full_time_remote`: Indicates if the job is a full-time remote position.
- `no_of_employ`: The number of employees at the company offering the job.
- `no_of_application`: The number of applications received for the job.
- `posted_day_ago`: The number of days ago the job was posted.
- `alumni`: Indicates if the job posting is for alumni of a certain organization.
- `Hiring_person`: The name of the person responsible for hiring for the job.
- `linkedin_followers`: The number of LinkedIn followers of the hiring person.
- `hiring_person_link`: A link to the LinkedIn profile of the hiring person.
- `job_details`: Detailed information about the job, including responsibilities and requirements.

## Issues with the Dataset
The dataset exhibits several issues that require attention:

1. Dirty Data:
   - The `job` column contains unnecessary information such as yearly package, technology, company name, and work type (remote) added in the title.
   - The `no_of_application` column includes values like 'hours' and 'minutes' that should not be present.

2. Consistency:
   - In the `posted_day_ago` column, time is added in the form of strings, such as '9 hours' and '8 minutes'.
   - The `Alumni` column includes strings with the count value ('company alumni').
   - The `Hiring_person` column contains nicknames added within parentheses.

3. Completeness:
   - The `company_id` column is completely blank.

4. Validity:
   - The `linkedin_followers` column contains the string 'linkedin_followers' with numbers, where numbers are separated by ' , '.
   - The `Full_time_remote` column combines involvement and level in one column, separated by '·'.
   - The `No_of_employ` column combines employees_count and industry in one column, with the 'employees' string added unnecessarily, separated by '·'.
   - The `location` column combines country, state, and city in one column, separated by ','.

5. Messy Data:
   - In the `Job` column, some entries start with capital letters while others are in small letters.
   - The `company_name` column has inconsistencies in the name, with some letters starting with a lowercase and others with a capital letter.
   - There are 2,084 duplicate values found in the dataset.

## Exploratory Data Analysis (EDA) Functions in Python
During the data cleaning process, the following EDA functions in Python can be applied:
- `head` and `tail`: Display the top or bottom rows of the dataset.
- `sample`: Retrieve a random sample of rows from the dataset.
- `info`: Provide information about the dataset, including column data types and non-null values.
- `isnull`: Identify missing values in the dataset.
- `duplicated`: Identify duplicated rows in the dataset.
- `describe`: Generate descriptive statistics of the numerical columns.

These functions will assist in understanding the structure and characteristics of the data, enabling effective data cleaning and exploration.

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

