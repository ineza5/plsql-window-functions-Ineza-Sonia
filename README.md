# plsql-window-functions-Ineza-Sonia
# PL/SQL Window Functions – Ineza Sonia

## Problem Definition
A retail supermarket chain in Rwanda wants to analyze its sales performance across different regions.  
The company struggles to identify top products per region/quarter, monitor monthly sales growth, and classify customers by spending levels.  

**Expected Outcome:**  
Using PL/SQL window functions, generate insights on top products, running sales totals, growth rates, customer segmentation, and moving averages to guide marketing and inventory decisions.

---

## Database Schema


### Tables
- **Customers:** stores customer details (customer_id, name, region)  
- **Products:** stores product details (product_id, name, category)  
- **Transactions:** sales records (transaction_id, customer_id, product_id, sale_date, amount)  

### Example ER Diagram

## Inserted Sample Data

```sql
-- Customers
INSERT INTO customers VALUES (1001, 'Alice M.', 'Kigali');
INSERT INTO customers VALUES (1002, 'Jean P.', 'Huye');
INSERT INTO customers VALUES (1003, 'Grace K.', 'Musanze');

-- Products
INSERT INTO products VALUES (2001, 'Coffee Beans', 'Beverages');
INSERT INTO products VALUES (2002, 'Cooking Oil', 'Food');
INSERT INTO products VALUES (2003, 'Soap', 'Household');

-- Transactions
INSERT INTO transactions VALUES (3001, 1001, 2001, DATE '2025-01-15', 25000);
INSERT INTO transactions VALUES (3002, 1001, 2002, DATE '2025-01-20', 15000);
INSERT INTO transactions VALUES (3003, 1002, 2003, DATE '2025-02-05', 5000);
INSERT INTO transactions VALUES (3004, 1003, 2001, DATE '2025-03-10', 30000);
INSERT INTO transactions VALUES (3005, 1002, 2002, DATE '2025-03-15', 20000);
