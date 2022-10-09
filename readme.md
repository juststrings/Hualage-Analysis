# Introduction
Haulage Analysis for a fictional haulage bussiness.


# Project Name: Hualage Analysis (Deriving insights From Data)
![homepage](https://user-images.githubusercontent.com/92920156/194767939-de70c762-1380-4633-9b3a-4271b7950b81.jpg) <br>
image source: [google.com](https://www.google.com/) <br>
all rights belongs to the orignal creator

# Problem Objective <br>

Data Analysis using Power BI<br>
Creating a Reports that gives the insights on a fictional haulage bussiness covering the employee productivity, most moved product(most profitable product), revenue, expenses and profit generated by product,drivers and depot and destination visited. 
Including a year over year analysis.

# Tools used in actualizing the project

Power Bi<br>
Excel<br>
Notepad<br>


# Data Sourcing
The dataset was provided by my mentor <br>
[Sulaiman Lukman](https://www.linkedin.com/in/sulaimanlukmanadeleke/) <br>
## The dataset includes 5 excel sheets;
- Closed trip list: This icludes more than 7 columns: 
    - Trip No
    - Date
    - Time
    - Truck No
    - Driver Name
    - Destination
    - Actual Arriver Date   
- Open trip list:  This icludes more than 7 columns: 
    - Trip No
    - Date
    - Time
    - Truck No
    - Destination
    - Actual Arriver Date 
- Trip Rates:  This icludes more than 9 columns: 
    - Load Port
    - Destinatiom
    - Product Category
    - Trip Rate
    - Loading Expenses
    - Trip Allowance
    - Union Fees
    - Parking Fees
    - Capacity
    - Product
- Truck Available: This icludes more than 7 columns: 
    - Truck No
    - Product Type
    - Capacity
    - Truck Classification
    - Aquilla Status
    - Status(Availability)
    - Depot Location
- Truck List: This icludes more than 7 columns: 
    - Truck No
    - Product Type
    - Capacity
    - Truck Classification
    - Aquilla Status
    - Status(Availability)
    - Depot Location
    - Registration Year
    - Use column
 
---

# Data Transformation & Modeling

## Data Cleaning & Transformation
### - Step 1
After importing the datasets using the import method in power bi:<br>
Then, the first task i did was to clean the data by renaming misspelt values in columns, changing data-types and splitting the date-time columns (in tables that had them) to increase performance.<br>
<br/>
![applied steps 1](https://user-images.githubusercontent.com/92920156/194769932-eaf39578-461a-4dca-b480-a8b502cdd211.jpg)

Then I used excel to create a new table including just a column named total truck trip by copy the truck trip id from both closed and open trips into a single column. This was done to create a better relationship between this two columns.<br>
### Note
I didn't append both tables because they had little structural differences.
Then i imported this newly created table which i named destinations into power bi (note: I later used this table as my fact table. Forgive me for the wrong choice of name)

### - Step 2
I created a primary key in all the initial five tables to enable creating relationship with the destination table easier.<br>
Then I merged the already imported Destination tables (fact table) with other tables to create a table with more than 10 columns aside the secondary keys. <br>
Which Includes:
- Truck Trip Id
- Total Truck No
- Trip Status (conataining value indicating if the trip is closed or opem)
- Product type
- Truck Capacity
- Truck Classification 
- Depot Location
- Trip Rate
- Loading Expenses
- Trip Allowances
- Union Fees
- Destination (three columns- Destination name, Latitude and Longitude)
- Secondary Keys
<br>
<br>
![Destination3](https://user-images.githubusercontent.com/92920156/194777110-b97037cb-006b-4fc9-a9e8-cbaf64182686.jpg)



### - Step 3
I created a date table using blank query and M code.<br>
I also disabled power bi's defualt date table by setting my created table as my date table

## Data Modeling
I enabled many to one relationship and cross filter direction from the destination table (fact table) to other tables using their respective keys.
<br>
<br>
![model](https://user-images.githubusercontent.com/92920156/194776944-7cab5945-3346-414e-9f5a-8e61d43288d4.jpg)




