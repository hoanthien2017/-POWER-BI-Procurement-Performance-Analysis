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
![image](https://github.com/user-attachments/assets/0ddf6534-3e0a-4129-afff-43a8f4206684)


### Step 3 - Ideate
![image](https://github.com/user-attachments/assets/29d02d59-4c91-4598-b523-3ab1c0ee7f11)
![image](https://github.com/user-attachments/assets/a3f0ab3d-8370-4f1e-98e8-ae662b2448a7)


### Step 4 - Prototype
![image](https://github.com/user-attachments/assets/04236226-ebcc-42a2-9323-85e1c3f298a7)

### Step 5 - Review
![image](https://github.com/user-attachments/assets/98330772-b751-4cd4-9d00-0a0e52692b7e)


## III. Visualization
### 1. Dashboard Dictionary
<details>
<summary><b>Total Procurement Cost</b></summary>
- <b>Definition</b>: The total amount of money spent on purchasing products or services over a specific period.<br>
- <b>Example</b>: If you spend $1 million each month on procurement, your total procurement cost for the year would be $12 million.
</details>

<details>
<summary><b>Number of Purchase Orders</b></summary>
- <b>Definition</b>:  The total number of individual orders placed to purchase products.<br>
- <b>Example</b>: If you place 100 orders in a year, this number would reflect that total.
</details>

<details>
<summary><b>Number of Vendors</b></summary>
- <b>Definition</b>: The number of different suppliers or companies from which products or services are purchased.<br>
- <b>Example</b>: If you buy from 5 different suppliers, you have 5 vendors.
</details>

<details>
<summary><b>Monthly Procurement Cost</b></summary>
- <b>Definition</b>: The amount of money spent on procurement each month.<br>
- <b>Example</b>: If you spend $500,000 in January and $600,000 in February, these would be your monthly procurement costs.
</details>

<details>
<summary><b>Yearly Procurement Cost</b></summary>
- <b>Definition</b>: The total procurement cost for an entire year.<br>
- <b>Example</b>: The total amount spent on procurement in the year 2023.
</details>

<details>
<summary><b>Avg Unit Price</b></summary>
- <b>Definition</b>: The average cost per unit of product purchased from vendors.<br>
- <b>Example</b>: If you buy 10 items at $50 each, the average unit price is $50.
</details>

<details>
<summary><b>Credit Rating</b></summary>
- <b>Definition</b>: A score that indicates how reliable a vendor is, often based on their financial stability and past performance.<br>
- <b>Example</b>: A higher credit rating means the vendor is more trustworthy.
</details>

<details>
<summary><b>Avg Order-to-Delivery Days</b></summary>
- <b>Definition</b>: The average number of days it takes from when an order is placed until it is delivered.<br>
- <b>Example</b>: If you order something on January 1st and receive it on January 22nd, the order-to-delivery time is 22 days.
</details>

<details>
<summary><b>Avg Order-to-Ship Days</b></summary>
- <b>Definition</b>: The average time it takes for an order to be processed and shipped.<br>
- <b>Example</b>: If orders take 5 days on average to be shipped after being placed, this is your avg order-to-ship time.
</details>

<details>
<summary><b>Order Fulfillment Rate</b></summary>
- <b>Definition</b>: The percentage of orders that are completed exactly as requested.<br>
- <b>Example</b>: If you place 100 orders and 96 are delivered as requested, the fulfillment rate is 96%.
</details>

<details>
<summary><b>Order Fulfillment Rate - Full Order</b></summary>
- <b>Definition</b>: The percentage of orders that are delivered completely and on time by vendors. This rate only considers orders that are fulfilled 100%; anything below 100% is not counted.<br>
- <b>Example</b>: If all 100 orders are delivered on time and complete, the fulfillment rate is 100%. If any order is less than 100%, it does not contribute to the fulfillment rate.
</details>

<details>
<summary><b>Vendor Reliability Score</b></summary>
- <b>Definition</b>: A score or measure of how consistently a vendor meets Three expectations including low average unit price, low average order-to-delivery days, high average fulfillment rate - full order (from 1-6).<br>
- <b>Example</b>: A reliability score of 1 might indicate Highest reliability.
</details>

<details>
<summary><b>Product Reliability Score</b></summary>
- <b>Definition</b>: A score or measure of how consistently a vendor meets Three expectations including low average unit price, low average Order-to-Ship Time, high average fulfillment rate (from 1-6).<br>
- <b>Example</b>: A reliability score of 1 might indicate Highest reliability.
</details>

<details>
<summary><b>Vendor Ranking</b></summary>
- <b>Definition</b>: A rank given to products, vendors, or categories based on performance metrics like reliability of products or vendors.<br>
- <b>Example</b>: A Vendor with the highest vendor reliability might be ranked 1st.
</details>

<details>
<summary><b>Product Ranking</b></summary>
- <b>Definition</b>: A rank given to products, vendors, or categories based on performance metrics like reliability of products or vendors.<br>
- <b>Example</b>: A product with the highest product reliability might be ranked 1st.
</details>

<details>
<summary><b>Vendor Breakdown</b></summary>
- <b>Definition</b>: A categorization of vendors based on their Vendor Reliability, such as "Best Vendors" or "Worst Vendors."<br>
- <b>Example</b>: Vendors with the highest fulfillment rates and lowest prices might be classified as "Best Vendors."
</details>

<details>
<summary><b>Avg Quantity Ordered</b></summary>
- <b>Definition</b>: The average number of units ordered per purchase.<br>
- <b>Example</b>: If you order 200 units one time and 300 units another time, the average is 250 units.
</details>

<details>
<summary><b>Status Rate</b></summary>
- <b>Definition</b>: A visual representation of the status of orders, often shown as a pie chart indicating approved, pending, or rejected orders.<br>
- <b>Example</b>: A pie chart showing 92% of orders are approved and 8% are pending.
</details>

<details>
<summary><b>Order Requirement</b></summary>
- <b>Definition</b>: Summary data showing the minimum, maximum, and average quantities ordered, as well as the average days to ship and fulfillment percentage.<br>
- <b>Example</b>: It might show that the smallest order was 10 units, the largest was 1,000 units, and the average order was 500 units.
</details>

<details>
<summary><b>Cost Distribution Overview</b></summary>
- <b>Definition</b>: A breakdown of the different costs involved in procurement, such as purchase subtotal, shipping cost, and tax cost.<br>
- <b>Example</b>: A pie chart showing that 90% of costs are for the product itself, 7% for shipping, and 3% for taxes.
</details>

<details>
<summary><b>Subtotal</b></summary>
- <b>Definition</b>: The total amount of all items in a purchase order before adding taxes and shipping costs. It is calculated by summing up all individual line item totals for a specific purchase order.<br>
- <b>Example</b>: If a vendor's Active Flag is set to 1, the vendor is currently supplying products.
</details>


### 2. Overall procurement performance
![image](https://github.com/user-attachments/assets/ab13d4a3-bfb7-433c-8614-da429b9741ca)

### 3. Vendors Analysis
![image](https://github.com/user-attachments/assets/77e308c2-fce1-4107-b7fa-d5cd09464d47)

### 4. Product Analysis
![image](https://github.com/user-attachments/assets/76edfe57-4397-490f-98e5-3172ca1777ca)
