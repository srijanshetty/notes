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
