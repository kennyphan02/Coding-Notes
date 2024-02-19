Database - collection of related data that is managed by a ***DBMS (Database Management System)***
A DBMS is expected to: 
1. Allows users to create new databases and specify their ***schema (logical structure)*** using ***Data Definition Language (DDL)***
2. Allows users to query the data and modify the data using a specialized language called ***query language***. Query language is a form of ***data manipulation language***. ***(DML)***
3. Efficient Access/Storing large amounts of data   (efficient access/storing of data)
4. Enables recovery of a database in the event of failure, or intentional misuse.  (backup recovery) 

**Transaction** - A set of "read" and "write" operations 
- A transaction is said to be properly implemented if it passes the **ACID** test. 
	- Atomicity
	- Consistency
	- Isolation
	- Durability

***Atomicity***
- All-or-nothing rule for execution of transactions

***Isolation*** - every transaction must appear to execute as if in isolation (there are no other tranactions executing at the same time). transactions are independently processed 
Database vs physical file system comparisons

Example: Wyatt sending $50 to Caleb
1. Read Wyatt's account balance
2. Check if wyatt's balance >= 50 
3. Update wyatt's account balance = wyatt's account balance - 50
4. Read caleb's account balance
5. update caleb's account balance = caleb's account balance + 50 
6. STOP 
Before the transaction starts, wyatt's accountbalance = $850 
caleb's account balance = $750
after the transaction ends, wyatt's accountbalance = $800
caleb's account balance = $800

Sum of both account balances, before and after transactions = $1600 

**Consistency** - it preserves the correctness of a database
**Durability** - The effect of a transaction must never be lost once the transaction is complete. E.g changes to Wyatt's and Caleb's account balance should be valid until the next update. 

Transaction Processor 
- ***Concurrency control manager/scheduler***-  maintains isolation for all transactions achieved by maintaining locks on certain pieces of data. 
	- those locks prevent 2 transactions from accessing the same piece of data in ways that interact badly. 
	- locks are stored in main-memory dock table
- Deadlock resolution - as transacitons compete for resources tthrough docks that a scheduler grants, they can get into a situation where no transaction can proceed, as each transaction needs something the other transaction has. 
	- the transaction processor interferes and cancels 1 of more transactions tto let the others proceed. 
- Logging - to ensure durability, every change in the database is logged spearately on the disk
	- Initially, the log manager writes the logs in buffers and then negotiates with the buffers. buffers are written to disk
- Data Model
	- A mathematical representation of data parts of a data model. 
	- Parts of a data model:
		- structure of the data 
		- operations on data
		- constraints
I. semi-structured model - it is based on trees
E.G Movies 
	-> title
	-> genre
	-> length
	-> age rating 
	-> audience rating
XML - extensible markup language 
```
<?xml version= "1.0" encoding = "utf-8"> 
<movies>
	<movie title="Whiplash">
	<year> 2014 </year>
	<length> ... </length>
</movies>

alternative way 

<movie> <title> ... </title>
		<year> ... </year>
		<length> ... </length>
</movie>
```
Relational Model

| O | O | O | O |
| ---- | ---- | ---- | ---- |
| Item 1 | Item 2 | Item 3 | Item 4 |
| Item 4 | Item 5 | Item 6 | Item 8 |
Attributes
- The columns of  a relation are named by its attributes
- describes the meaning of the entries in the column below 
- A database consists of 1 or more relations

**Relation Schema**
```
< Name of the relation > + <set of attributes for the relation> 
```
e.g Student(name, ID, major, gpa, grade level)

Database Schema
- the set of all relation schemas

Tuple
- The rows of a relation except the header rows 
- Relational model requires each component of each tuple to be atomic (same elementary type) 
- SQL - Structured query language 

**Data Types**
- Int/integers
	- Denotes integer values
- Float/ real 
	- denotes floating point values 
- Decimal (n,d)
	- 1357.23 -> Decimal(6,2)
	- n -> total # of digits
	- d -> position of the decimal point from the right
- Char(n)
	- a fixed-length string of "n" characters 
	- 'apple' -> char(5)
	- 'pie' will turn into 'pie__' adds trailing blanks
- varchar(n)
	- a variable-length string of up to 'n' characters
	- e.g 'orange' -> varchar(6)
	- pie -> 
- Date
	- date "yyyy-mm-dd"
	- e.g "16 Jan 2024" -> DATE "2024-01-16"
- Time
	- TIME 'hh:mm:ss'
	- e.g: 11:45 am TIME '11:45:00'
	- e.g: 15 seconds after 1:30pm  TIME "13:30:15'
	- uses the military clock (24-hour time)
- Boolean
	- TRUE
	- FALSE
	- UNKNOWN

- SQL encloses strings in single quotes
- e.g 'John'
- e.g 'John's car' (would throw error cause of 2nd ') so -> 'John"s car'. " gives a literal single quote"
- any value can be null