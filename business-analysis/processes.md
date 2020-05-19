# Processes

## Business Overview

We are making a software application "Erimont" which is an online shop builder. Erimont enables businesses to create business accounts, and then they can add products which they sell. When customers go the to the webshop for that business, they can sign up as customers, add products to the card, and make an order as well as payments for the order.

## Actors

* Businesses
* Customers
* Suppliers

## Business Process

A Business sells products to its customers, and purchases products from suppliers.

Business can set the retail prices for the products and also for each product choose the supplier for that product.

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
3. Supplier fulfills the order and ships the products to the Business
4. Business records the received products within inventory
5. Supplier sends an invoice to the Business
6. Business makes payment for the invoice

