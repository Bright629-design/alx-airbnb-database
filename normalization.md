# Normalization of Airbnb Database Schema

## Overview
The goal was to ensure all tables in our Airbnb-style schema comply with the Third Normal Form (3NF) to reduce redundancy, improve consistency, and enhance data integrity.

---

## 1. First Normal Form (1NF)
All tables were evaluated for atomicity of fields.

- Multi-valued or composite attributes were not present.
- All values are atomic (e.g., `email`, `name`, `location`).

1NF Achieved.

---

## 2. Second Normal Form (2NF)
Each table has a single-column primary key, so no partial dependencies exist.

2NF Achieved.

---

## 3. Third Normal Form (3NF)

### a) Property Table
- `location` was initially a free-text field. This may lead to redundancy and inconsistent naming.
- Normalization suggestion: move `location` to a separate `Location` table if multiple properties reuse cities or countries.

### b) Review Table
- Originally stored `user_id` and `property_id` alongside `booking_id`.
- These are transitively dependent via the `Booking` table.
- Fix: use only `booking_id` as FK. User and Property can be accessed through the booking.

3NF Achieved after these refinements.

---

## Summary

All tables comply with 3NF. Optional refinements were applied to ensure the elimination of transitive dependencies and ensure full functional dependency.
