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

**2. Measure Table Creation**
- Create a separate table named `Measure Table` to organize and manage DAX measures efficiently.

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
- Set the X-axis type to **Continuous**.
- Assign the `Total Orders` measure to the **Y-axis**.
- Set the chart title to **Daily Order Count**.

**5. Analysis and Insights**
- Analyze the line chart to identify daily order trends, peak ordering dates, and fluctuations in order volume over time.
- Use the visualization to understand changes in order placement patterns across different dates.
