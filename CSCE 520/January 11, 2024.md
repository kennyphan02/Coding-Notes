Database - collection of related data that is managed by a ***DBMS (Database Management System)***
A DBMS is expected to: 
1. Allows users to create new databases and specify their ***schema (logical structure)*** using ***Data Definition Language (DDL)***
2. Allows users to query the data and modify the data using a specialized language called ***query language***. Query language is a form of ***data manipulation language***. 
3. Efficient Access/Storing large amounts of data 
4. Enables recovery of a database in the event of failure, or intentional misuse.

**Transaction** - A set of "read" and "write" operations 
- A transaction is said to be properly implemented if it passes the **ACID** test. 

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
