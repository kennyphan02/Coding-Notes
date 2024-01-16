Database - collection of related data that is managed by a ***DBMS (Database Management System)***
A DBMS is expected to: 
1. Allows users to create new databases and specify their ***schema (logical structure)*** using ***Data Definition Language (DDL)***
2. Allows users to query the data and modify the data using a specialized language called ***query language***. Query language is a form of ***data manipulation language***. ***(DML)***
3. Efficient Access/Storing large amounts of data 
4. Enables recovery of a database in the event of failure, or intentional misuse.

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
XML - e