

# Calorie Counter REST API

This is a REST API for tracking calories. It allows users to create an account, log in, and manage their calorie entries. The API supports authentication, implements three roles with different permission levels, and connects to a calories API provider to fetch calorie information if not provided by the user. It also includes user settings for the expected number of calories per day, and calculates a boolean field indicating if the total for the day is below the expected calories. The API returns data in JSON format and provides filtering capabilities and pagination for list endpoints.

## Features

- User registration: Users can create an account by providing a username, password, role, and expected number of calories per day.
- User authentication: All API calls are authenticated using JSON Web Tokens (JWT).
- Role-based permissions: Three roles are implemented - regular user, user manager, and admin - each with different permission levels for CRUD operations on records and users.
- Calorie entry management: Users can create, read, update, and delete their calorie entries. The entries contain a date, time, text description, and number of calories.
- External API integration: If the number of calories is not provided by the user, the API connects to a calories API provider (e.g., Nutritionix) to fetch the calorie information for the entered meal.
- Daily calories tracking: Each entry includes an extra boolean field indicating if the total for the day is less than the expected number of calories per day.
- JSON format: Data is returned in JSON format to enable easy consumption by clients.
- Filtering and pagination: List endpoints support filtering capabilities and pagination to efficiently retrieve data.

## Tech Stack

- Python: Programming language used for API development.
- Flask: Python web framework for building the REST API.
- SQLite: Lightweight database used for storing user and calorie entry data.
- SQLAlchemy: Object-Relational Mapping (ORM) library for interacting with the database.
- Flask-Bcrypt: Library for password hashing and verification.
- JWT: JSON Web Tokens for user authentication and authorization.
- Requests: Library for making HTTP requests to external APIs.
- Pytest: Testing framework for unit and end-to-end (E2E) tests.

## Installation and Setup

1. Clone the repository:

```
git clone https://github.com/CalorieCounter/calorie-tracker-api.git
cd calorie-tracker-api
```

2. Create a virtual environment and activate it:

```
python3 -m venv venv
source venv/bin/activate
```

3. Install the required dependencies:

```
pip install -r requirements.txt
```

4. Run the database migrations:

```
flask db upgrade
```

5. Start the development server:

```
flask run
```

The API will be accessible at `http://localhost:5000`.

## Testing

To run the unit tests and end-to-end (E2E) tests, use the following command:

```
pytest
```

The tests will be executed, and the results will be displayed in the terminal.

## API Documentation

The API documentation and endpoint details can be found in the [API Documentation](api-docs.md) file.

## Deployment

To deploy the API to a production environment, additional steps are required. Some considerations include:

- Securing sensitive information (e.g., secret keys, database credentials).
- Configuring a production-grade web server (e.g., Nginx) and deploying the API using a WSGI server (e.g., Gunicorn).
- Setting up a production database (e.g., PostgreSQL) for storing user and calorie entry data.
- Enabling HTTPS for secure communication.
- Scaling the API to
