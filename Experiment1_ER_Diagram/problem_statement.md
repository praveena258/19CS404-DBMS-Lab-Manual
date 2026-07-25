# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
<img width="1032" height="562" alt="P1 drawio" src="https://github.com/user-attachments/assets/d60b234a-31f1-4170-918c-e17507f7eb16" />


### Entities and Attributes

| Entity   | Attributes (PK, FK)                                              | Notes                                    |
| -------- | ---------------------------------------------------------------- | ---------------------------------------- |
| Members  | **Membership_ID (PK)**, Name, Phone, Membership_Type, Start_Date | Stores member details                    |
| Programs | **Program_ID (PK)**, Program_Name, Duration, Schedule            | Stores fitness program details           |
| Trainers | **Trainer_ID (PK)**, Name, Contact, Specialization               | Stores trainer information               |
| Session  | **Session_ID (PK)**, Date, Attendance, Payment                   | Stores personal training session details |



### Relationships and Constraints
| Relationship                    | Cardinality | Participation | Notes                                                                            |
| ------------------------------- | ----------- | ------------- | -------------------------------------------------------------------------------- |
| Members — Enrolls In — Programs | M:N         | Total         | A member can enroll in multiple programs and each program can have many members. |
| Trainers — Conducts — Programs  | M:N         | Total         | Trainers may conduct multiple programs, and programs may have multiple trainers. |
| Members — Books — Session       | 1:M         | Partial       | One member can book many sessions.                                               |
| Trainers — Conducts — Session   | 1:M         | Total         | One trainer can conduct multiple sessions.                                       |


### Assumptions
Each session is booked by only one member.
Each session is conducted by one trainer.
Attendance and payment are recorded for every session.

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
<img width="1032" height="690" alt="P2 drawio" src="https://github.com/user-attachments/assets/69bbc029-238e-4b3d-b19a-b3df76ad151f" />


### Entities and Attributes

| Entity  | Attributes (PK, FK)                                              | Notes                        |
| ------- | ---------------------------------------------------------------- | ---------------------------- |
| Members | **Membership_ID (PK)**, Name, Phone, Membership_Type, Start_Date | Stores member information    |
| Book    | **Book_ID (PK)**, Title, Author, Genre                           | Stores book details          |
| Loan    | **Loan_ID (PK)**, Date, Return_Date, Fine                        | Stores borrowing records     |
| Event   | **Event_ID (PK)**, Name, Date, Number                            | Stores library event details |



### Relationships and Constraints

| Relationship                | Cardinality | Participation | Notes                                                                               |
| ---------------------------   | ----------- | ------------- | ----------------------------------------------------------------------------------- |
| Members — Borrows — Book   | M:N         | Partial       | Members can borrow many books |
| Members — Registers — Event | M:N         | Partial       | Members can register for multiple events.                    |
| Members — Gets — Loan       | 1:M         | Total         | One member can have multiple loan records.                                          |
| Book — Included In — Loan   | 1:M         | Total         | A book can appear in multiple loan records over time.                               |


### Assumptions
A loan record represents one borrowing transaction.
Overdue fines are calculated based on the return date.
Members can participate in multiple events

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
<img width="1507" height="696" alt="P3 drawio" src="https://github.com/user-attachments/assets/4fa82a01-992e-4a89-9d7f-8fc707015442" />


### Entities and Attributes

| Entity      | Attributes (PK, FK)                              | Notes                      |
| ----------- | ------------------------------------------------ | -------------------------- |
| Customer    | **Customer_ID (PK)**, Name, Phone                | Stores customer details    |
| Reservation | **Reservation_ID (PK)**, Date, Time, No_of_Guest | Stores reservation details |
| Order       | **Order_ID (PK)**, Date, Amount                  | Stores food order details  |
| Dish        | **Dish_ID (PK)**, Name, Category, Price          | Stores menu information    |
| Waiter      | **Waiter_ID (PK)**, Name, Contact                | Stores waiter details      |


### Relationships and Constraints

| Relationship                   | Cardinality | Participation | Notes                                                                   |
| ------------------------------ | ----------- | ------------- | ----------------------------------------------------------------------- |
| Customer — Makes — Reservation | 1:M         | Total         | One customer can make multiple reservations.                            |
| Reservation — Has — Order      | 1:M         | Total         | One reservation can include multiple orders.                            |
| Order — Contains — Dish        | M:N         | Total         | An order can contain many dishes, and a dish can appear in many orders. |
| Waiter — Serves — Reservation  | 1:M         | Total         | One waiter can serve multiple reservations.                             |


### Assumptions
Each reservation is assigned to one waiter.
Bills are generated from the total amount of ordered dishes.
A customer may place multiple orders during a reservation.


---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
