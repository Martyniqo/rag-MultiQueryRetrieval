# Project Name

## Overview
This project involves storing and working with embeddings in PostgreSQL. To enable this functionality, the `pgvector` extension is required, which allows PostgreSQL to handle vector data types for embedding storage and operations.

## Prerequisites

Before you can store embeddings in PostgreSQL, you must install the `pgvector` extension. Follow the steps below to set it up.

### System Requirements:
- PostgreSQL 12 or later (the guide below is for PostgreSQL 16)
- `git`, `make`, `gcc`, and `postgresql-server-dev-16`

### Installation Steps:

1. **Ensure the required packages are installed**:
   Run the following command to install necessary build tools and PostgreSQL development files:

   ```bash
   sudo apt update
   sudo apt install git make gcc postgresql-server-dev-16

   sudo apt search pgvector
   sudo apt install postgresql-pgvector
   ```

2. **Enable extension**:
   
   ```sql
   CREATE EXTENSION IF NOT EXISTS vector;
   ```

3. **Create table for embeddings**:
   
   ```sql
   CREATE TABLE IF NOT EXISTS embeddings_256 (
    id SERIAL PRIMARY KEY,
    content TEXT,
    token_count INTEGER,
    embedding VECTOR(256),  -- Replace 256 with your desired dimensionality
    filename TEXT,
    parent_section TEXT,
    url TEXT);
   ```



