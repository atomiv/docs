# Use Cases

## Business Use Cases

### Administrators

Commands:

* Register a Business account
* Edit the list of employees within the company
* Deactivate employees within the company

Queries:

* View all list of all employees within the company
* Deactivate Business account

### Procurement Managers

Commands:

* Add products in the product catalog
* Edit products in the product catalog
* Unlist products in the product catalog \(i.e. products which are no longer sold\)
* Relist products in the product catalog \(i.e. these products become active again\)
* Select list of possible suppliers for products
* Specify default \(preferred\) supplier for each product
* Set the retail price for each product
* Set promotional discounts for all or some products

Queries:

* Browse products in the product catalog 
* View products in the product catalog

### 

### Pricing Managers

Commands:



Queries:





## Sales Use Cases

### Customers

Commands:

* Browse products in the Product Catalog
* Add products to the Shopping Cart
* Remove products from the Shopping Cart
* Submit Order based on products in the Shopping Cart
* Make online payments for Orders
* Create draft orders
* Edit the draft orders they had created
* Submit the draft orders
* Archive shipped orders

Queries:

* Filter and search for their orders - including filtering by order status and dates \(order submission date and order delivery date\)
* View their own orders

### Warehouse Employees

Commands:

* Pack an Order
* Ship an Order

Queries:

* Browse Orders
* View Orders





## Purchasing Process

The primary purchasing process is triggered either automatically \(when stock for a product goes below a minimum\) or when the procurement department specifically makes a purchase order:

1. System creates a purchase order
2. System sends purchase order
3. Supplier fulfills the order and ships the products to the Business
4. Business records the received products within inventory
5. Supplier sends an invoice to the Business
6. Business makes payment for the invoice





## Business Customer Use Cases

### Employees



### Managers

Commands:

* Approve orders
* Reject orders

Queries:

* View statistics at company-level regarding the total purchase value of orders

### Administrators

Commands:

* Edit the list of employees within the company
* Deactivate employees within the company
* Set the roles for employees within the company \(i.e. setting employees, managers, administrators\)

Queries:

* View all list of all employees within the company

## Private Customer Use Cases

### Customers

Commands:

* Create draft orders
* Edit the draft orders they had created
* Submit the draft orders
* Archive the orders they had created

Queries:

* Filter and search for orders their own orders - including filtering by order status and dates \(order submission date and order delivery date\)
* View their own orders

## Supplier Use Cases

### Catalog Managers



## Packers

Commands:

* Fulfill purchase orders - packing and sending to shipper

Queries:

* Browse purchase orders
* View purchase orders

### Administrators



## System Use Cases

Commands:

* Automatically create supplier orders





