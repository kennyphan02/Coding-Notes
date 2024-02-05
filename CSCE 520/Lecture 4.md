No 2 tuples may agree on all the attributes of a relation. (each tuple must be unique)
- One or more attributes may be declared as the PRIMARY KEY or UNIQUE

### Creating a Relation
```SQL
CREATE TABLE <name of the relation> (
	<list of attributes>
);
```
e.g:
```SQL
CREATE TABLE Student(
	name VARCHAR(30),
	dateOfBirth DATE,
	studentID INT,
	major VARCHAR(20),
	gpa DECIMAL(3,2),
	ssn CHAR(11) PRIMARY KEY
);
```

### Multi-attribute key 
```SQL
CREATE TABLE Student (
	name VARCHAR(30),
	dateOfBirth DATE,
	PRIMARY KEY(name, dateOfBirth)
);
```
- A primary key can never be NULL but attributes declared UNIQUE may have NULL values.

### Modifying a Relation
- To add an attribute
`SQL > ALTER TABLE <relation name> ADD <attr><datatype>;`
E.G `ALTER TABLE STUDENT ADD phoneNumber CHAR(13);`
- To delete an attribute
`SQL > ALTER TABLE <relatoin name> DROP <attr>;
E.G `ALTER TABLE STUDENT DROP MAJOR`

### Default Values
`ALTER TABLE Student ADD phoneNumber CHAR(13) DEFAULT 'unlisted';`

### Deleting a Relation
`SQL > DROP TABLE <Relation Name>;`

### Relational Algebra
- A mathematical system that consists of operations and operands
- Operands are relations in a database
- Union (different tuples)
- Intersection (Share the same tuples)
- Subtraction (Find the similar tuples and remove it)
- Pre condition for Union, Intersection, and subtraction
	- both relations (X and Y) must have the same schema. 
	- The ***order of attributes in both relations must be the same***
- 