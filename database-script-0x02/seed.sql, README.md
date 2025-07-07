-- ===============================
-- USERS
-- ===============================
INSERT INTO users (user_id, first_name, last_name, email, password_hash, phone_number, role)
VALUES
('11111111-1111-1111-1111-111111111111', 'Alice', 'Wanjiru', 'alice@example.com', 'hashpass1', '0712345678', 'guest'),
('22222222-2222-2222-2222-222222222222', 'Brian', 'Otieno', 'brian@example.com', 'hashpass2', '0722333444', 'host'),
('33333333-3333-3333-3333-333333333333', 'Clara', 'Mwangi', 'clara@example.com', 'hashpass3', NULL, 'guest');

-- ===============================
-- PROPERTIES
-- ===============================
INSERT INTO properties (property_id, host_id, name, description, location, price_per_night)
VALUES
('aaaaaaa1-aaaa-aaaa-aaaa-aaaaaaaaaaaa', '22222222-2222-2222-2222-222222222222', 'Nairobi Apartment', 'Modern 2 bedroom apartment in Kilimani', 'Nairobi', 55.00),
('aaaaaaa2-aaaa-aaaa-aaaa-aaaaaaaaaaaa', '22222222-2222-2222-2222-222222222222', 'Mombasa Beach House', 'Ocean-view house ideal for families', 'Mombasa', 120.00);

-- ===============================
-- BOOKINGS
-- ===============================
INSERT INTO bookings (booking_id, property_id, user_id, start_date, end_date, total_price, status)
VALUES
('b1111111-bbbb-bbbb-bbbb-bbbbbbbbbbbb', 'aaaaaaa1-aaaa-aaaa-aaaa-aaaaaaaaaaaa', '11111111-1111-1111-1111-111111111111', '2025-08-01', '2025-08-05', 220.00, 'confirmed'),
('b2222222-bbbb-bbbb-bbbb-bbbbbbbbbbbb', 'aaaaaaa2-aaaa-aaaa-aaaa-aaaaaaaaaaaa', '33333333-3333-3333-3333-333333333333', '2025-07-15', '2025-07-18', 360.00, 'pending');

-- ===============================
-- PAYMENTS
-- ===============================
INSERT INTO payments (payment_id, booking_id, amount, payment_method)
VALUES
('p1111111-pppp-pppp-pppp-pppppppppppp', 'b1111111-bbbb-bbbb-bbbb-bbbbbbbbbbbb', 220.00, 'credit_card');

-- ===============================
-- REVIEWS
-- ===============================
INSERT INTO reviews (review_id, property_id, user_id, rating, comment)
VALUES
('r1111111-rrrr-rrrr-rrrr-rrrrrrrrrrrr', 'aaaaaaa1-aaaa-aaaa-aaaa-aaaaaaaaaaaa', '11111111-1111-1111-1111-111111111111', 5, 'Loved the place, very clean and central!');

-- ===============================
-- MESSAGES
-- ===============================
INSERT INTO messages (message_id, sender_id, recipient_id, message_body)
VALUES
('m1111111-mmmm-mmmm-mmmm-mmmmmmmmmmmm', '11111111-1111-1111-1111-111111111111', '22222222-2222-2222-2222-222222222222', 'Hi Brian, is the Nairobi apartment available next month?');


## README.md
# Seed SQL Script - Airbnb Clone

This script populates the database with realistic test data for development and testing.

## Entities Populated

- Users (3 entries)
- Properties (2 entries)
- Bookings (2 entries)
- Payments (1 entry)
- Reviews (1 entry)
- Messages (1 entry)

## How to Use

To populate your database after creating the tables, run:

```bash
mysql -u your_username -p your_database < seed.sql
