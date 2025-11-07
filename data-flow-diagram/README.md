# Airbnb Clone Backend — Data Flow Diagram (DFD)

## Objective

This document presents a Data Flow Diagram (DFD) that illustrates how data moves through the Airbnb Clone backend system. It captures the flow of information between users, system processes, and data stores, helping developers understand how core operations are structured and interconnected.

---

## Overview

The DFD visualizes the interactions between three key user roles — **Guest**, **Host**, and **Admin**, and the backend system. It highlights how data is input, processed, stored, and output across major functionalities such as property management, bookings, payments, reviews, and messaging.

---

## External Entities

- **Guest**: Searches properties, books stays, makes payments, sends messages, and writes reviews.
- **Host**: Lists properties, receives bookings, communicates with guests, and manages listings.
- **Admin**: Oversees users, listings, bookings, and payment notifications via the admin dashboard.

---

## Core Processes

### 1. User Management
- Handles registration, login, profile updates, and role-based access.
- Stores user data in the `Users` database.

### 2. Listing Management
- Hosts can add, edit, or delete property listings.
- Listings are stored in the `Properties` database.

### 3. Booking Management
- Guests book properties and cancel reservations.
- Bookings are validated and stored in the `Bookings` database.

### 4. Payment Processing
- Guests make payments via external gateways (e.g., Stripe, PayPal).
- Hosts receive payouts.
- Payment records are stored in the `Payments` database.

### 5. Review System
- Guests leave reviews and ratings.
- Hosts can respond to reviews.
- Reviews are stored in the `Reviews` database.

### 6. Messaging
- Enables communication between guests and hosts.
- Messages are stored in the `Messages` database.

---

## Data Stores

- `Users`: Stores user profiles and roles
- `Properties`: Stores property listings
- `Bookings`: Stores reservation details
- `Payments`: Stores transaction records
- `Reviews`: Stores ratings and feedback
- `Messages`: Stores user communications

---

## How to Use This Diagram

- **Developers**: Use it to design database schemas and API endpoints.
- **Architects**: Reference it for system modularity and data flow optimization.
- **QA Engineers**: Identify test cases based on data interactions.