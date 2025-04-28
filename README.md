# airbnb-clone-project

The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security. This project enables learners to understand complex architectures, workflows, and collaborative team dynamics while building a scalable web application.

## Technology Stack
1. Python (Django) - For full-stack web dev
2. PostgreSQL - strongly relational DB
3. Docker - containerization
4. Kubernetes - container orchestration
5. Sentry - app monitoring
6. Jenkins - CI/CD automation
7. Github - version control

## Database Design
#### Users
-id (PK)
-name
-email
-password_hash
-user_type (e.g., "host" or "guest")

#### Properties
-id (PK)
-user_id (Foreign key → Users)
-title
-description
-location
-price_per_night

#### Bookings
-id (PK)
-property_id (Foreign key → Properties)
-user_id (Foreign key → Users)
-start_date
-end_date
-total_price

#### Reviews
-id (PK)
-property_id (Foreign key → Properties)
-user_id (Foreign key → Users)
-rating (1-5 stars)
-comment

#### Payments
-id (PK)
-booking_id (Foreign key → Bookings)
-payment_date
-amount
-payment_status (e.g., "pending", "completed", "failed")

#### Relationships:
- A User can be a host (who owns properties) or a guest (who books properties).
- A User can create multiple Properties (host role).
- A User can make multiple Bookings (guest role).
- A Property can have many Bookings.
- A Property can have many Reviews.
- A Booking must be linked to one Property and one User (guest).
- A Review is made by a User for a Property.
- A Payment is linked to a Booking and records the transaction.

## Feature Breakdown
### User Management
Handles user registration, login, and profile management. Supports different user roles (hosts and guests) and ensures secure authentication and authorization.

### Property Management
Enables hosts to do CRUD for property listings. Properties include details like location, description, price per night, and available amenities.

### Booking System
Allows guests to book available properties for specific dates. It manages availability, prevents double-booking, and calculates the total booking price. Also does booking recommendations.

### Review System
Lets guests leave ratings and comments on properties they’ve stayed at. Reviews help future guests make informed decisions and maintain platform quality.

### Payment Integration
Manages secure payment processing for bookings. Tracks payment statuses to ensure hosts get paid and bookings are confirmed only after successful transactions.

### API Security
Implements authentication, authorization, rate-limiting and data validation measures. Protects user data, prevents unauthorized access, and secures transactions.

###  CI/CD Pipeline
Automates the testing and deployment process using tools like Jenkins and Docker. Ensures faster development cycles and reliable production releases.

##  API Security
Protecting the API endpoints from unauthorized access, abuse and overuse. This could come in the form of DDOS attacks, attempts at unauthorized access and excessive pinging. 

### Measures to use:
#### Registration & Token Authentication
API Registration will be integrated for anyone seeking access to the API. Tokens will allow us to manage access using features like token issuance, token expiry and revoking tokens. This will ensure only identified users get access to the system.

### Authorization
Using the API registration, user types (type: api_user) will be checked to ensure only the authorized user gets access to the API.

## Rate limiting
Sentry ensures each endpoint is monitored and rate limiting is enforced depending on IP address and requests per given timeframe. This ensures no one client can abuse or overuse API resources.

## CI/CD Pipeline
CI/CD = Continuous Integration (of new code into existing codebase) / Continuous Deployment (build and release of new code)
A CI/CD pipeline is important to ensure continuous improvements on the application in a reliable way.
### Tools used:

#### Git
Running tests and using Git for VCS are used to ensure there is continuous integration of code using pull requests, while deployment is done by building and pushing code to the application server using tools like npm and go build to build and SSH to push the code.

#### Jenkins
Jenkins is used to automate this process by having Jenkinsfiles with stages. This leads to a faster CI/CD process as jenkins runs the tests, builds the application and deploys all on it's own.


## Team Roles
`Front-End Developer` - Ensure the user interface and user experience are aligned to customer and business goals. Links UI with backend services.
`Back-End Developer` - Ensure data is received, stored & processed in line with business logic, as well as availing the data for linking with the UI in correct formats.
`Software Architect & Product Maneger` - Designs the high-level architecture of the software and manages the implementation process as well the implementors involved. In charge of product and team management.


## Info
As part of ALX Pro-Dev Backend Course.
