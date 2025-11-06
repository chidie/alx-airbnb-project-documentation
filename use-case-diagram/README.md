# Airbnb Clone Backend — Use Case Diagram

## Objective

This document presents a use case diagram that visualizes the key interactions between users and the backend system of the Airbnb Clone project. It helps developers and stakeholders understand the functional scope, user roles, and system responsibilities required to build a scalable, secure, and feature-rich rental marketplace.

---

## Overview

The use case diagram illustrates how three primary actors—**Guest**, **Host**, and **Admin**—interact with the backend system. Each actor is associated with specific functionalities that reflect their role in the platform.

The system is represented as a central node labeled **"Airbnb Backend System"**, with use cases branching out as ovals connected to each actor.

---

## 👥 Actors and Their Use Cases

### 👤 Guest
- `Register` — Create a new account
- `Login` — Authenticate with email/password or OAuth
- `Search Properties` — Browse listings based on filters
- `Book Property` — Reserve a property for specific dates
- `Make Payment` — Pay for bookings securely
- `Leave Review` — Rate and review properties after stay
- `Send Message` — Communicate with hosts

### 👤 Host
- `Register` — Sign up as a host
- `Login` — Access host dashboard
- `Add/Edit/Delete Property` — Manage property listings
- `View Bookings` — See upcoming and past reservations
- `Receive Payment` — Get paid after guest stays
- `Respond to Review` — Reply to guest feedback
- `Send Message` — Communicate with guests

### 👤 Admin
- `Manage Users` — Monitor and moderate user accounts
- `Monitor Listings` — Review and approve property listings
- `View All Bookings` — Access system-wide booking data
- `Manage Payments` — Oversee transactions and resolve issues

---

## Technical Notes

- The diagram is designed using **Draw.io** and follows UML standards for use case modeling.
- Each use case is represented as an oval and connected to its respective actor via straight lines.
- Actors are depicted as stick figures with labels: `Guest`, `Host`, and `Admin`.

---


---

## How to Use This Diagram

- **Developers**: Use it to guide API design and database schema planning.
- **Product Managers**: Reference it for feature prioritization and user flow mapping.
- **QA Engineers**: Use it to define test cases based on user interactions.

---

## Next Steps

- Implement RESTful endpoints for each use case
- Define role-based access control (RBAC) for actors
- Link use cases to database tables and business logic

---

## Author

Chidiebere — Controls & Software Engineer  
Building scalable platforms for inclusive digital experiences.

---

## License

This documentation is for educational and planning purposes. Feel free to fork, adapt, and contribute.



