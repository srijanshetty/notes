NoSQL
=====
- **Schema less**: You do not have to define the explicit schema,
    albeit there always is an implicit schema.
- **Distributed**: Can be distributed across a cluster of machines,
    ergo is good for **data intensive** applications.
- **Impedance Mismatch**: The model of the database and application
    is not the same. **Easy development, agile development**.

Types
=====
# Aggreagate Oriented
- You have aggregates: **Objects, Documents** that you push into
    the database and out.
- **Key Value, Document, Column**

# Graph oriented
- You deal with relationships

Impedance Mismatch
===================
- In Relational database, you have to break down your data model
    into tables which are unrelated.
- So, while at the application level you have this concept of nice
    aggregates, it is not reflected in the database.

Traditional Databases
=====================
- All the rows are stored in a row major fashion.
- This means that it is very easy to read entire rows at once.
- So queries with high projectivity (reading a lot of columns) or
queries with high selectiviyt (high number of rows end up in the
results) are IO performant.

Column Databases
================
- Column major format
- This allows an entire column to be read at once.
- Assembling rows together is a difficult task since they are scattered
across the disk.
- Queries with low selectivity are the ones that shine.
- For every additional column read, we have an overhead of a disk seek.

# Hybrid approaches
- Divide the table into row groups and for each row group, the data is
stored in a column major format
- This is called PAX.
- Row reconstruction becomes cheaper as compared to a totally column
oriented architecture.
- But to read a column, we have to load in multiple row groups.

# Compression
- Since the values in a column are similar, they are highly amenable
to compresion saving read time and disk space.
