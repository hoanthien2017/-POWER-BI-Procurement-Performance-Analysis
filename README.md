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
### 1. Overview
![image](https://user-images.githubusercontent.com/101726623/235497110-a732bd29-f481-457b-9021-e968080ab67e.png)

### 2. Customers
![image](https://user-images.githubusercontent.com/101726623/235497166-ca401479-7edb-4cf0-9b7a-d40099037922.png)

### 3. Products
![image](https://user-images.githubusercontent.com/101726623/235497264-43237888-b261-4531-9d93-0922cd2261ad.png)

### 4. Profit
![image](https://user-images.githubusercontent.com/101726623/235497321-196e669a-c4c0-4317-810c-bd368e432e52.png)
