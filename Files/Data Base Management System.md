# Database
***
## 1- Important Definitions
- **Database:** A collection of related data.
- **Database Management System (DBMS):** A software package/ system to facilitate the creation and maintenance of a computerized database.
- **Database System:** The DBMS software together with the data itself. 
&nbsp;
***
## 2- Database Life Cycle
1. Analysis
2. Database Design → Entity Relation Diagram (ERD)
3. Database Mapping → Actual Schema
4. Database Implementation
5. Application (GUI Interface)
6. Client → End User
&nbsp;
***
## 3- Entity-Relation Diagram (ERD)
- **What is an ERD?**
	- An **ERD** is a visual representation of the database structure. It shows:
		- **Entities**: Objects or concepts (`e.g`, Customer, Product).
		- **Attributes**: Properties of entities (`e.g`, Customer Name, Product Price).
		- **Relationships**: How entities are connected (`e.g`, a Customer places an Order).
- **ERD Notations:**
	- **Rectangles**: Represent entities (`e.g`, Customer, Order).
	- **Diamonds**: Represent relationships (`e.g`, "*places*" between Customer and Order).
	- **Ellipses**: Represent attributes (`e.g`, Customer Name, Order Date).
- **Types of Entities**:
	- **Strong Entity**: Has a primary key (`e.g`, Customer ID).
	- **Weak Entity**: Depends on another entity for its identity (`e.g`, an Order Line depends on an Order).
- **Types of Attributes**:
	- **Simple Attribute**: A single value (`e.g`, Age).
	- **Composite Attribute**: Made up of multiple parts (`e.g`,*Address = Street + City + Zip*).
	- **Multi-valued Attribute**: Can have multiple values (`e.g`, Phone Numbers).
	- **Derived Attribute**: Calculated from other attributes (`e.g`, Age derived from Date of Birth).
&nbsp;
***
## 4- Relationships
- **What is a Relationship?**
	- A Relationship is an association among several entities.
- **Degree of Relationships**:
	- **Unary**: A *relationship* within the *same entity* (`e.g`, an Employee manages another Employee).
	- **Binary**: A *relationship* between *two entities* (`e.g`, Customer places Order).
	- **Ternary**: A `relationship` among `three entities` (`e.g`, Student, Course, and Instructor).
- **Cardinality**:
	- **One-to-One**: *One entity* is *related* to *one other entity* (`e.g`, one Employee has one Office).
	- **One-to-Many**: *One entity* is *related* to *many others* (`e.g`, one Customer places many Orders).
	- **Many-to-Many**: *Many entities* are *related* to *many others* (`e.g`, many Students take many Courses).
- **Participation Constraint**:
	- **Total Participation**: *Every entity must participate* in the *relationship* (`e.g`, every Order must have a Customer).
	- **Partial Participation**: *Some entities may not participate* (`e.g`, not every Employee manages a Department)
&nbsp;
***
## 5- Keys
- **What is a Key?**
	- A **key** is an attribute (or set of attributes) that uniquely identifies an entity.
	- **Types of Keys**:
		- **Candidate Key**: is a set of one or more attributes whose value can uniquely identify an entity in the entity set
		- **Primary Key**: is the candidate key that is chosen by the database designer as the unique identifier of an entity. [Unique & Not Null]
		- **Foreign Key**: Links two tables (`e.g`, Order table has a Customer ID to link to the Customer table).
		- **Composite Key**: A key made up of multiple attributes (`e.g`, First Name + Last Name).
&nbsp;
***
## 6- Mapping

#### Steps to Convert ERD to Mapping:
### **1. Convert Entities to Tables**
- Each **Strong Entity** becomes a table.
- Its **Attributes** become columns.
- The **Primary Key** of the entity becomes the primary key of the table.
### **2. Handle Weak Entities**
- A **Weak Entity** depends on a strong entity.
- The table includes:
  - The **Partial Key** of the weak entity.
  - The **Primary Key** of the related strong entity as a foreign key.
  - Together, they form the **composite primary key**.
### **3. Convert Relationships**
#### One-to-Many (1:N)
- Add the **Primary Key** from the "1" side as a **Foreign Key** in the "N" side's table.
#### Many-to-Many (M:N)
- Create a **new table** for the relationship.
- Include:
  - The **primary keys** from both entities as **foreign keys**.
  - These two foreign keys usually form a **composite primary key**.
#### One-to-One (1:1)
- You can add the **primary key** of one entity as a **foreign key** in the other table.
- Depends on **business rules**.
### **4. Multivalued Attributes**
- Create a **new table**:
  - Include the **primary key** of the original entity.
  - And the **multivalued attribute**.
  - Combined, they form the **primary key** of the new table.
### **5. Composite Attributes**
- Break them down into **simple attributes** and add them to the table.
&nbsp;
***
## 7- Normalization
- **What is Normalization?**
	- *Normalization* is the process of *organizing data* to *reduce redundancy* and *improve efficiency*.
	- **Normal  Forms:**
		- **1NF**: Eliminate duplicate columns and ensure atomic values.
		- **2NF**: Remove partial dependencies (`e.g`, ensure all non-key attributes depend on the entire primary key).
		- **3NF**: Remove transitive dependencies (`e.g`, ensure non-key attributes depend only on the primary key).

   - **Dependencies:**
		- It’s a relationship between columns in a database table. It occurs when the value of one column (or a set of columns) uniquely determines the value of another column within the same table.
		- **Types:**
			- **Fully Dependent:**
				- Occurs when a non-key attribute is fully dependent on the entire primary key, rather than just a part of it.
			- **Partially Dependent:**
				- Occurs when a non-key attribute is dependent on only a part of the composite primary key, rather than on the entire composite key.
			- **Transitive Dependent:**
				- Occurs when a non-key attribute depends on another non-key attribute, rather than directly on the primary key.
&nbsp;
***
