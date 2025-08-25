# airbnb-clone-project

## Team Roles

- **Project Manager**  
  Oversees the project’s progress, ensures deadlines are met, manages communication between team members, and aligns the project with business goals.

- **Backend Developer**  
  Responsible for implementing the server-side logic, building APIs, handling authentication, and ensuring scalability and security of the application.

- **Frontend Developer**  
  Develops the user interface, ensures responsive design, and provides a smooth and intuitive user experience across devices.

- **Database Administrator (DBA)**  
  Designs and maintains the database, optimizes queries, manages migrations, and ensures data security and integrity.

- **DevOps Engineer**  
  Sets up CI/CD pipelines, manages cloud deployment, monitors performance, and ensures system reliability and scalability.

- **Quality Assurance (QA) Engineer**  
  Tests new features, finds bugs, and validates that the application meets the functional and non-functional requirements before release.

- **UI/UX Designer**  
  Creates wireframes, mockups, and prototypes, defines style guides, and ensures the product has an engaging and user-friendly design.


## Technology Stack

- **Django**  
  A high-level Python web framework used to build the backend of the application, manage business logic, and provide RESTful/GraphQL APIs.

- **PostgreSQL**  
  A powerful open-source relational database system used to store and manage application data securely and efficiently.

- **GraphQL**  
  A query language for APIs that allows clients to request exactly the data they need, reducing over-fetching and improving performance.

- **Docker**  
  Used to containerize the application and its dependencies, ensuring consistent environments across development, testing, and production.

- **Nginx**  
  A web server and reverse proxy used to serve static files, handle load balancing, and route requests to the application backend.

- **Redis**  
  An in-memory data structure store used for caching and session management to speed up response times.

- **GitHub Actions**  
  Provides CI/CD pipelines to automate testing, building, and deployment of the application.


## Database Design

### Key Entities

- **Users**
  - Fields: `id`, `name`, `email`, `password_hash`, `role` (guest or host), `created_at`
  - Description: Represents both guests and hosts. Hosts can list properties, while guests can book properties and leave reviews.

- **Properties**
  - Fields: `id`, `host_id`, `title`, `description`, `location`, `price_per_night`, `created_at`
  - Description: A property listed by a host. Each property belongs to a user (the host).

- **Bookings**
  - Fields: `id`, `user_id`, `property_id`, `start_date`, `end_date`, `status`
  - Description: A reservation made by a guest for a property. Each booking belongs to one guest (user) and one property.

- **Reviews**
  - Fields: `id`, `user_id`, `property_id`, `rating`, `comment`, `created_at`
  - Description: Guests can leave reviews for properties they have booked. Each review belongs to a user and a property.

- **Payments**
  - Fields: `id`, `booking_id`, `amount`, `payment_method`, `payment_date`, `status`
  - Description: Represents a transaction linked to a booking. Each payment is tied to one booking.

## Feature Breakdown

- **User Management**  
  Allows users to register, log in, and manage their profiles. Supports both roles: hosts (who list properties) and guests (who book properties), with secure authentication and authorization.

- **Property Management**  
  Hosts can create, update, and manage property listings with details such as title, description, location, price, and availability. This enables a wide variety of accommodations to be displayed on the platform.

- **Booking System**  
  Guests can search for available properties, make reservations for specific dates, and track their bookings. The system ensures that bookings are validated to avoid double reservations.

- **Payment Integration**  
  Provides a secure way for guests to pay for their bookings. Handles different payment statuses (e.g., pending, completed, failed) and ensures financial transactions are safely processed.

- **Review & Rating System**  
  Guests can leave reviews and ratings for properties they have stayed at. This helps build trust and transparency on the platform by allowing future guests to make informed decisions.

- **Search & Filtering**  
  Users can search for properties based on location, price range, date availability, and other filters. This improves the user experience by making it easier to find suitable accommodations.

- **Admin Dashboard (Optional Extension)**  
  Administrators can oversee users, properties, and bookings. This ensures proper monitoring, moderation, and management of the platform.

