# ![human-resources](https://github.com/shashank297/Linkdin_Job_Analytics/assets/67503481/291364bf-388b-4dd8-931b-b6886c679a75)Company HR Recruitment Insights

## ![presentation](https://github.com/shashank297/Linkdin_Job_Analytics/assets/67503481/c18579cc-df95-4bea-980e-653c6b89c0d5)&nbsp; Introduction
This project focuses on extracting insights from a large dataset related to recruitment and placement activities in companies. The dataset provides valuable information that can be used by the HR department to gain knowledge about the recruitment process and market trends. The project involves several steps, including data scraping, data cleaning, exploratory data analysis (EDA), and building a dashboard using Tableau.

## ![folder](https://github.com/shashank297/Linkdin_Job_Analytics/assets/67503481/47317616-5fb6-43b0-9430-709ea820f528)&nbsp; Folder Structure Guide

| Files/Folder         | Description                                                             |
|---------------------|-------------------------------------------------------------------------|
| Notebooks Folder       | This folder includes the Jupyter notebook files that were utilized to scrape the data from the web.                                  |
| Dataset Folder      | Within this folder, there are two CSV tables that were acquired by scraping data from the web.                                   |
| Presentation Folder | This folder contains the presentation in PDF format.                                   |
| Dashboard File      | This is a Power BI-based dashboard that we developed to generate insights.                                   |


## ![waterfall](https://github.com/shashank297/Linkdin_Job_Analytics/assets/67503481/938da01a-c072-48f8-82b3-a39d2b7a5c3d)&nbsp; Project Steps
1. **Scraping Data from LinkedIn:** The data is collected from the professional networking platform LinkedIn using the Python library Beautiful Soup or a similar tool. The scraping script is available in the notebook named `Linkdin_scraping.ipynb`.

2. **Data Cleaning:** The collected data is cleaned and preprocessed to ensure its quality and consistency. The data cleaning process is performed in the notebook named `Data_Cleaning.ipynb`.

3. **Exploratory Data Analysis (EDA):** The cleaned data is analyzed to gain insights into various aspects of the recruitment process. The EDA is conducted using Python in the notebook named `EDA_Python.ipynb`.

4. **Dashboard Creation:** A dashboard is built using Tableau to visualize and present the extracted insights in an interactive and informative manner.


## ![data-analysis](https://github.com/shashank297/Linkdin_Job_Analytics/assets/67503481/a3a4d682-d34f-401a-b9dc-ec3b43be870a)&nbsp; Data Summary
The provided LinkedIn dataset consists of 7,927 rows and 15 columns, offering a comprehensive overview of job postings available on the platform. This dataset can be utilized for data analysis, visualization, and research purposes. The job postings encompass various roles such as Data Analyst, Machine Learning Engineer, IT Services, and IT Consulting, located in diverse locations worldwide, with varying salaries and work hours. The dataset provides information about the company, role responsibilities, and required skills for each job. It serves as a valuable resource for understanding job opportunities in different industries and locations.

## ![spreadsheet](https://github.com/shashank297/Linkdin_Job_Analytics/assets/67503481/5b85051e-7d5e-437a-a013-ac8d0215da17)&nbsp; Column Descriptions
The dataset contains the following columns:

| Column Name      | Description                                                        |
|------------------|--------------------------------------------------------------------|
| job_ID           | Unique identifier for each job listing.                             |
| designation      | The title or position of the job.                                  |
| company_id       | Unique identifier for each company.                                |
| name             | Name of the company offering the job.                              |
| work_type        | Indicates whether the job is remote or on-site.                    |
| involvement      | The level of involvement required for the job (e.g., Full-time, Part-time). |
| employees_count  | The count of employees in the company.                             |
| total_applicants | The total number of applicants for the job.                        |
| linkedin_followers | The number of followers on the company's LinkedIn page.           |
| job_details      | Description of the job and its responsibilities.                   |
| details_id       | Unique identifier for the job details.                             |
| industry         | The industry or sector to which the company belongs.               |
| level            | The experience level or seniority associated with the job.         |
| City             | The city where the job is located.                                 |
| State            | The state where the job is located.                                |


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

## ![data-cleaning](https://github.com/shashank297/Linkdin_Job_Analytics/assets/67503481/3c3cce7b-e566-41f0-9383-5b085bdd5fc6)&nbsp; Data Cleaning and Preprocessing
- Remove duplicate values from the DataFrame.
- Replace or remove null values based on analysis.
- Assign unique identifiers to the "company_id" column based on the order of appe&nbsp;arance in the DataFrame.
### Handling missing values
  - All the column has the null value except `job_ID` and `company_id`
  - `job` has **27** Null values -- This column has the less null value we can remove all the null values
  - `location` has **27** Null values -- This column also has less null value so we can directly remove all
  - `company_name` has **28** Null values -- This column also has less null value so we can directly remove all
  - `work_type` has **132** Null values -- Since the data in this column object type we can replace it with the mode 
  -`full_time_remote` has **67** Null values -- This column also has less null value so we can directly remove all
  - `no_of_employ` has **229** Null values -- This column also has less null value so we can directly remove all
  -`no_of_application` has **33** Null values -- either we can remove it or replace it with the 0 because i know for a fact there is null values because at that time there is no application
  -`posted_day_ago` has **6** Null values -- This column also has less null value so we can directly remove all
  - `Hiring_person` has **1686** Null values -- In this we are going to replace the null values with 'Not Available'
  -`linkedin_followers` has **2313** -- In this column there is a posiblity there is 0 followers so null is placed insist of it but i am going to replace it with the mean.
  -`job_details` has **44** Null values -- This column also has less null value so we can directly remove all
#### steps involved in the data cleaning process
- Check the top 5 and last 5 rows of the DataFrame.
- Check for null values and calculate their percentage column-wise.
- Check the data types and count of non-null values in the DataFrame.
- Check for duplicate values in the dataset.
- Create a copy of the DataFrame.
- Remove duplicate values and reset the index.
- Assign a unique identifier to each company based on their order of appearance in the DataFrame.
- Assign unique numerical identifiers to companies and jobs based on their order of appearance in the DataFrame.
- Drop unnecessary columns.`'location','posted_day_ago','Hiring_person','alumni','hiring_person_link'`
- Remove unwanted strings from the DataFrame.
- Separate columns and handle null values generated.
- Replace null values in the "company_sector" and "job_level" columns.
- Remove null values in the "posted_day_ago" column.
- Separate the city and state from the "location" column.
- Install the geopy module.
- Create functions to find states and cities based on given cities.
- Apply the functions to extract state and city information.
- Check for noise values in the "City" and "State" columns.
- Replace noise values in the "State" column.
- Identify noise in the "job" column and categorize it accordingly.



## Insights
The following are some of the key insights obtained from the analysis:

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

## Conclusion
This project provides valuable insights into the recruitment process and market trends. The extracted information can be utilized by the HR department to make informed decisions and optimize their recruitment strategies. The interactive dashboard created using Tableau enables easy exploration and visualization of the data.

For more detailed information and visualizations, please refer to the respective notebooks and the final dashboard.

## Quick Overview of EDA in Python
- For indept  detail checkout the `Python_EDA Notebook`
### Univariate Analysis
In this section, both categorical and numerical columns are analyzed separately.
**Task in this section:-**
- First Seprate the  Numarical and Categorical clolumns for the analysis
- In the categorical columns:-
  - Check the Frequency distribution for the each categorical columns.
  - Plot the Countplot and Pie chat side by side for each columns
  - In some categorical columns unique category count is high for those columns we are going to disply Top 10 category.
- In the Numarical Columns:-
 - Check the Central Tendency for each numarical columns Measures `Mean, Median, Mode`
 - Check for the Dispersion Measures with the help of `Discribe Function`
 - Check For the Descriptive Statistics such as `skewness and kurtosis`
 - Plot the `Histplot` and `kdeplot` for the each numarical columns for visual representation
 
#### Univariate Analysis of Work_type
 ![chat 1](https://github.com/shashank297/Linkdin_Job_Analytics/assets/67503481/34813d10-3714-4eeb-8b66-2826f43239a4)

