## README.md
# Database Schema (DDL) - Airbnb Clone

This directory contains the SQL script `schema.sql` used to define the database schema for the Airbnb clone project.

## Tables Included

- users
- properties
- bookings
- payments
- reviews
- messages

Each table includes:
- Primary keys
- Foreign keys for relationships
- ENUM types for statuses and roles
- Indexes for performance

## How to Use

To execute the schema and create the database structure, run:

```bash
mysql -u your_username -p your_database < schema.sql
