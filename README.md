# **Title**: World Electricity Data Analysis
![WhatsApp Image 2024-08-27 at 18 42 42](https://github.com/user-attachments/assets/8a1fe8e7-6ffa-44af-a612-41fc72d5fe4d)

### **Overview**
In this project, we analyzed electricity data for approximately 216 countries using data provided by the client. We began by extracting the data from the client’s database, which was in JSON format. The process involved transforming the JSON files into a long format, cleaning the data, filtering, and merging it with metadata. Finally, we saved the cleaned data into CSV files and used Power BI to generate valuable insights.



### **Objectives**

1) **Trends in Electricity Generation by Source**
2) **Comparison Between Electricty Generation by Nuclear Source and Income Group**
3) **Least Electrified Countires**
4) **Electricity Loss Across Different Regions**
5) **Comparison between Electricity Access of Urban to the Rural region**   

### **Tools used** :

1) Pandas library
2) JSON library
3) PowerBI Tool

### **Methodology**

1) **Data Acquisition**: The data was imported from the specified location.
2) **Data Conversion**: Initially in JSON format, the data was converted into a DataFrame. It was then melted to improve analysis and understanding, and finally saved in CSV format.
3) **Data Cleaning**: Using the Pandas library, the DataFrame was cleaned by removing duplicate values and unnecessary columns, as well as handling null and missing values.
4) **Data Visualization**: After cleaning, the data was loaded into Power BI to create visualizations and an interactive dashboard to uncover key insights.

### **Quick Summary**
**Here's a snippet of code that demonstrates the process described, followed by an explanation**
 
 ![code1](https://github.com/user-attachments/assets/f143c7c5-b8f4-464b-a481-5d46d5f32f1b)

 ![code2](https://github.com/user-attachments/assets/b6083e05-ff9a-424a-8c6c-4f4fb98bbefb)



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
