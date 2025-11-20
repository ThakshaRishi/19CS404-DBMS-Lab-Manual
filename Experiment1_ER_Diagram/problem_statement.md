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
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_fitness.png)

<img width="981" height="704" alt="image" src="https://github.com/user-attachments/assets/a1ac6074-4c46-413c-8cdb-8fca0d4e7896" />

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

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
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

<img width="832" height="636" alt="image" src="https://github.com/user-attachments/assets/4cd40594-a25c-4cf1-84eb-94e85eeb1b6d" />

### Entities and Attributes
| **Entity**         | **Attributes (PK, FK)**                                        | **Notes**                                                     |
| ------------------ | -------------------------------------------------------------- | ------------------------------------------------------------- |
| **Member**         | **MemberID (PK)**, Name, Email                                 | A member can make loans and attend events.                    |
| **Loan**           | **LoanID (PK)**, BorrowDate, LoanExpiryDate, **MemberID (FK)** | A loan is made by one member and covers one book.             |
| **Book**           | **ISBN (PK)**, Name, Author                                    | A book can be part of many loans.                             |
| **Fine**           | **FineID (PK)**, Amount, DateExceeded, **LoanID (FK)**         | A fine is generated when a loan exceeds expiry.               |
| **Event**          | **EventID (PK)**, Date, Time, Venue                            | Members attend events; events use rooms.                      |
| **Rooms**          | **RoomNumber (PK)**, Capacity, Availability                    | Rooms are used for events and host an author/speaker session. |
| **Author/Speaker** | **SpeakerID (PK)**, Name, GenreFocus                           | Conducts events in rooms.                                     |


### Relationships and Constraints

| **Relationship**                     | **Cardinality** | **Participation**                    | **Notes**                                                              |
| ------------------------------------ | --------------- | ------------------------------------ | ---------------------------------------------------------------------- |
| **Member – Makes – Loan**            | 1 : M           | Member (mandatory), Loan (mandatory) | One member can make many loans; each loan belongs to one member.       |
| **Loan – Covers – Book**             | M : 1           | Loan (mandatory), Book (mandatory)   | A loan covers exactly one book; a book can appear in multiple loans.   |
| **Loan – Generates – Fine**          | 1 : M           | Loan (optional), Fine (mandatory)    | A loan may generate zero or many fines; each fine belongs to one loan. |
| **Member – Attends – Event**         | M : M           | Both optional                        | Members can attend many events; events have many attendees.            |
| **Event – Use – Rooms**              | M : 1           | Event (mandatory), Rooms (optional)  | An event uses one room; a room can host many events.                   |
| **Rooms – Conduct – Author/Speaker** | 1 : 1           | Both mandatory                       | One author/speaker conducts an event in exactly one room at a time.    |


### Assumptions

Each loan is strictly linked to one book (not multiple books per loan).

A member can exist without creating loans or attending events.

Fines only exist if a loan has exceeded its expiry date.

Every event must be held in a room.

Author/Speaker is treated as its own entity, not part of Member.

Each event has one speaker, and each speaker conducts one event at a time.

Room availability indicates whether the room can host events.

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
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_restaurant.png)

<img width="835" height="696" alt="image" src="https://github.com/user-attachments/assets/796fd0f8-1a5e-48c4-b353-d81640426f5f" />




### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
