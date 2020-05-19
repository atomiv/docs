# Processes

## Business Overview

We are making a software application "Erimont" which is an online shop builder. Erimont enables businesses to create business accounts, and then they can add products which they sell. When customers go the to the webshop for that business, they can sign up as customers, add products to the card, and make an order as well as payments for the order.

## Actors

* Businesses
* Customers
* Suppliers

## Catalog Process

Acme Corporation Employees need to be able to manage products:

1. Employee browses the Product Catalog
2. Employee adds additional products to the Product Catalog
3. Employee unlists products in the Product Catalog
4. Employee relists products in the Product Catalog
5. Employee selects the Supplier for each product
6. Employee sets the retail price for each product
7. Employee sets product price discounts

## Sales Process

The primary sales process is triggered by the Customer:

1. Customer browses the Product Catalog
2. Customer adds products to the Shopping Cart
3. Customer submits order
4. Customer makes a payment
5. Business receives the payment
6. Order is shipped to the customer
7. Inventory is updated based on the shipped products

## Purchasing Process

The primary purchasing process is triggered either automatically \(when stock for a product goes below a minimum\) or when the procurement department specifically makes a purchase order:

1. System creates a purchase order
2. System sends purchase order
3. Supplier fulfills the order and ships the products to Acme
4. Acme ERP records the received products within inventory
5. Supplier sends an invoice to the Acme
6. Acme makes payment for the invoice

