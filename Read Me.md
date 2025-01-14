![CustomerChurn](src/Customer-Churn.png)

## End-to-End Churn Analysis Portfolio Project

### 1. Project Overview
This project focuses on building an end-to-end churn analysis solution for a telecom company. It involves creating an ETL process, analyzing customer data, and developing a Power BI dashboard. The solution visualizes customer demographics, payment details, and service usage while predicting potential churners using machine learning, enabling proactive strategies to improve customer retention.
________________________________________

### 2. What is Churn Analysis and Why is it Important?
Churn analysis identifies customers likely to leave a business by analyzing patterns in customer data. For telecom companies, it is critical as customer acquisition costs are high, and retaining existing customers ensures steady revenue. By understanding churn drivers, companies can implement targeted strategies to enhance customer satisfaction and loyalty.
________________________________________

### 3. Project Target
The project aims to:
    
    •	ETL Process: Extract, transform, and load customer data into a database for structured analysis.
    
    •	Data Visualization: Create a Power BI dashboard to analyze customer demographics, geography, and account details.
   
    •	Machine Learning: Develop an algorithm to predict churn.
    
    •	Churn Insights: Provide actionable insights to reduce churn and improve customer retention.

________________________________________

### Stage 1: Data Ingestion via Google Colab
1. Connecting Google Drive to Google Colab
    To start, I uploaded the dataset (CSV file) to my Google Drive. Then, I connected Google Colab to my Drive to access the file:
    
    •	Mounted my Drive using the command from google.colab import drive; drive.mount('/content/drive').
    
    •	Navigated to the folder containing my CSV file.
2. Loading the Data Using Pandas
    Next, I used the Pandas library to load the data:
    
    •	Imported Pandas: import pandas as pd.
    
    •	Loaded the CSV: df = pd.read_csv('/content/drive/MyDrive/dataset.csv').
    I checked the first few rows using df.head() to ensure the data was loaded correctly.
3. Initial Data Cleaning
    I inspected the dataset for null values and inconsistencies:
    
    •	Used df.info() to get an overview of the columns and data types.
    
    •	Checked for missing values: df.isnull().sum().
    
    •	Filled missing values where appropriate and standardized column names for consistency.

![ETL Google Colab](/src/ETL%20Google%20Colab%20&%20Drive.JPG)
________________________________________

### Stage 2: Data Transformation with Pandas
1. Creating Key Metrics
    To prepare the data for analysis, I derived key metrics:
    
    •	Calculated Total Customers, Churn Rate, and New Joiners using Pandas functions like groupby() and count().
    
    •	Added new columns, such as Churn_Status, using conditional logic:
    python
    Copiar código
    df['Churn_Status'] = df['Customer_Status'].apply(lambda x: 1 if x == 'Churned' else 0)
2. Preparing Data for Visualization
    I saved the transformed dataset as a new CSV for use in Power BI:
    
    •	Saved the file: df.to_csv('/content/drive/MyDrive/transformed_data.csv', index=False).
________________________________________

### Stage 3: Building the Power BI Architecture
1. Importing the Dataset
    In Power BI, I imported the CSV file generated from Google Colab:
    
    •	Used the “Get Data” option to load the file.
    
    •	Ensured that the data types matched my transformations in Pandas.
2. Creating a Data Model
    To organize my analysis, I created a clean architecture:
    
    •	Set up relationships between tables (if applicable).
    
    •	Filtered the data using slicers for attributes like Customer Status, Age Group, and Monthly Charges.
________________________________________

### Stage 4: Visualization in Power BI
1. Designing the Dashboard
    I focused on creating visually appealing and insightful dashboards:
    
    •	Used Power BI’s color palette to align with the project theme: #4A44F2, #9B9FF2, #F2F2F2, #A0D1FF.
    
    •	Created visuals such as:
    
    o	Bar charts to display customer churn by demographic or geographic groups.
    
    o	Pie charts to highlight churn rate by customer profile.
    
    o	Line graphs to analyze trends over time.
2. Insights and Analysis
    I analyzed the trends and answered key questions about customer churn:
    
    •	Identified high-risk customer segments by filtering demographics, services, and payment preferences.
    
    •	Highlighted areas for targeted marketing campaigns, such as customers with short tenure or specific contract types.

![ChurnVisualization](/src/Churn%20Analysis%20Summary.JPG)
________________________________________

### Stage 5: Driving Business Insights
Using the visualizations, I derived actionable insights:
•	Demographic and geographic trends helped understand where churn was highest.

•	Payment and account data revealed which payment methods were more likely to result in churn.

•	Service data highlighted which products or plans correlated with higher churn rates.
These insights can guide retention strategies, such as offering discounts or improved services to at-risk customers.


