# Database Table Designs

In order to store fish, users, orders and carts, these are the tables we'll need:

## Fish Table

All the fish that Fishy Business is selling will be stored in here

| Column Name | Description |
|---|---|
| fish_id | ID for each fish |
| name | Name of fish |
| description | Info about fish |
| size | Size or weight |
| condition | Live, dead or filleted |
| price | Price of fish |
| price_per_lb | Price per pound |
| quantity | How many in stock |
| availability | Available or unavailable |
| image | Picture of fish |

Admins should be allowed to do things like add fish, change prices, edit details and update stock

## Users Table

Stores customer and admin accounts within Fishy Business

| Column Name | Description |
|---|---|
| user_id | Unique ID for each user |
| username | Account username |
| email | Email for login |
| password_hash | Encrypted password |
| role | Customer or admin |

Admins can work to manage store meanwhile users can log in, buy fish, and view orders

## Orders Table

Stores orders that customers will place

| Column Name | Description |
|---|---|
| order_id | Unique order ID |
| user_id | User who made the order |
| order_date | When order was made |
| total_price | Total cost |
| status | Pending, completed or canceled |

Admins can see orders and update their status, perhaps automatically in future

## Order Items Table

Stores the fish in each order

| Column Name | Description |
|---|---|
| order_item_id | Unique ID |
| order_id | Order it belongs to |
| fish_id | Fish being bought |
| quantity | How many were bought |
| price | Price when purchased |

Allowed for customers to be able to buy more than one type of fish in an order

## Cart Table

Stores shopping carts for users

| Column Name | Description |
|---|---|
| cart_id | Unique cart ID |
| user_id | User who owns the cart |
| created_at | When cart was made |
| updated_at | Last time cart was changed |

Can save fish inside their cart and then be able to come back later with it still saved

## Cart Items Table

Stores the fish added to the carts

| Column Name | Description |
|---|---|
| cart_item_id | Unique ID |
| cart_id | Cart it belongs to |
| fish_id | Fish added to cart |
| quantity | How many they want |

Users can add or remove fish, and change quantities with ease

## Table Relationships

- One user can have more than one order
- One order will be able to have multuple fishes
- Each order item connects to a fish listed in table
- Each user should have their own cart
- One cart can have a bunch of fish
- Each cart item connects to a fish in table

## Admin Features

- Add a new fish to table
- Edit info of fish
- Change prices of fish
- Update stock of fish
- Mark fish as no longer available if need be
- Add or change pictures of fish
- View status of customer orders
- Update order status for customers

These tables should be sufficient in covering what we need for the project
