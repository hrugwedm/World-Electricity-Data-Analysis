# **Title**: World Electricity Data Analysis  (2000-2020)
---
![WhatsApp Image 2024-08-27 at 18 42 42](https://github.com/user-attachments/assets/8a1fe8e7-6ffa-44af-a612-41fc72d5fe4d)

### **Overview**
---
In this project, we analyzed electricity data for approximately 216 countries using data provided by the client. We began by extracting the data from the client’s database, which was in JSON format. The process involved transforming the JSON files into a long format, cleaning the data, filtering, and merging it with metadata. Finally, we saved the cleaned data into CSV files and used Power BI to generate valuable insights.



### **Objectives**
---

1) **Trends in Electricity Generation by Source**
2) **Comparison Between Electricty Generation by Nuclear Source and Income Group**
3) **Least Electrified Countires**
4) **Electricity Loss Across Different Regions**
5) **Comparison between Electricity Access of Urban to the Rural region**   

### **Tools used** 
---

1) Pandas library
2) JSON library
3) PowerBI Tool

### **Methodology**
---

1) **Data Acquisition**: The data was imported from the specified location.
2) **Data Conversion**: Initially in JSON format, the data was converted into a DataFrame. It was then melted to improve analysis and understanding, and finally saved in CSV format.
3) **Data Cleaning**: Using the Pandas library, the DataFrame was cleaned by removing duplicate values and unnecessary columns, as well as handling null and missing values.
4) **Data Visualization**: After cleaning, the data was loaded into Power BI to create visualizations and an interactive dashboard to uncover key insights.

### **Quick Summary**
---
**Here's a snippet of code that demonstrates the process described, followed by an explanation**

 
 ![code1](https://github.com/user-attachments/assets/f143c7c5-b8f4-464b-a481-5d46d5f32f1b)

 ![code2](https://github.com/user-attachments/assets/b6083e05-ff9a-424a-8c6c-4f4fb98bbefb)



1) **Load Metadata**:
The metadata file (Metadata.csv) is loaded into a DataFrame. This file contains additional information about countries, including Region and IncomeGroup.

2) **Define File Mapping**:
A dictionary file_info maps each JSON file to its corresponding new column name and CSV output file name.

3) **Load JSON Data**:
Each JSON file is read and converted into a DataFrame.

4) **Clean DataFrame**:
The first row of each DataFrame, which contains header information, is removed.
The remaining row is set as the new header.
Reset the DataFrame index.

4) **Melt DataFrame**:
The DataFrame is transformed from wide to long format using pd.melt(). The Year column is created, and the values are placed under a new column name as specified in file_info.

5) **Remove Null Values**:
Rows with null values in the Year and values columns are removed.
Year is converted to numeric and filtered to keep only years greater than 1999.

6) **Merge Metadata**:
The Country Code from the melted DataFrame is used to merge with the metadata DataFrame, adding Region and IncomeGroup columns.
Rows with null values in Region or IncomeGroup are removed.

7) **Reorder Columns**:
The columns are reordered to place the value column at the end of the DataFrame.

8) **Save to CSV**:
The cleaned and processed DataFrame is saved to a CSV file as specified in file_info.

9) **Completion**:
A message is printed to indicate that data processing is complete and the individual CSV files have been created.


### **PowerBI DashBoard**
---
![World_Electricity_Analysis_Dashboard](https://github.com/user-attachments/assets/eb8ba28f-38a2-49ac-8d92-f1dcfae308ed)



### **Conclusion**
---

1) **Global Electrification:**
   - Out of 216 countries analyzed, the world electrification rate stands at 80.71%.
   - Urban areas have significantly higher access to electricity (90.03%) compared to rural areas (76.23%).

2) **Electricity Production by Source:**
   - There has been a declining trend in electricity generation from oil and nuclear sources over the years.

3) **Nuclear Energy Production:**
   - High-income countries dominate nuclear energy production, contributing 74.71% of the total.
   - Upper-middle-income countries account for 16.83% of nuclear energy production.

4) **Electricity Loss:**
   - Sub-Saharan Africa experiences the highest electricity loss rate at 21.23%, indicating inefficiencies in the region's power distribution.

5) **Electricity Access Disparities:**
   - Significant gap in electricity access between urban and rural areas, especially in Sub-Saharan Africa, where rural access is only 28.65%.

6) **Least Electrified Countries:**
   - The least electrified countries are primarily located in Africa, with South Sudan having the lowest electrification rate at 3.68%.

7) **Geographical Insights:**
   - The world map highlights significant disparities in electricity access across different regions, with the highest access in North America and Europe and the lowest in Sub-Saharan Africa.

This analysis underscores the global disparities in electricity production and access, highlighting the need for targeted efforts to improve electrification, particularly in rural areas and lower-income regions.






### **Challenges Faced During The Project**
---

1) **Data Complexity:**

- **Data Format and Structure:** The initial data in JSON format is complex and nested, making it challenging to extract and convert into a usable DataFrame. Establishing a consistent structure during conversion is crucial.
- **Data Size:** Handling and processing large datasets from 216 countries leads to performance issues and requires significant computational resources.

2) **Data Cleaning:**

- **Null Values and Inconsistent Data Types:** Dealing with null values and inconsistencies in data types across various countries requires extensive cleaning efforts to ensure data accuracy.
- **Missing and Inconsistent Data:** In addition to null values, managing missing data and inconsistencies within the dataset is a significant challenge that demands careful attention during the cleaning process.
- **Handling Different Units:** Standardizing electricity data that may be provided in different units or formats across countries is necessary for consistency.

3) **Data Transformation:**

- **Merging Metadata:** Integrating metadata with the primary data is challenging, especially if the metadata is incomplete or inconsistently formatted.
- **Melting Data:** Converting the data into a long format (melting) introduces complexities, particularly in ensuring that key variables are correctly aligned.

4) **Data Relationship and Star Schema Design:**

- **Establishing Data Relationships:** Implementing a star schema in Power BI to handle data relationships can streamline the process. The star schema helps by defining fact tables and dimension tables, making it easier to establish clear relationships between them. This approach simplifies querying and reporting.
- **Star Schema Design:** Designing an effective star schema involves identifying and creating fact tables that store quantitative data (e.g., electricity production) and dimension tables that provide context (e.g., country details, time periods). Ensuring accurate and efficient data integration within this schema is critical.

5) **Visualization:**

- **Complex Visualizations:** Creating clear and informative visualizations in Power BI is challenging, especially when trying to display complex data in an easily digestible format.
- **Performance:** Power BI experiences performance issues when dealing with large datasets, particularly when creating interactive dashboards. Optimization of the star schema and efficient data modeling are required to enhance performance.

6) **Technical Integration:**

- **Power BI Integration:** Ensuring seamless integration of cleaned data from Pandas into Power BI for visualization poses technical challenges, particularly in maintaining data integrity and consistency.
- **Automation:** Automating the data processing pipeline, from extraction to visualization, is complex and requires careful orchestration of different tools and processes.

7) **Interpreting Results:**

- **Analyzing Trends:** Identifying meaningful trends and patterns in the data is difficult, especially when dealing with diverse countries with varying levels of electricity production and access.
- **Insight Generation:** Generating actionable insights from the visualized data requires a deep understanding of the underlying patterns and potential socio-economic implications.





