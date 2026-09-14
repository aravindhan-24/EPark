# EPark

EPark is a Spring Boot web application for renting and listing parking spaces for electric vehicles (EVs). The platform allows users to:

- browse available parking spots
- register and log in
- post parking listings with images, location details, and pricing
- view parking offers from the main listing page

The application uses Java, Spring MVC, Spring Data JPA, MySQL, and JSP views.

## Project overview

This project is designed to help EV owners find nearby parking spaces and help property owners monetize unused parking areas. It includes:

- a landing page for the application
- a user registration form
- a login page
- a parking listing form with image upload
- a page to view all available parking listings
- database persistence for users and listing data

## Tech stack

- Java 8
- Spring Boot 2.5.3
- Spring Web MVC
- Spring Data JPA
- MySQL Connector
- Hibernate Validator
- JSP / JSTL
- Maven
- Tomcat embedded server

## Project structure

- `controller/` - request handling and page navigation
- `model/` - entity classes for users and parking details
- `Repository/` - Spring Data repositories
- `views/` - JSP pages
- `aboutResource/` and `signUpResource/` - frontend assets and static files
- `application.properties` - project configuration
- `pom.xml` - Maven dependencies and build settings

## Prerequisites

Before running the application, make sure you have:

- JDK 8 or later
- Maven 3+
- MySQL Server installed and running
- a MySQL database named `EPark`

## Database configuration

The app is configured in `application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/EPark
spring.datasource.username=root
spring.datasource.password=admin
spring.jpa.hibernate.ddl-auto=update
```

If your MySQL setup differs, update the username, password, and database URL accordingly.

## Running the project

1. Clone the repository.
2. Create the MySQL database named `EPark`.
3. Update database credentials in `application.properties` if required.
4. Run the application with:

```bash
mvn spring-boot:run
```

5. Open the app in a browser:

```text
http://localhost:8080/
```

## Main routes

- `/` - home page
- `/register` - register a new user
- `/login` - login page
- `/view` - view parking listings
- `/profile` - user profile page
- `/addDetails` - submit a new parking listing

## Features

### User registration
Users can create an account with:

- name
- email
- password

### Login
The login flow checks the email and password against the `RegisterUser` table.

### Post parking details
A listing can include:

- plot number
- address
- description
- email
- amount
- image upload

The uploaded image is stored as a Base64-encoded string in the database.

### View listings
The application retrieves all entries from the details repository and displays them in the `View` page.

## Notes

- The project is packaged as a WAR application.
- JSP files are stored under the `views/` directory.
- The database schema is generated automatically with `spring.jpa.hibernate.ddl-auto=update`.
- For production use, you should replace the local database credentials and add better security around authentication.

## License

This project is provided as-is for learning and demonstration purposes.

## Contributing

This is a small academic/project-style application. Contributions can include:

- improving validation and error handling
- adding session-based login flow
- securing endpoints and password storage
- enhancing the UI
- adding search and filtering for parking spaces

