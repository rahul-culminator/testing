# README

## Script Overview

`action.py` is a script that automates the process of building the action schema in a PostgreSQL database. The script performs the following tasks:

1. Running AWS Glue jobs.
2. Creating tables, indices, and performing post-load operations in the PostgreSQL database.

## Prerequisites

### AWS Authentication

To connect to AWS, follow these steps in a new terminal:

1. Load the required configuration and use sandbox:
  
2. Login to AWS SSO

### PostgreSQL Connection

Establish the appropriate tunnel for the PostgreSQL database instance in the terminal.

## Steps to Follow

### Step 1: Setup the Environment

Ensure you have the necessary AWS and PostgreSQL configurations set up as described above.

### Step 2: Clone the Repository

1. Clone the repository to your local machine:
    ```bash
    git clone https://github.com/CulminationGithub/postgresdb.git
    ```
2. Navigate to the cloned repository in a new terminal.

3. Update the `config_sandbox.yaml` file with the appropriate port number used in the tunnel. For example, if the tunnel command is:
    ```bash
    ssh -L5434:10.**.17.**:5432 jupyter_dev
    ```
    Then set the port in `config_sandbox.yaml` to `5434`:
    ```yaml
    port: 5434
    ```

### Step 3: Drop the Action Schema

Manually drop the existing action schema in the PostgreSQL database using the following command:
```sql
DROP SCHEMA action CASCADE;
```

### Step 4: Run the Script

Run the `action.py` script:
```bash
python3 action.py
```

This will automate the process of running the Glue jobs and setting up the action schema in the PostgreSQL database.
