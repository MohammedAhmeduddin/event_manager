# Event Manager Company: Software QA Analyst/Developer Onboarding Assignment

Welcome to the Event Manager Company! As a newly hired Software QA Analyst/Developer and a student in software engineering, you are embarking on an exciting journey to contribute to our project aimed at developing a secure, robust REST API that supports JWT token-based OAuth2 authentication. This API serves as the backbone of our user management system and will eventually expand to include features for event management and registration.

## Issue resolved:

1. **Min password length as 8 char**: Enhanced password validation by adding a password_min_length function to ensure that user passwords comply with security best practices. This function enforces a minimum password length of 8 characters, preventing the use of overly short and insecure passwords. This improvement strengthens user account security by aligning with modern password policy standards.

link to the issue: https://github.com/MohammedAhmeduddin/event_manager/tree/1-min-password-length-as-8-char

2. **remove duplicate login endpoint**: Simplified the user route by removing the redundant login endpoint, ensuring there is only a single login route. This change reduces redundancy, improves maintainability, and prevents potential inconsistencies in login logic.

link to the issue: https://github.com/MohammedAhmeduddin/event_manager/tree/5-remove-duplicate-logic-endpoint

3. **exceptions logs are missing**: Addressed the absence of exception logs in user routes by integrating logging functionality. This ensures that all exceptions are captured and logged, improving traceability, debugging, and monitoring of user-related operations.

link to the issue: https://github.com/MohammedAhmeduddin/event_manager/tree/7-exceptions-logs-are-missing

4. **Refactored jwt Service**: The code was refactored to improve **readability**, **functionality**, and **maintainability**. Detailed **docstrings** were added for better documentation. The `decode_token` function now includes error handling to safely manage invalid tokens. Logic was simplified for clarity, and explicit algorithm specifications enhance security. These changes make the code more robust, user-friendly, and easier to maintain or extend.

link to the issue: https://github.com/MohammedAhmeduddin/event_manager/tree/9-refactored-jwt-service


5. **Added logging Functionality in email service**: The refactored code enhances the original by incorporating detailed logging and robust error handling to improve monitoring and debugging. Logging is added at key stages, such as service initialization, email template rendering, and sending, providing visibility into operations. It logs specific details like email type and recipient, making it easier to track actions and diagnose issues. Error handling is strengthened with `try-except` blocks to catch and log failures during template rendering or email sending, ensuring clear error messages with contextual information. These changes make the service more reliable, maintainable, and transparent for developers.

link to the issue: https://github.com/MohammedAhmeduddin/event_manager/tree/12-logging-functionality-in-email_service

6. **Min password length as 8 char**: The refactored code adds **password validation** to enforce strong security requirements, ensuring passwords contain uppercase, lowercase, special characters, and numbers. It also includes detailed logging for monitoring key operations and robust error handling to log and manage failures during email rendering or sending. These updates enhance security, reliability, and maintainability.

link to the issue: https://github.com/MohammedAhmeduddin/event_manager/tree/14-password-complex-requirements-such-as-upper-case-lowercase-special-char-and-one-number-for-password


7. **Nickname Mismatch in User Creation**: Resolved Nickname Mismatch in User Creation: Fixed an issue where provided nicknames were overwritten during user creation. Ensured that valid and unique nicknames are used directly, while generating new unique nicknames only when required. Improved logging for better visibility of nickname conflicts.

link to the issue: https://github.com/MohammedAhmeduddin/event_manager/tree/17-nickname-mismatch-in-user-creation

Docker Image and Container Screenshot:
![alt text](<Screenshot 2024-12-06 at 1.25.58 AM.png>)
![alt text](<Screenshot 2024-12-06 at 1.26.25 AM.png>)

## Setup and Preliminary Steps

1. **Fork the Project Repository**: Fork the [project repository](https://github.com/kaw393939/event_manager) to your own GitHub account. This creates a copy of the repository under your account, allowing you to work on the project independently.

2. **Clone the Forked Repository**: Clone the forked repository to your local machine using the `git clone` command. This creates a local copy of the repository on your computer, enabling you to make changes and run the project locally.

3. **Verify the Project Setup**: Follow the steps in the instructor video to set up the project using [Docker](https://www.docker.com/). Docker allows you to package the application with all its dependencies into a standardized unit called a container. Verify that you can access the API documentation at `http://localhost/docs` and the database using [PGAdmin](https://www.pgadmin.org/) at `http://localhost:5050`.

## Testing and Database Management

1. **Explore the API**: Use the Swagger UI at `http://localhost/docs` to familiarize yourself with the API endpoints, request/response formats, and authentication mechanisms. Swagger UI provides an interactive interface to explore and test the API endpoints.

2. **Run Tests**: Execute the provided test suite using pytest, a popular testing framework for Python. Running tests ensures that the existing functionality of the API is working as expected. Note that running tests will drop the database tables, so you may need to manually drop the Alembic version table using PGAdmin and re-run migrations to ensure a clean state.

3. **Increase Test Coverage**: To enhance the reliability of the API, aim to increase the project's test coverage to 90%. Write additional tests for various scenarios and edge cases to ensure that the API handles different situations correctly.

## Collaborative Development Using Git

1. **Enable Issue Tracking**: Enable GitHub issues in your repository settings. [GitHub Issues](https://guides.github.com/features/issues/) is a powerful tool for tracking bugs, enhancements, and other tasks related to the project. It allows you to create, assign, and prioritize issues, facilitating effective collaboration among team members.

2. **Create Branches**: For each issue or task you work on, create a new branch with a descriptive name using the `git checkout -b` command. Branching allows you to work on different features or fixes independently without affecting the main codebase. It enables parallel development and helps maintain a stable main branch.

3. **Pull Requests and Code Reviews**: When you have completed work on an issue, create a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) to merge your changes into the main branch. Pull requests provide an opportunity for code review, where your team members can examine your changes, provide feedback, and suggest improvements. Code reviews help maintain code quality, catch potential issues, and promote knowledge sharing among the team.

## Resources and Documentation

- **Instructor Videos and Important Links**:
 - [Introduction to REST API with Postgres](https://youtu.be/dgMCSND2FQw) - This video provides an overview of the REST API you'll be working with, including its structure, endpoints, and interaction with the PostgreSQL database.
 - [Assignment Instructions](https://youtu.be/TFblm7QrF6o) - Detailed instructions on your tasks, guiding you through the assignment step by step.
 - [Git Command Reference I created and some explanation for collaboration with git](git.md)
 - [Docker Commands and Running The Tests in the Application](docker.md)
 - Look at the code comments:
    - [Test Configuration and Fixtures](tests/conftest.py)
    - [API User Routes](app/routers/user_routes.py)
    - [API Oauth Routes - Connection to HTTP](app/routers/oauth.py)
    - [User Service - Business Logic - This implements whats called the service repository pattern](app/services/user_service.py)
    - [User Schema - Pydantic models](app/schemas/user_schemas.py)
    - [User Model - SQl Alchemy Model ](app/models/user_model.py)
    - [Alembic Migration - this is what runs to create the tables when you do alembic upgrade head](alembic/versions/628adcb2d60e_initial_migration.py)
    - See the tests folder for all the tests

 - API Documentation: `http://localhost/docs` - The Swagger UI documentation for the API, providing information on endpoints, request/response formats, and authentication.
 - Database Management: `http://localhost:5050` - The PGAdmin interface for managing the PostgreSQL database, allowing you to view and manipulate the database tables.

- **Code Documentation**:
 The project codebase includes docstrings and comments explaining various concepts and functionalities. Take the time to read through the code and understand how different components work together. Pay attention to the structure of the code, the naming conventions used, and the purpose of each function or class. Understanding the existing codebase will help you write code that is consistent and integrates well with the project.

- **Additional Resources**:
 - [SQLAlchemy Library](https://www.sqlalchemy.org/) - SQLAlchemy is a powerful SQL toolkit and Object-Relational Mapping (ORM) library for Python. It provides a set of tools for interacting with databases, including query building, database schema management, and data serialization. Familiarize yourself with SQLAlchemy's documentation to understand how it is used in the project for database operations.
 - [Pydantic Documentation](https://docs.pydantic.dev/latest/) - Pydantic is a data validation and settings management library for Python. It allows you to define data models with type annotations and provides automatic validation, serialization, and deserialization. Consult the Pydantic documentation to understand how it is used in the project for request/response validation and serialization.
 - [FastAPI Framework](https://fastapi.tiangolo.com/) - FastAPI is a modern, fast (high-performance) Python web framework for building APIs. It leverages Python's type hints and provides automatic API documentation, request/response validation, and easy integration with other libraries. Explore the FastAPI documentation to gain a deeper understanding of its features and how it is used in the project.
 - [Alembic Documentation](https://alembic.sqlalchemy.org/en/latest/index.html) - Alembic is a lightweight database migration tool for usage with SQLAlchemy. It allows you to define and manage database schema changes over time, ensuring that the database structure remains consistent across different environments. Refer to the Alembic documentation to learn how to create and apply database migrations in the project.

These resources will provide you with a solid foundation to understand the tools, technologies, and concepts used in the project. Don't hesitate to explore them further and consult the documentation whenever you encounter challenges or need clarification.

### Evaluation

This assignment provided a substantial opportunity to enhance technical expertise in secure software development and system reliability. Implementing features such as enforcing password complexity requirements (e.g., minimum length, special characters, and case sensitivity) demonstrated the importance of adhering to security best practices in user authentication. Refactoring the JWT service to include structured error handling and explicit algorithm specifications improved the system's robustness and security. Addressing issues like duplicate login routes and nickname mismatches in user creation emphasized the value of database integrity and efficient query design to ensure consistency and scalability in multi-user environments.

The integration of detailed logging across various services, including the user routes and email services, underscored the importance of observability in modern applications. By adding logging at critical execution points and during exception handling, the system now offers better traceability and simplifies debugging processes. Refactoring and modularizing these components reinforced the importance of maintainable and extensible code, which is critical for large, collaborative codebases. Additionally, working with unique constraints in the database, especially for nicknames, highlighted the necessity of validating inputs dynamically to avoid runtime conflicts.

This experience also strengthened understanding of collaborative development workflows, including issue tracking, branching, and version control best practices. By isolating changes for each task and maintaining comprehensive documentation, the project achieved consistency and scalability while adhering to software development standards. Ultimately, this assignment provided hands-on experience in designing secure, maintainable, and reliable systems while addressing practical challenges in real-world development scenarios.