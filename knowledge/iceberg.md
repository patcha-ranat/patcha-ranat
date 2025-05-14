# Apache Iceberg

*Patcharanat P.*

*Apache Iceberg is a high performance open-source format for large analytic tables. Iceberg enables the use of SQL tables for big data while making it possible for engines like Spark, Trino, Flink, Presto, Hive, Impala, StarRocks, Doris, and Pig to safely work with the same tables, at the same time.*

When we're thinking of modern data architecture (at the time this note is written), we could think of ***Data Lakehouse***. There're some outstanding technology that apply this concept to its functionality; *Apache Hudi, Apache Iceberg, and Delta Lake*

*Iceberg is known for its schema evolution capabilities and broader ecosystem integration, while Delta Lake excels in ACID transactions and tight integration with Databricks.*

## Tabel of Contents
- [What is Data Lakehouse / Open Table Format?](#what-is-data-lakehouse--open-table-format)
- [What Functionality Iceberg Offer](#what-functionality-iceberg-offer)
- [Basic Usage](#basic-usage)
    - [Creating Iceberg Table Foramt](#creating-iceberg-table-format)
    - [Upsert](#upsert)
    - [Schema Evolution](#schema-evolution)
    - [Partition Evolution](#partition-evolution)
    - [Data Versioning (Time Travel and Table Rollback)](#data-versioning-time-travel-and-table-rollback)
- [References](#references)

## What is Data Lakehouse / Open Table Format?

Storing Tabular Data with Blob/Object storage (filesystem-like) with additional some rich features that benefit in data governance and management.
- Data
- Metadata for the data

## What Functionality Iceberg Offer

- Data Versioning (Time Travel and Table Rollback)
    - Data & Metadata
- Indexing
- ACID Properties
    - Allow Concurrency Reading/Writing
- Upsert Data
- Schema Evolution
    - No need to drop existing table and create a new one to adjust table schema

## Basic Usage

### Creating Iceberg Table Format

We can create a table with both via spark and spark SQL
- Spark required some specific dependencies to be used and some storage path specified.
- SQL is required to use `USING iceberg` in DDL script (like `USING delta`) which can be executed through spark sql session.

### Upsert

*executed by spark sql*

```sql
MERGE INTO ... 
USING ... 
ON ... 
WHEN MATCHED 
    THEN UPDATE ... 
WHEN NOT MATCHED 
    THEN INSERT ...
```

### Schema Evolution

*executed by spark sql*

- Check Table properties

```sql
DESCRIBE EXTENDED <env>.<schema>.<table_name>
```

- Rename Column

```sql
ALTER TABLE ... RENAME COLUMN ... TO ...
```

- Add Column Comment

```sql
ALTER TABLE ... ALTER COLUMN ... COMMENT "..."
```

- Change Data Type

```sql
ALTER TABLE ... ALTER COLUMN ... TYPE ...
```

- Change Column Order in a Table

```sql
ALTER TABLE ... ALTER COLUMN ... AFTER ...
```

- Add Column (no need to drop existing table and create a new one)

```sql
ALTER TABLE ... ADD COLUMN ...<column_name> <data_type> AFTER ...
```

- Delete Column

```sql
ALTER TABLE ... DROP COLUMN ...
```

### Partition Evolution

*executed by spark sql*

```sql
ALTER TABLE ...
ADD PARTITION FIELD <column_name>
```

### Data Versioning (Time Travel and Table Rollback)


Data & Metadata: Contains schema and all changes on a table

- Query From Metadata json file

```sql
SELECT snapshot_id, manifest_list
FROM <env>.<schema>.<table_name>.snapshots
```

- View table history

```sql
SELECT * FROM <env>.<schema>.<table_name>.history
```

- Rollback to Specific Version

```sql
CALL system.rollback_to_snapshot("<env>.<schema>.<table_name>", <snapshot_id>)
```

## References
Quite an interesting blog written in Thai, demonstrating practical example of apache iceberg, not just in abstract way.
- [What is Apache Iceberg](https://mesodiar.com/2023/06/24/what-is-apache-iceberg-iceberg/)