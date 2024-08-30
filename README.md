# **Title**: World Electricity Data Analysis
![WhatsApp Image 2024-08-27 at 18 42 42](https://github.com/user-attachments/assets/8a1fe8e7-6ffa-44af-a612-41fc72d5fe4d)

### **Overview**
This script processes JSON data files, transforms them into a long format, merges metadata, and saves the cleaned data to CSV files. The process includes several key steps such as data cleaning, melting, filtering, and merging.



### **Objectives**

1) **Trends in Electricity Generation by Source**
2) **Comparison Between Electricty Generation by Nuclear Source and Income Group**
3) **Least Electrified Countires**
4) **Electricity Loss Across Different Regions**
5) **Comparison between Electricity Access of Urban to the Rural region**   

### **Tools used** :

1) Pandas library
2) NumPy library
3) PowerBI Tool

### **Methodology**

1) **Data Acquisition**: Data is imported from the given location.
2) **Data Conversion**: Data is in JSON format, so data is first converted into DataFrame using File Handeling.
3) **Data Cleaning**: with the help of pandas library dataFrame is cleaned. In these duplicated values and unnecessary columns are removed, null and missing values are also removed or replace.
4) **Data Visualisation**: after cleaning Data is load in PowerBI for making visuals and interractive Dashboard for finding key insights.

### **Quick Summary**

**Steps Performed**

**Load Metadata**:
The metadata file (Metadata.csv) is loaded into a DataFrame. This file contains additional information about countries, including Region and IncomeGroup.

**Define File Mapping**:
A dictionary file_info maps each JSON file to its corresponding new column name and CSV output file name.

**Process Each JSON File**:

**Load JSON Data**:
Each JSON file is read and converted into a DataFrame.

**Clean DataFrame**:
The first row of each DataFrame, which contains header information, is removed.
The remaining row is set as the new header.
Reset the DataFrame index.

**Melt DataFrame**:
The DataFrame is transformed from wide to long format using pd.melt(). The Year column is created, and the values are placed under a new column name as specified in file_info.

**Remove Null Values**:
Rows with null values in the Year and values columns are removed.
Year is converted to numeric and filtered to keep only years greater than 1999.

**Merge Metadata**:
The Country Code from the melted DataFrame is used to merge with the metadata DataFrame, adding Region and IncomeGroup columns.
Rows with null values in Region or IncomeGroup are removed.

**Reorder Columns**:
The columns are reordered to place the value column at the end of the DataFrame.

**Save to CSV**:
The cleaned and processed DataFrame is saved to a CSV file as specified in file_info.

**Completion**:
A message is printed to indicate that data processing is complete and the individual CSV files have been created.

**Notes**
Ensure that the JSON files are formatted correctly and the columns match the expected names.
The Metadata.csv file should have columns Country_Code, Region, and IncomeGroup for successful merging.
The script handles null values and ensures only relevant years and data are included in the final CSV files.
