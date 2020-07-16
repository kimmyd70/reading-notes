## Database Normalization

[this article](https://www.essentialsql.com/get-ready-to-learn-sql-database-normalization-explained-in-simple-english/)

+ DN is organizing info into a table of rows and columns around a *specific* topic/purpose

+ Each table in your DB should have a specific purpose to avoid duplicate entries and make updating entries (or tables or the DB) easier and conflict free.

+ This also simplifies queries/sorts

+ This also keeps storage and performance optimal

+ Avoid Modification Anomalies:
    - Insert anomaly:  needing other data/facts before you can create the record

    - Update anomaly: creates inconsistencies if data appears in many places and you don't update them all

    - Deletion anomaly: if data is not separated, you risk losing one set of facts if you delete another

3 common forms that qualify the previous as you progress:(BCNF is another but more advanced)
    - First Normal Form (1NF): a relational table with each column containing atomic values and no repeating columns
    - 2NF all columns depend on the table's primary key
    - 3NF all columns are not transitively dependent on the primary key