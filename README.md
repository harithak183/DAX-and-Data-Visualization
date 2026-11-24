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
