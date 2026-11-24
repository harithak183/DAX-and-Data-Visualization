# DAX-and-Data-Visualization
A practical Power BI assignment focused on DAX calculations and data visualization, demonstrating skills in creating calculated measures, analyzing business data, and developing insightful visual reports to support data-driven decision-making.


### 1. Load the Amazingcart.xlsx file and create a Clustered Column chart that can explain the countries with the highest order placements from the data table.

## Clustered Column Chart – Total Orders by Country

1. **Data Import** – Import the `Amazingcart.xlsx` dataset into Power BI using the Excel Workbook connector.
2. **Measure Table Creation** – Create a dedicated table named `Measure Table` to organize and manage DAX measures.
3. **DAX Measure Development** – Create a `Total Orders` measure using the `COUNT()` function to calculate the total number of orders.
   ```
   Total Orders = COUNT(ListOfOrders[Order ID])
   ```
**3. Create a Clustered Column Chart**
- Select the Clustered Column Chart from the Visualizations pane.
- Assign `Country` from the `ListOfOrders` table to the **X-axis**.
- Assign the `Total Orders` measure to the **Y-axis**.
- Set the chart title to **Total Orders by Country**.

**Result:**

The visualization compares order volumes across different countries and identifies the countries with the highest number of order placements, providing insights into geographical sales distribution.

### 1.1 Use the Customer_Data.xlsx data table to create a line chart that shows the count of orders received per date.

**1. Data Import**
- Load the `Customer_Data.xlsx` file into Power BI using **Home → Get Data → Excel Workbook**.
- Select the `Customer_Data` table and load the dataset.
  
**3. DAX Measure Development**
- Create a new measure named `Total Orders` to calculate the total number of orders received.
- Use the `COUNT()` DAX function to count the Order IDs from the `Customer_Data` table.

**DAX Formula:**
```dax
Total Orders = COUNT(Customer_Data[Order ID])
```

**4. Line Chart Creation**
- Select the **Line Chart** from the Visualizations pane.
- Assign the `Order Date` column from the `Customer_Data` table to the **X-axis**.
- Select the original `Order Date` field instead of `Date Hierarchy` to display complete calendar dates.
- Assign the `Total Orders` measure to the **Y-axis**.
- Set the chart title to **Daily Order Count**.

**5. Analysis and Insights**
- Analyze the line chart to identify daily order trends, peak ordering dates, and fluctuations in order volume over time.
- Use the visualization to understand changes in order placement patterns across different dates.


### 1.2 From the Employee_Layoffs.xlsx dataset create a Pie chart that can best explain the locations with the highest number of layoffs.

**1. Data Import**
- Load the `Employee_Layoffs.xlsx` file into Power BI using **Home → Get Data → Excel Workbook**.
- Select the relevant table and load the dataset.

**2. DAX Measure Development**
- Create a new measure named `Total Layoffs` in the existing `Measure Table` to calculate the total number of employees laid off.
- Use the `SUM()` DAX function to aggregate the layoff counts.

**DAX Formula:**
```dax
Total Layoffs = SUM(Employee_Layoffs[total_laid_off])
```

**3. Pie Chart Creation**
- Select the **Pie Chart** from the Visualizations pane.
- Assign the `Location` column to the **Legend** field.
- Assign the `Total Layoffs` measure to the **Values** field.
- Set the chart title to **Top 5 Locations by Total Layoffs**.

**4. Apply Top N Filter**
- Navigate to the **Filters pane** and locate the `Location` field under **Filters on this visual**.
- Change the filter type to **Top N**.
- Select **Top** and enter `5` in the **Show items** field.
- Drag the `Total Layoffs` measure into the **By value** field.
- Click **Apply filter** to display only the five locations with the highest total layoffs.

**5. Analysis and Insights**
- Analyze the Pie Chart to compare the proportion of employee layoffs across the top five locations.
- Identify the locations contributing the highest number of layoffs based on their share of total layoffs.


### 1.3 Use the Customer Data to create a Calculated Column to the same table. You can create a column that multiples the quantity of the products with its price. There already is a same column “Total Price” that shows the same output. It’s okay just try to create a new column that simply replicates the “Total Price”. 

**1. Create a Calculated Column**

- Open the **Customer Data** table in Power BI Desktop.
- Navigate to the **Table Tools** tab and select **New Column**.
- Enter the following DAX formula in the formula bar to calculate the total price by multiplying the product quantity by its unit price.

**DAX Formula:**

```
Calculated Total Price = 
'Customer Data'[Quantity] * 'Customer Data'[Price Per Unit]
```

**2. Verify the Calculated Column**

- Press **Enter** to create the calculated column.
- Check the newly created `Calculated Total Price` column in the Customer Data table.
- Compare its values with the existing `Total Price` column to verify that both columns return the same results.

**Note:** The existing `Total Price` column already contains the calculated values. This exercise creates a new calculated column to practise using DAX multiplication.

1.4 Create new Measures to find the sum of any numerical column from the Datasets shared. Also write DAX queries to create Measures for finding the total number of Rows in a table, counting the number of valid records, counting the total missing values and to find the smallest and largest number from any column of your choice.

### 1. Existing Measure Table
A table named **Measure Table** was created to organize and store all DAX measures in one place.
The following three measures were already created:
```
Total LaidOff =
SUM(Employee_Layoffs[Total_Laid_Off])
```

```
Total Orders =
COUNT(ListOfOrders[Order ID])
```

```
Total Orders from customer =
COUNT('Customer Data'[Order ID])
```
The following measures were created in the existing **Measure Table** to perform different calculations using the available datasets.

**a. Sum of a Numerical Column**

Calculate the total quantity from the Customer Data table using the `SUM()` function.

Total Quantity =
SUM('Customer Data'[Quantity])

**b. Total Number of Rows**

Use the `COUNTROWS()` function to find the total number of rows in the Customer Data table.

```
Total Rows =
COUNTROWS('Customer Data')
```
**c. Count the Number of Valid Records**
Count records where both Quantity and Price Per Unit contain valid, non-blank values.
```
Valid Records =
COUNTROWS(
    FILTER(
        'Customer Data',
        NOT(ISBLANK('Customer Data'[Quantity])) &&
        NOT(ISBLANK('Customer Data'[Price Per Unit]))
    )
)
```
**d. Count the Total Missing Values**
Use the `COUNTBLANK()` function to calculate the total missing values in the selected numerical columns.
```
Missing Values =
COUNTBLANK('Customer Data'[Quantity]) +
COUNTBLANK('Customer Data'[Price Per Unit])
```

**e. Find the Smallest Number**
Use the `MIN()` function to find the smallest quantity.
```
Minimum Quantity =
MIN('Customer Data'[Quantity])
```

**f. Find the Largest Number**
Use the `MAX()` function to find the largest quantity.

```
Maximum Quantity =
MAX('Customer Data'[Quantity])
```

### 3. Steps to Create Measures

1. Select the existing **Measure Table** from the Fields pane.
2. Go to **Table Tools → New Measure**.
3. Enter the required DAX formula in the formula bar.
4. Press **Enter** to create the measure.
5. Repeat the steps for each additional measure.

### 4. Verification

- Verify that all measures appear under the existing Measure Table.
- Check the calculated results to ensure the DAX expressions work correctly.
- Use Card visuals to display the calculated values, if required.
