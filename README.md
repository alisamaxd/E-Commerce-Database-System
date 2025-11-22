# E-Commerce Database Management System 

## Project Overview
This project demonstrates a comprehensive relational database design for a fictional B2C E-Commerce platform. It covers the entire data lifecycle from customer registration to order processing and sales reporting. The system is designed to simulate real-world scenarios with fully normalized tables and strict data integrity constraints.

## Technologies Used
* **Database Engine:** Microsoft SQL Server 2022
* **Language:** T-SQL (Transact-SQL)
* **Tools:** SQL Server Management Studio (SSMS)

## Key Features & Architecture
The project includes a robust schema design with the following key features:

* **Hierarchical Category Structure:** Implemented a self-referencing table (`ParentID`) logic to support infinite sub-categories (e.g., Electronics > Computer > Laptop).
* **Scalable Order Management:** Separated logic for `Orders` (Header) and `OrderDetails` (Line Items) to ensure database normalization and scalability.
* **Reporting & Analysis:** Created Views (e.g., `vw_SalesReports`) to analyze total revenue, customer spending, and product performance instantly.
* **Data Integrity:** Enforced Primary Keys, Foreign Keys, and Default Constraints to prevent data anomalies.

## How to Run the Project
1.  Download the `ECommerceDB_Full_Setup.sql` file from this repository.
2.  Open **SQL Server Management Studio (SSMS)**.
3.  Open the file and execute the script.
4.  The script will automatically:
    * Create the database and tables.
    * Set up relationships (PK/FK).
    * Insert sample mock data (Customers, Products, Orders).

## Sample Query (Sales Analysis)
Here is an example of a T-SQL query used in the project to calculate total revenue per product:

```sql
SELECT 
    p.ProductName, 
    SUM(od.Quantity) AS TotalSold, 
    SUM(od.Quantity * od.UnitPrice) AS TotalRevenue
FROM OrderDetails od
JOIN Products p ON od.ProductID = p.ProductID
GROUP BY p.ProductName
ORDER BY TotalRevenue DESC;

Developed by Ali Şener - Management Information Systems Student Aspiring Data Engineer |
