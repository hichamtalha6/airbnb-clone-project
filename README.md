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
