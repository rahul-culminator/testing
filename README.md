# PostgreSQL Cheat Sheet

## Connection

### Step 1: Connect to PostgreSQL using SSH Tunnel
First, establish an SSH tunnel to connect to the PostgreSQL server.

### Step 2: Connect to the Database
After connecting to the SSH tunnel, use the following command to connect to the PostgreSQL database:

```sh
psql --host=hostname -U username -d database
```

## Database Operations

### Connect to a Database
```sh
\c database_name
```

### List Tables, Views, and Sequences
```sh
\d
```

### List Tables Only
```sh
\dt
```


### List Views Only
```sh
\dv
```


### List Sequences Only
```sh
\ds
```

### Describe a Table: Show columns and their data types for a specific table.
```sh
\d table_name
```

### List Schemas
```sh
\dn
```

### List Indexes
```sh
\di
```

### List Functions
```sh
\df
```

### List Data Types
```sh
\dT
```

## User and Permission Management

### List Roles (Users)
```sh
\du
```

### List Databases
```sh
\l
```

### Quit psql
```sh
\q
```

### Display Command History
```sh
\s
```

### Show Active Connections
```sh
\conninfo
```


## Query Execution
### Run a Query
```sh
SELECT * FROM table_name;
```


## Backup and Restore
### Backup a Database
```sh
pg_dump database_name > backup_file.sql
```

### Restore a Database
```sh
psql database_name < backup_file.sql
```



## Schema Management

### Set the Search Path to a Specific Schema
```sh
SET search_path TO schema_name;
```

### Verify the Current Search Path
```sh
SHOW search_path;
```

## Script Execution
### Execute a Script File
```sh
\i filename.sql
```
