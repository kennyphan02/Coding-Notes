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
CREATE TABLE Student (
	name VARCHAR(30),
	dateOfBirth DATE,
	PRIMARY KEY(name, dateOfBirth)
);
- A primary key can never be NULL but attributes declared UNIQUE may have NULL values.