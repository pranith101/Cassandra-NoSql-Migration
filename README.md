# Cassandra-NoSql-Migration
Cassandra Data Modeling of High Frequency Data

Goals

Populate Elassandra (Formerly Cassandra) with Radius data.
Reduce the write load by removing this data from the RDBMS.

Background and strategic fit
This is part of an ongoing strategy to reduce the load on the current RDBMS shifting the high frequency and unstructured data into Elassandra. This is two part, one for future analytics and also to speed up current reporting.

Assumptions
This data is used mostly for reporting and is high frequency. However there is no reason to store this in an RDBMS as:
It is not critical data requiring transactional integrity.
The data can change or be more easily enriched without requiring structural changes to the db.
The data will be stored in a message queue (MQ). Peferred choice is Kafka this provides.

Redundancy
The Radius authentication will still take place on the RDBMS.
