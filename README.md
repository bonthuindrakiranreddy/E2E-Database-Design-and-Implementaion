# E2E-Database-Design-and-Implementaion
# Integrated Supply Chain and Financial Management System

## Project Overview
This project, undertaken as part of the MGS 613 – DBMS (Fall 2023) course during my Master’s, demonstrates the development of an Enterprise Resource Planning (ERP) Database Schema designed to address the operational needs of a manufacturing and supply chain company. It streamlines employee allocation, product lifecycle management, material flow, and vendor invoice processing to enhance overall organizational efficiency.

The objective of this project was to create an ERP database capable of managing:
- Employee performance and payroll tracking.
- Departmental and warehouse operations.
- Vendor and raw material relationships.
- Invoice processing by the accounting department.
- The schema ensures data consistency, operational efficiency, and seamless information flow across the organization.

## Key Features
- **Comprehensive Database Schema:** Modeled using Enhanced Entity-Relationship (EER) diagrams to visualize entities, relationships, and constraints.
- **Data Normalization:** Achieved up to Third Normal Form (3NF) to eliminate redundancy and ensure integrity.
- **SQL Implementation:** Database implemented and tested using Oracle SQL.
- **Real-World Constraints:** Business rules encoded as referential integrity constraints.
- **Query Optimization:** Key queries written for analytics and operational needs.

## Business Rules
Rule	Description	Related Entities
- **Business Rules1:**	Company has departments, warehouses, and production lines.	Departments, Warehouses, Production lines
- **Business Rules2:**	Company designs and produces products.	Products
- **Business Rules3:**	Each department, warehouse, and production line has multiple employees.	Departments, Warehouses, Production lines, Employees
- **Business Rules4:**	Each employee works in only one department, warehouse, or production line.	Employees, Departments, Warehouses, Production lines
- **Business Rules5:**	Some departments design products (at least one).	Departments, Products
- **Business Rules6:**	Each product must be produced by one specific production line.	Products, Production lines
- **Business Rules8:**	Each production line can produce only one product (or none).	Production lines, Products
- **Business Rules9:**	Raw materials are supplied by any number of warehouses (supplied by vendors).	Raw materials, Warehouses, Vendors
- **Business Rules10:**	Raw materials may also be directly supplied by vendors.	Raw materials, Vendors
- **Business Rules11:**	Vendors can supply any number of materials.	Vendors, Raw materials
- **Business Rules12:**	Vendors submit invoices if they receive orders.	Vendors, Invoices
- **Business Rules13:**	Invoices must be processed by the accounting department.	Invoices, Accounting department

## Project Timeline
Phase	                          Duration	  Milestones
Requirements Analysis & Design	Weeks 1-3	  Identified entities, attributes, relationships, and constraints. Developed metadata repository.
Normalization & Schema Creation	Weeks 4-5	  Normalized database to 3NF and finalized SQL table definitions.
Implementation & Testing	      Weeks 6-9	  Created physical database, performed testing, and documented the entire process.
Presentation	                  Week 10	    Delivered project findings and outcomes to the professor and class audience.

## System Design and Implementation
- **Metadata:** Defined for all key entities, including Employee, Department, Product, Warehouse, and Vendor.
- **EER Diagrams:** Captured relationships and cardinalities (e.g., one-to-many, many-to-many).
- **Database Constraints:** Included primary keys, foreign keys, and referential integrity rules.

## Database Structure

The database consists of the following key tables:

| Table Name            | Description                                                                 |
|-----------------------|-----------------------------------------------------------------------------|
| **Department**        | Contains details about each department in the organization.                 |
| **Employee**          | Stores employee data, linked to the Department and Warehouse tables.        |
| **Vendor**            | Holds information about vendors supplying raw materials and other products. |
| **Product**           | Lists all products, including raw materials and finished goods.             |
| **Supply Schedule**   | Manages the supply schedules for raw materials from various vendors.        |
| **Invoice**           | Tracks invoices related to purchases and payments made to vendors.          |
| **Warehouse**         | Details about warehouses, including their locations and capacity.           |

## Normalization

### 1. **First Normal Form (1NF)**
- All tables contain atomic data, ensuring that each column holds a single value.
- Example: In the `Employee` table, fields such as `FirstName`, `LastName`, and `DepartmentID` are atomic.

### 2. **Second Normal Form (2NF)**
- The database is free of partial dependencies, with every non-key attribute fully dependent on the primary key.
- Example: In the `Product` table, all non-key attributes (e.g., `ProductName`, `CategoryID`) depend solely on the `ProductID`.

### 3. **Third Normal Form (3NF)**
- The database is free of transitive dependencies, ensuring that non-key attributes are only dependent on the primary key.
- Example: In the `Invoice` table, attributes such as `VendorID` and `Amount` are directly dependent on the `InvoiceID`.

## Conclusion
The Integrated Supply Chain and Financial Management System successfully delivers a robust ERP database tailored to streamline supply chain and financial operations. By employing effective database design, normalization, and implementation strategies, the project ensures data integrity, eliminates redundancy, and supports efficient decision-making. Completed within the proposed timeline, this project serves as a scalable foundation for enhancing operational efficiency and addressing real-world business needs.

