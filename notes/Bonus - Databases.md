Database in Software Process

- Option 1 - each developer installs copy locally
- Option 2 - DB hosted remotely

Connect to db from project using api endpoint
need credetials set up

- use env variables for credentials
- Dev, Test and Prod db's
- use config file for different db's credentials
- also use config for log level

DevOps Engineer needs to:

- Configure DB
- Setup DB
- Manage DB

Database Types

Key Value

- Redis, Memcached, etcd
- no joins
- fast access but limited storage
- not for long-term storage
  Wide Column
- Cassandra
- schema-less
- no joins
- good for iot-records
  Document
- DynamoDB
- schema-less
- no joins
- collection
- good for mobile apps, CMS
  Relational DB
- MySQL
- structured
- schema with data types
- SQL
- rows and columns
- joins
- ACID (Atomicity, Consistency, Isolation, Durability)
  - no half-changes
  - all or nothing
    Graph
- DGraph
- directly connect entities
- used for detecting patterns
  Search
- conduct massive searches
- full test search
- ElasticSearch
