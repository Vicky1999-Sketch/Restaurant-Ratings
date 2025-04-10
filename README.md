# Restaurant-Ratings
![1a35a810-eada-4f73-a072-107c53f43b6b](https://github.com/user-attachments/assets/b1ae2868-096c-4f9a-ba54-64b8ae1f6e7d)

## I. Introduction
The restaurant rating dataset contains information about restaurants in Mexico. It is the result of a customer survey conducted in 2012 to collect details about each restaurant, their cuisines, their consumers, and consumer preferences. 
The aim of this dataset is to derive meaningful insights that can aid business entrepreneurs and investors in making more informed decisions.

## II. Data Description
The dataset comprises five tables:
1. **Consumer Table**  
   - **Columns (14)**: Consumer ID, City, State, Country, Latitude, Longitude, Smoker, Drink Level, Transportation Method, Marital Status, Children, Age, Occupation, Budget  
   - **Rows**: 138
2. **Consumer Preference Table**  
   - **Columns (2)**: Consumer ID, Preferred Cuisine  
   - **Rows**: 330
3. **Rating Table**  
   - **Columns (5)**: Consumer ID, Restaurant ID, Overall Rating, Food Rating, Service Rating
   - **Rows**: 1161
4. **Restaurant Table**  
   - **Columns (13)**: Restaurant ID, Name, City, State, Country, Latitude, Longitude, Alcohol Service, Smoking Allowed, Price, Franchise, Area, Parking  
   - **Rows**: 130
5. **Restaurant Cuisine Table**  
   - **Columns (2)**: Restaurant ID, Cuisine  
   - **Rows**: 112

## III. Problem Statement
1. What can you learn from the highest-rated restaurants? Do consumer preferences affect ratings?  
2. What are the consumer demographics? Do they indicate a bias in the data sample?  
3. Are there any demand and supply gaps that can be exploited in the market?  
4. If you were to invest in a restaurant, which characteristics would you be looking for?

## IV. Methodology
Power BI was used for cleaning, modeling, analyzing, and visualizing the data.

## V. Data Transformation / Cleaning
Data cleaning was conducted in Power Query. Key steps included:
1. **Handling Null Values**  
   - **Smoker**: Replaced nulls with 'No' (modal value)  
   - **Transportation**: Used fill down  
   - **Marital Status**: Replaced nulls with 'Single'  
   - **Children**: Replaced nulls with 'Independent'  
   - **Occupation**: Replaced nulls with 'Independent'  
   - **Budget**: Used fill down
2. **Validated Data Types**  
   - Confirmed all columns had correct data types.
3. **Adjusted Headers**  
   - Used the first row as header in the Consumer Preference table.
4. **Removed Irrelevant Data**  
   - Dropped Zip Code from the Restaurant table due to excessive missing values and irrelevance.
5. **Improved Readability**  
   - Changed rating scale (0,1,2) in the Ratings table to ‘Unsatisfactory’, ‘Satisfactory’, and ‘Highly Satisfactory’.

   ## VI. Data Modeling

### A. Fact Table:  
- **Ratings Table**: Includes IDs and ratings (later converted to text for better interpretation).

### B. Dimension Tables:
1. **Consumer Table** – One-to-many relationship with the fact table  
2. **Restaurant Table** – One-to-many relationship with the fact table  
3. **Consumer Preference Table** – Many-to-many relationship  
4. **Restaurant Cuisine Table** – Many-to-many relationship

![RR Modelling](https://github.com/user-attachments/assets/ff312c55-17d4-481d-b413-8b371579f4cf)

## DAX Measures and Calculated Columns Created
- Number of Customers  
- Number of Restaurants  
- Highest Rated Restaurants (by Overall Rating)  
- Number of Cities  
- Number of Restaurant Cuisines  
- Age Category Column

## VII. Findings & Insights

### 1. **Top 5 Highest-Rated Restaurants**

![RR HRR](https://github.com/user-attachments/assets/0cb38ff0-746f-4014-834f-d1fc089b47a1)

![RR HRRD](https://github.com/user-attachments/assets/52bfb8da-ca1c-4b6a-935c-699c6d701883)

**Findings**
- Tortas Locas Hippocampo  
- Puesto De Tacos  
- La Cantina Restaurante  
- Cafetería y Restaurante El Pacífico  
- El Rincón de San Francisco  

**Insight:**  
All five are located in San Luis Potosi, indicating that **location significantly influences customer satisfaction**. Only two serve alcohol, and just one allows smoking.

### Do consumer preferences affect ratings?

![RR HRC](https://github.com/user-attachments/assets/98900f9f-a20f-4e34-8f83-bbdeb9ed3d43)

**Insights** 
While Mexican cuisine received high ratings overall, the top-rated restaurant (Tortas Locas Hippocampo) specialized in Fast Food, which wasn't among the top 10 cuisines by rating. This suggests that **consumer preferences alone do not determine restaurant ratings**—factors like service quality, or even value for money may have greater influence.

### 2. **Consumer Demographics**

Occupation                             | Budget                                |Age                                    |Marital Status
:-------------------------------------:|:-------------------------------------:|:-------------------------------------:|:------------------------------------:

![RR Occupation](https://github.com/user-attachments/assets/412e9424-0bb1-4cd9-825b-d173a27832a2)|
![RR Budget](https://github.com/user-attachments/assets/dfd24932-9941-4df7-9864-8ae9ff1f3077)|
![RR Age](https://github.com/user-attachments/assets/cdddce77-f5dd-4340-8dd1-9c5b5a9bf458)
![RR MS](https://github.com/user-attachments/assets/6c707719-e12e-4f1d-a428-fff623013c76)|







