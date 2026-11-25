datamodels?
- relational
- hiarichal 
- network


Sql
relational data modle -> RDBMS Ex. MySql oraclr
object relational data modal -> ORDBMS Ex Post Sql

NoSql
Documens dat model -> MongoDb 
Key value pair -> Nodis


>**Sql** 
>Data Modal: relational data modal  
>Schema
>Scalability: vertical scalability
>consistency: follows acid properties
>complex queries : can write   

> **Nosql**
> Data Modal: key value, document wide column
> Schemaless - structure not fixed
> Scalability: horizontal
> consistency : acid properties may or may not follow
> complex queries : cant write


Functional dependency
R ( x,y,z )
x -> y  
- x determines y
- y dependent attribute
- x determinant
x -> w
y -> z

closer property?
- how many attribute can be determined from a variable?

Keys?
- super key
	- set of attribute that can uniquly determine an entity set 
- candidate key
	- smallest subset of super key 
- composite key
	- when primary key needs 2 or more attributes  

Normalization?
- reduce redundancy - duplicate data
	- can reduce redundancy to 0% -> needs it to relate data
- remove anomalies
- Levels/ methods to remove normalization
	- 1NF, 2Nf, ..
- 2NF 
	- 1NF + No partial dependency
		- when a perticular attribute depends on part of candidate keys
		- x,y -> m 
		- x -> w
		- y -> z
- 3NF 
	- No transitive dependency
	- if 
		- x -> y
		- y -> z
	- then 
		- x -> z 
		- should be there 
- BCNF



# SQL
- DDL
	- create 
	- alter
	- update
		- drop or truncate difference?
		- create indexing?
- DML 
	- insert
	- update 
	- delete
- BCM
	- deal with permission
- TCL
	- commit
	- rollback
	- save points
- DQL
	- select
- Join
	- inner join 
	- outer join
	- left outre join
	- right outer join
	- cross join
	- self join
	- 