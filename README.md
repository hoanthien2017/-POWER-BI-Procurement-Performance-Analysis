# POWER BI-Procurement Performance Analysis
## I. Introduction
### 1. Introduction to Dataset
* Dataset: **AdventureWorks database**
- The Dataset supports standard online transaction processing scenarios for a fictitious bicycle manufacturer.

- Data tables:
    | Table number: 7             | Fact table: 3                                      | Dim table: 4                                      |
    |-----------------------------|---------------------------------------------------|-------------------------------------------------|
    | Purchasing.PurchaseOrderHeader,  | Purchasing.PurchaseOrderHeader,                  | Purchasing.ShipMethod,                           |
    | Purchasing.PurchaseOrderDetail, | Purchasing.PurchaseOrderDetail,                   |Purchasing.PurchaseOrderDetail,                   |
    | Purchasing.ProductVendor       | Purchasing.ProductVendor                          | Purchasing.ProductVendor,                        |
    | Purchasing.ShipMethod,  |                                                   | Purchasing.Vendor,                               |
    |Purchasing.PurchaseOrderDetail, |                                                   | Production.Product,                              |
    | Purchasing.ProductVendor,   |                                                   | Production.ProductSubcategory                    |
    |Purchasing.Vendor,       |                                                         |                                                |
     |Production.Product,       |                                                         |                                                |
    |Production.ProductSubcategory       |                                                |                                                |
  
### 2. Data Detail
- Contents of tables:
    - Purchasing.PurchaseOrderDetail: Individual products associated with a specific purchase order.
    - Purchasing.ProductVendor: Cross-reference table mapping vendors with the products they supply.
    - Purchasing.OrderHeader: General purchase order information.
    - Purchasing.Vendor: Companies from whom Adventure Works Cycles purchases parts or other goods.
    - Purchasing.ShipMethod : Shipping company lookup table.
    - Production.Product: Products sold or used in the manufacturing of sold products.
    - Production.ProductSubcategory: Stores information about product subcategories.
    - Production.Productsubcategories: High-level product categorization.
- Description How to record data in each table:
    - All tables follow the Snapshot data capture type. Each row records a product type in the order. For orders with n products, n rows will be recorded. Each area is considered a unique record for other attributes.
- Preliminary assessment of data quality:
    - null, distinct, quality rule, min/max
### 3. Business Questions
- How can we ensure that purchases are made in the right quantity, on time, and at the best price?
- What insights can optimize the procurement process and improve operational efficiency?
  
## II. Design Thinking Method
**Here are the five steps of design thinking:**
### Stage 1: Empathize 
![image](https://github.com/user-attachments/assets/71af896a-ce87-4906-9b36-fd93692bf99a)
![image](https://github.com/user-attachments/assets/010e1e29-825d-4f6c-b7f3-b8d8a11c4281)


### Stage 2: Define POV 
![image](https://github.com/user-attachments/assets/108d1624-9a64-440e-9e94-48dfa575924a)
![image](https://github.com/user-attachments/assets/bce4d87c-6654-4e87-9f0e-858aa815a7e6)

### Step 3 - Ideate
![image](https://github.com/user-attachments/assets/29d02d59-4c91-4598-b523-3ab1c0ee7f11)
![image](https://github.com/user-attachments/assets/9f0b84f9-a7d4-4219-8573-8f93a99425d5)


### Step 4 - Prototype
![image](https://github.com/user-attachments/assets/04236226-ebcc-42a2-9323-85e1c3f298a7)

### Step 5 - Review
![image](https://github.com/user-attachments/assets/98330772-b751-4cd4-9d00-0a0e52692b7e)


## III. Visualization
### 1. Dashboard Dictionary
| **Metric**                          | **Definition**                                                                                                                                                     |
|-------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Total Procurement Cost**          | The total amount of money spent on purchasing products or services over a specific period.                                                                         |
| **Number of Purchase Orders**      | The total number of individual orders placed to purchase products.                                                                                                |
| **Number of Vendors**              | The number of different suppliers or companies from which products or services are purchased.                                                                     |
| **Monthly Procurement Cost**       | The amount of money spent on procurement each month.                                                                                                              |
| **Yearly Procurement Cost**        | The total procurement cost for an entire year.                                                                                                                     |
| **Avg Unit Price**                 | The average cost per unit of product purchased from vendors.                                                                                                      |
| **Credit Rating**                  | A score that indicates how reliable a vendor is, often based on their financial stability and past performance.                                                    |
| **Avg Order-to-Delivery Days**     | The average number of days it takes from when an order is placed until it is delivered.                                                                           |
| **Avg Order-to-Ship Days**         | The average time it takes for an order to be processed and shipped.                                                                                                |
| **Order Fulfillment Rate**         | The percentage of orders that are completed exactly as requested.                                                                                                 |
| **Order Fulfillment Rate - Full Order** | The percentage of orders that are delivered completely and on time by vendors. This rate only considers orders that are fulfilled 100%; anything below 100% is not counted. |
| **Vendor Reliability Score**       | A score or measure of how consistently a vendor meets three expectations including low average unit price, low average order-to-delivery days, and high fulfillment rate (from 1-6). |
| **Product Reliability Score**      | A score or measure of how consistently a vendor meets three expectations including low average unit price, low average order-to-ship time, and high fulfillment rate (from 1-6). |
| **Vendor Ranking**                 | A ranking system for vendors based on performance metrics such as product quality, delivery times, and customer service reliability.                             |
| **Product Ranking**                | A ranking system for products based on factors such as quality, customer satisfaction, and durability.                                                            |
| **Vendor Breakdown**               | A categorization of vendors based on their Vendor Reliability, such as "Best Vendors" or "Worst Vendors."                                                          |
| **Avg Quantity Ordered**           | The average number of units ordered per purchase.                                                                                                                 |
| **Status Rate**                    | A visual representation of the status of orders, often shown as a pie chart indicating approved, pending, or rejected orders.                                      |
| **Order Requirement**              | Summary data showing the minimum, maximum, and average quantities ordered, as well as the average days to ship and fulfillment percentage.                         |
| **Cost Distribution Overview**     | A breakdown of the different costs involved in procurement, such as purchase subtotal, shipping cost, and tax cost.                                                 |
| **Subtotal**                       | The total amount of all items in a purchase order before adding taxes and shipping costs. It is calculated by summing up all individual line item totals for a specific purchase order. |

### 2. Overall procurement performance
![image](https://github.com/user-attachments/assets/ab13d4a3-bfb7-433c-8614-da429b9741ca)

### 3. Vendors Analysis
![image](https://github.com/user-attachments/assets/77e308c2-fce1-4107-b7fa-d5cd09464d47)

### 4. Product Analysis
![image](https://github.com/user-attachments/assets/76edfe57-4397-490f-98e5-3172ca1777ca)

## IV. Insights and recommendations 
1. **Reduce Lead Time**  
- Lead time increased from 17 to 41 days between 2011 and 2013, now at 38 days in 2014. Focus on optimizing this to ensure timely deliveries.

2. **Maintain High Fulfillment Rate**  
- Fulfillment rate improved from 85% in 2011 to 97% in 2014. Keep this momentum by closely monitoring supplier performance.

3. **Summary Vendor Insight**  
- Vendor performance is strong, with a high fulfillment rate 98% and $35.30 in average unit price, indicating better cost management. However, reducing the average delivery time of 22 days could further optimize operations.

4. **Key Vendor Insight**  
- Comfort Road Bicycles excels with a 100% fulfillment rate, a competitive unit price of $22, and a swift delivery time of 15 days, making it a critical and efficient supplier.

5. **Bottom Vendor Insight**  
- American Bicycles and Wheels, despite a 98% fulfillment rate, has a high unit price of $57.00 and a longer delivery time of 17 days. Reevaluation of this vendor could improve both cost and delivery efficiency.

6. **Summary Product Insight**  
- High fulfillment rates (97-99%) and stable 9-day delivery times indicate reliable procurement. A slight drop in average unit prices, especially in 2014, reflects effective cost management.

7. **Key Product Insight**  
- Clothing is a top performer with 100% fulfillment, competitive unit prices, and consistent 9-day delivery, ensuring timely availability for sales and production.

8. **Bottom Product Insight**  
- Pedals show lower fulfillment rates (95-98.5%) and higher costs ($51.44 in 2011). Despite consistent 9-day delivery, there's a need to improve supplier efficiency and cost management.
