# WitleShop Online Retail System — ERD Assignment

**Student:** Shudufhadzo Mashamba  
**Date:** 05 October 2026

---

## 1. Entities Identified

| Entity | Description |
|--------|-------------|
| Customer | People who register and place orders |
| Address | Delivery addresses (customers can have many) |
| Category | Product categories |
| Supplier | Companies that supply products |
| Product | Items being sold |
| Order | Orders placed by customers |
| OrderItem | Links orders to products (resolves the M:N relationship) |
| Payment | One payment per order |
| Delivery | One delivery per order |

---

## 2. Primary Keys

| Entity | Primary Key |
|--------|-------------|
| Customer | CustomerID |
| Address | AddressID |
| Category | CategoryID |
| Supplier | SupplierID |
| Product | ProductID |
| Order | OrderID |
| OrderItem | OrderItemID |
| Payment | PaymentID |
| Delivery | DeliveryID |

---

## 3. Foreign Keys

| Entity | Foreign Key | References |
|--------|-------------|------------|
| Address | CustomerID | Customer |
| Product | CategoryID | Category |
| Product | SupplierID | Supplier |
| Order | CustomerID | Customer |
| OrderItem | OrderID | Order |
| OrderItem | ProductID | Product |
| Payment | OrderID | Order |
| Delivery | OrderID | Order |
| Delivery | AddressID | Address |

---

## 4. Relationships and Cardinality

| Relationship | Cardinality |
|--------------|-------------|
| Customer → Address | 1:M |
| Customer → Order | 1:M |
| Category → Product | 1:M |
| Supplier → Product | 1:M |
| Order → OrderItem | 1:M |
| Product → OrderItem | 1:M |
| Order → Payment | 1:1 |
| Order → Delivery | 1:1 |
| Address → Delivery | 1:M |
| Order ↔ Product (via OrderItem) | M:N |

---

## 5. Design Decisions

- **OrderItem** is a junction table that resolves the Many-to-Many relationship between Order and Product.
- **Payment** and **Delivery** each have a 1:1 relationship with Order.
- **Delivery** links to **Address** (not Customer) so that deliveries only go to a customer's registered address.

---

## 6. Files in this Repository

- `Witleshop-ERD.drawio` — editable source file
- `Witleshop-ERD.drawio.png` — exported image

---

## 7. How to View the ERD

- View the PNG image directly in this repository
- Or download the `.drawio` file and open it at https://app.diagrams.net
