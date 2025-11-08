# Airbnb Clone Backend — Feature Requirements

## Objective

This document outlines the technical and functional requirements for core backend features of the Airbnb Clone project. It includes API endpoints, input/output specifications, validation rules, and performance criteria to guide development and ensure system robustness.

---

## 1. User Authentication

### ✅ Functional Requirements
- Allow users to register as `guest`, `host`, or `admin`
- Support login via email/password and OAuth (Google, Facebook)
- Issue JWT tokens for authenticated sessions
- Enable profile updates (name, email, phone, photo)

### API Endpoints

| Method | Endpoint              | Description                  |
|--------|-----------------------|------------------------------|
| POST   | `/api/auth/register`  | Register new user            |
| POST   | `/api/auth/login`     | Authenticate user            |
| GET    | `/api/users/me`       | Get current user profile     |
| PUT    | `/api/users/me`       | Update profile info          |

### Input Specifications

- `name`: string, required, max 100 chars
- `email`: string, required, valid email format
- `password`: string, required, min 8 chars
- `role`: enum (`guest`, `host`, `admin`)
- `phone`: optional, valid phone format

### Output Specifications

- JWT token
- User object (id, name, email, role, timestamps)

### ✅ Validation Rules

- Unique email constraint
- Password strength enforcement
- Role must match predefined enum
- Email format validation

### Performance Criteria

- Response time < 300ms for login and registration
- Token expiration configurable (default: 24h)
- Rate limiting: max 5 login attempts per minute

---

## 2. Property Management

### ✅ Functional Requirements
- Hosts can create, edit, and delete property listings
- Listings include title, description, location, price, amenities, availability
- Properties are linked to host accounts

### API Endpoints

| Method | Endpoint                  | Description                     |
|--------|---------------------------|---------------------------------|
| POST   | `/api/properties`         | Create new property listing     |
| GET    | `/api/properties`         | Retrieve all listings           |
| GET    | `/api/properties/:id`     | Retrieve single listing         |
| PUT    | `/api/properties/:id`     | Update listing                  |
| DELETE | `/api/properties/:id`     | Delete listing                  |

### Input Specifications

- `title`: string, required, max 150 chars
- `description`: string, required
- `location`: string, required
- `price`: float, required, min 0
- `amenities`: array of strings
- `availability`: array of date ranges

### Output Specifications

- Property object (id, host_id, title, location, price, timestamps)

### ✅ Validation Rules

- Host must be authenticated
- Price must be positive
- Title and description must not be empty
- Availability must be valid date ranges

### Performance Criteria

- Listings retrieval < 500ms with pagination
- Indexes on `location`, `price`, and `host_id`
- Support for filtering and sorting

---

## 3. Booking System

### ✅ Functional Requirements
- Guests can book properties for specific dates
- Prevent overlapping bookings
- Track booking status: `pending`, `confirmed`, `cancelled`, `completed`
- Allow booking cancellation by guest or host

### API Endpoints

| Method | Endpoint                  | Description                     |
|--------|---------------------------|---------------------------------|
| POST   | `/api/bookings`           | Create new booking              |
| GET    | `/api/bookings`           | Retrieve user bookings          |
| PUT    | `/api/bookings/:id/cancel`| Cancel booking                  |
| GET    | `/api/bookings/:id`       | Get booking details             |

### Input Specifications

- `property_id`: UUID, required
- `guest_id`: UUID, auto from session
- `start_date`: date, required
- `end_date`: date, required
- `total_price`: float, auto-calculated

### Output Specifications

- Booking object (id, property_id, guest_id, status, dates, timestamps)

### ✅ Validation Rules

- Dates must not overlap with existing bookings
- Start date must be before end date
- Only guests can create bookings
- Only involved users can cancel

### Performance Criteria

- Booking creation < 400ms
- Conflict detection via indexed date range queries
- Status updates reflected in real-time

---

## Notes

- All endpoints follow RESTful conventions
- Authentication required for protected routes
- Role-based access enforced via middleware
- Responses use standardized JSON format

---

## Author

Chidiebere Onuoha — Controls & Software Engineer  
Focused on building scalable platforms and inclusive digital tools.

---

## License

This documentation is for educational and planning purposes. Feel free to fork, adapt, and contribute.
