# Exercise 1: Employee Directory

A startup is replacing its paper employee records with a small database. Build the first version of the system.

Store the following information for each employee:
- employee identifier
- full name
- department
- monthly salary
- years worked at the company
- phone number
- emergency contact (this information may not always be available)

Populate the database with the employees below.

| Name          | Department | Salary | Years | Phone      | Emergency Contact |
| ------------- | ---------- | -----: | ----: | ---------- | ----------------- |
| Alice Johnson | HR         |    850 |     2 | 0781111111 | Mary Johnson      |
| Brian Smith   | IT         |   1200 |     5 | 0782222222 |                   |
| Charles King  | Finance    |    980 |     3 | 0783333333 | Robert King       |
| Diana Green   | IT         |   1350 |     6 | 0784444444 |                   |
| Emma White    | HR         |    920 |     1 | 0785555555 | Susan White       |

After entering the data, complete the following tasks.

1. Display every employee in the system.
2. Produce a report showing each employee's name, department, and monthly salary.
3. Produce a report showing each employee's monthly salary together with the calculated yearly salary. Do not store the yearly salary in the table.
4. Identify employees earning more than **1000** per month.
5. Find employees who work in the **IT** department and have worked for the company for more than **4** years.
6. Find employees who either work in **HR** or earn more than **1300** per month.
7. Brian Smith has provided his emergency contact. Update the database accordingly.
8. Emma White has resigned. Remove her record from the database.
9. Produce one report showing employees whose emergency contact is unknown and another showing employees whose emergency contact is available.

# Exercise 2: Store Inventory

A neighborhood electronics store wants to replace its handwritten inventory records with a database. Build the first version of the inventory system.

Store the following information for each product:

- product identifier
- product name
- category
- unit price
- quantity in stock
- supplier(The supplier may not always be known.)
- warranty period (in months)



Populate the database with the products below.

| Product             | Category    | Unit Price | Quantity | Supplier   | Warranty |
| ------------------- | ----------- | ---------: | -------: | ---------- | -------: |
| Wireless Mouse      | Accessories |         25 |       40 | TechSource |       12 |
| Mechanical Keyboard | Accessories |         75 |       18 | KeyMasters |       24 |
| 24-inch Monitor     | Displays    |        180 |       12 | VisionTech |       36 |
| USB Flash Drive     | Storage     |         15 |       75 |            |       12 |
| External SSD        | Storage     |        120 |       20 | DataStore  |       24 |
| Laptop Stand        | Accessories |         35 |       30 |            |        0 |

After entering the data, complete the following tasks.

1. Display every product currently in stock.
2. Produce a report showing each product's name, category, unit price, and quantity.
3. Produce a report showing each product together with its total inventory value. Calculate the inventory value by multiplying the unit price by the quantity in stock. Do not store the result in the table.
4. Identify products with a unit price greater than **100**.
5. Find products in the **Accessories** category that have more than **20** units in stock.
6. Find products that either belong to the **Storage** category or cost more than **150**.
7. The price of the **24-inch Monitor** has increased to **195**. Update the database accordingly.
8. The store has sold all **USB Flash Drives** and no longer stocks them. Remove the product from the database.
9. Produce one report showing products whose supplier is unknown and another showing products whose supplier is recorded.

# Exercise 3: School Examination System

A secondary school is moving from spreadsheet-based tracking to a relational database system. Build the first version of the examination database.

Store the following information for each student:

- student identifier
- full name
- class
- subject
- exam score
- coursework score
- attendance percentage
- remarks (may be unknown)

Populate the database with the records below.

|Student|Class|Subject|Exam|Coursework|Attendance|Remarks|
|---|---|---|---|---|---|---|
|Amina Niyonzima|S4A|Mathematics|78|15|92||
|Brian Hakizimana|S4A|Mathematics|62|18|85|Needs improvement|
|Claire Uwase|S4B|Mathematics|88|20|96|Excellent|
|David Manzi|S4B|Mathematics|55|14|70||
|Eliane Mutesi|S4A|English|81|17|90|Strong performance|
|Frank Nsabimana|S4B|English|47|12|65||
|Grace Mukamana|S4A|English|73|16|88||

After entering the data, complete the following tasks.

1. Display every record in the system.
2. Display each student’s full name, class, subject, exam score, and coursework score only.
3. Produce a report that shows each student’s total score, calculated as: exam score + coursework score
4. Produce a report that shows each student’s final score using: exam score + coursework score + (attendance / 10)
5. Identify students whose exam score is greater than 75.
6. Identify students whose exam score is below 50 or attendance is below 70.
7. Find students who are in class **S4A** and scored more than 80 in total score.
8. Find students who are either in **S4B** or have a coursework score greater than 18.
9. Increase the coursework score by 2 for all students in **S4A**.
10. Update remarks for students whose final score is greater than 90 to **"Top performer"**.
11. Remove all students whose exam score is below 50.
12. Identify students who have no remarks recorded.
13. Identify students who have remarks recorded.


# Exercise 4: Hospital Patient Records System

A hospital is replacing its paper-based patient tracking system with a database. Build the first version of the patient management system.

Store the following information for each patient:

- patient identifier
- full name
- gender
- age
- department (ward)
- diagnosis
- blood pressure (systolic value)
- heart rate
- treatment cost
- insurance coverage amount
- discharge status (may be unknown)
    

Populate the database with the records below.

|Patient|Gender|Age|Ward|Diagnosis|BP|Heart Rate|Cost|Insurance|Discharge|
|---|---|---|---|---|---|---|---|---|---|
|Jean Uwimana|F|34|Cardiology|Hypertension|150|88|1200|1000||
|Patrick Ndayisaba|M|58|Cardiology|Stroke|180|95|3500|2000|Discharged|
|Marie Mukarwego|F|41|Neurology|Migraine|130|80|900|900||
|Samuel Bizimana|M|67|Cardiology|Heart Failure|190|102|5000|2500||
|Alice Nyiransabimana|F|29|Pediatrics|Asthma|120|76|700|700|Discharged|
|David Hirwa|M|45|Neurology|Epilepsy|160|90|1800|1200||
|Grace Ishimwe|F|52|Cardiology|Arrhythmia|170|98|2600|1500||

After entering the data, complete the following tasks.

1. Display every patient record in the system.
2. Display each patient’s full name, ward, diagnosis, age, and treatment cost only.
3. Produce a report showing each patient’s net bill calculated as: treatment cost − insurance coverage amount
4. Identify patients whose blood pressure is greater than 160.
5. Identify patients whose heart rate is greater than 90 or blood pressure is greater than 170.
6. Find patients in the **Cardiology** ward whose net bill is greater than 2000.
7. Find patients who are either in **Neurology** or have a heart rate below 85.
8. Increase treatment cost by 10% for all patients in **Cardiology**.
9. Reduce insurance coverage by 5% for all patients above age 50.
10. Update discharge status to **"Discharged"** for patients whose net bill is less than or equal to 0.
11. Remove all patients whose diagnosis is **Migraine**.
12. Identify patients who have not been discharged.
13. Identify patients whose discharge status is recorded.
14. Identify patients whose insurance does not fully cover their treatment cost.

# Exercise 5: Airline Booking and Revenue System

An airline company is replacing its manual booking spreadsheets with a database system. Build the first version of the booking and revenue system.

Store the following information for each booking:

- booking identifier
- passenger full name
- flight code
- departure city
- destination city
- seat class (Economy, Business, First)
- base ticket price
- luggage weight (kg)
- extra luggage fee per kg
- discount percentage
- payment status (may be unknown)

Populate the database with the records below.

|Passenger|Flight|From|To|Class|Price|Luggage|Fee/kg|Discount|Payment|
|---|---|---|---|---|--:|--:|--:|--:|---|
|Jean Uwimana|RW101|Kigali|Nairobi|Economy|320|18|5|0|Paid|
|Patrick Ndayisaba|RW101|Kigali|Nairobi|Business|620|25|8|10|Paid|
|Marie Mukarwego|RW202|Kigali|Dubai|Economy|780|32|6|5||
|Samuel Bizimana|RW202|Kigali|Dubai|First|1500|40|10|15|Pending|
|Alice Nyiransabimana|RW303|Kigali|London|Business|980|22|7|0|Paid|
|David Hirwa|RW303|Kigali|London|Economy|450|20|5|0||
|Grace Ishimwe|RW404|Kigali|Brussels|First|1350|35|9|20|Paid|

After entering the data, complete the following tasks.

1. Display every booking in the system.
2. Display passenger name, flight code, route (departure → destination), class, and base price only.
3. Produce a report showing the final ticket price calculated as: base price + (luggage weight − 20 if positive) × extra luggage fee − discount
4. Identify bookings where luggage weight exceeds 20 kg.
5. Identify bookings where:
    - seat class is Business or First
    - and luggage weight is greater than 30 kg
6. Find all passengers flying from **Kigali to Dubai** or **Kigali to London**.
7. Increase extra luggage fee by 2 for all First class passengers.
8. Apply an additional 5% discount for passengers whose luggage exceeds 30 kg.
9. Update payment status to **Paid** for passengers whose final ticket price is below 500.
10. Remove all bookings where payment status is unknown AND luggage is below 20 kg.
11. Identify passengers who have not paid.
12. Identify passengers who have discounts applied (discount > 0).
13. Identify passengers whose luggage fees significantly increase the final price (fee contribution > 100).
14. Identify routes that generate the highest base revenue (base price only, no calculations needed beyond filtering logic).


# Exercise 6: Multi-System Retail Analytics Platform

A large retail company is migrating from separate spreadsheets into a unified relational database. Build the first version of the retail analytics system.

Store the following information for each transaction:

- transaction identifier
- customer full name
- customer region
- product category
- product name
- unit cost
- quantity purchased
- discount rate (%)
- tax rate (%)
- payment status (may be unknown)
- return status (may be unknown)

Populate the database with the records below.

|Customer|Region|Category|Product|Cost|Qty|Discount|Tax|Payment|Return|
|---|---|---|---|--:|--:|--:|--:|---|---|
|Amina Niyonzima|East|Electronics|Headphones|120|2|5|18|Paid||
|Brian Hakizimana|West|Electronics|Keyboard|80|1|0|18|Paid|Returned|
|Claire Uwase|North|Furniture|Office Chair|220|3|10|18|||
|David Manzi|South|Furniture|Desk|350|1|15|18|Paid||
|Eliane Mutesi|East|Appliances|Microwave|180|2|0|18|Pending||
|Frank Nsabimana|West|Electronics|Monitor|300|1|20|18|Paid||
|Grace Mukamana|North|Appliances|Blender|90|4|5|18||Returned|
|Samuel Bizimana|South|Furniture|Sofa|600|1|25|18|Paid||

After entering the data, complete the following tasks.

1. Display every transaction in the system.
2. Display customer name, region, product, category, quantity, and unit cost only.
3. Produce a report showing the total revenue per transaction calculated as:
    (unit cost × quantity) − discount amount + tax amount
    where:
    - discount amount = (unit cost × quantity) × (discount / 100)
    - tax amount = (unit cost × quantity − discount amount) × (tax / 100)
        
1. Identify transactions where total quantity exceeds 2 OR unit cost exceeds 250.
2. Find transactions where:
    - product category is Electronics AND quantity is at least 2
    - OR product category is Furniture AND discount is greater than 10%
3. Find all transactions from the East or North regions with revenue above 300.
4. Increase discount rate by 5% for all Furniture products purchased in quantity greater than 1.
5. Increase tax rate by 2% for all Electronics products that are not returned.
6. Update payment status to **Paid** for all transactions whose computed revenue exceeds 500.
7. Mark return status as **Returned** for all transactions where quantity is greater than 3 AND product is not Furniture.
8. Remove all transactions where:
	- payment status is unknown
	- AND return status is unknown
	- AND total value (before discount and tax) is below 150
9. Identify customers who have at least one returned item.
10. Identify customers who have never returned anything.
11. Identify product categories that generate the highest total revenue (sum of computed revenue per category, no grouping output required beyond filtering logic).
