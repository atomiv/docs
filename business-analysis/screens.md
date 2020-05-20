# Web Applications

## ACME Identity

ACME Identity is an Identity Server, a microservice which handles the identities for all ACME employees and ACME subsidaries. A general requirement is that all ACME applications are multi-tenant applications.

ACME Identity URL: https://identity.acme-estore.com

ACME has multiple subsidiaries including:

* ACME USA Inc.
* ACME Deutschland GmbH
* ACME Serbia d.o.o.

ACME Identity contains screens for:

* Registering employees
* Authenticating employees
* Handling forgotten passwords and password resets

ACME Identity uses the OpenID Connect mechanism, so that when other ACME applications connect to it they can use token-based authentication, so that security is centralized.

The data which is managed by ACME Identity is:

* Subsidaries: Name, Country
* Employees: First Name, Last Name, Phone, Email, Photo, Subsidiary, Roles

## ACME Backoffice

ACME Backoffice is an application used by backoffice employees within ACME globally. 

ACME Backoffice URL: https://backoffice.acme-estore.com

When a user logs in, ACME Backoffice enables them to do the following:

* Employees can login and can manage orders, customers and products. 
* Managers can view analytics regarding order sales.
* Administrators can configure subsidiaries.

ACME Backoffice is integrated with the following:

* ACME IdentityServer \(to authenticate employees\)
* ACME ERP which contains products, product inventory, warehouses, suppliers, etc.

### Login

ACME Backoffice checks whether the employee is already logged into ACME Identity. 

* If they are already logged in, then they can proceed.
* If they are not already logged in, then it redirects the employee to ACME Identity, and when authenticated, returns back to ACME Backoffice.

### Navigation Bar

The navigation bar is displayed on all screens for authenticated users.

On the left hand side we have the subsidary where the logged in employee is employed:

* Subsidiary logo
* Subsidiary name

On the right hand side, the employee sees the following:

* Orders
* Customers
* Products
* Analytics \(this is only available for employees who have the manager role\)
* Admin \(this is only available for employees who have the administrator role\)

### Orders Screen

Employees can see an orders data table, with the following details:

* Order Number \(unique number identifying the order\)
* Order Date \(when the order was made\)
* Customer Name \(name of the customer who placed the order\)
* Customer Surname \(surname of the customer who placed the order\)
* Total Price \(total price for the order\)
* Order Status \(Placed, Packed, Shipped, Delivered, Cancelled, Delivery Failed\)
* Delivery Date \(the forecast delivery date if the order was not yet delivered\)

Additionally, there is a "New Order" button which is used when some customers don't create an order online but instead call ACME via the phone, so then orders are able to be placed on behalf of customers by ACME employees \(in this case the system marks the order as manually created by the specific employee\).

When the employee selects an order they can click on "View" to open the order. It is possible for employees to manually edit the order on behalf of the customer \(in this case the system marks the order as manually edited by the specific employee\). Orders can be manually edited only before they are "Shipped".

Initially, when an order was confirmed by the customer on the ACME Online Store, its status is is "Placed". The employee can then click buttons "Packed" \(if the order was successfully packed\) or "Cancelled" \(if the customer called to cancel the order or if the order was not able to be fulfilled or any other reason\). Once then employee clicks on "Packed", then the next buttons that appear is "Shipped" \(when the order is loaded to the shipping company truck\) or "Cancelled". After the order is "Shipped", then the employee is not able to set status any further.

From that point onwards, since ACME Backoffice is connected to ACME ERP, which is connected to shippers, ACME Backoffice synchronizes order statuses as follows: the ACME ERP gets statuses from the shipping company "Delivered" \(the order was delivered to the customer\) or "Delivery Failed" \(the order could not be delivered to the customer for some reason\).

## Customers





## ACME Online Store

