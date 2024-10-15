<h2 style="color:darkblue;"> <strong>RAG but better: Multi-Query Retriever Approach</strong> 🚀</h2>

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
   CREATE TABLE embeddings (
      id SERIAL PRIMARY KEY,
      text_content TEXT,  -- optional, to store associated text or metadata
      embedding vector(1536)  -- size of the vector (e.g., 1536 dimensions for OpenAI models)
   );
   ```