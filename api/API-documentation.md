# URL Shortener API Documentation

# Base URL
All endpoints are relative to the base URL: window.location.hostname // example: localhost:3000

# Authentication
Some endpoints require authentication. To authenticate, you need to include an Authorization header in your requests with a valid JSON Web Token (JWT) token.

Example:

Authorization: Bearer <your_token_here>

To obtain a JWT token, you need to send a POST request to the /auth/login endpoint with your credentials (username and password). The response will include a JWT token that you can use for subsequent authenticated requests.

# Endpoints

# Sign up
Endpoint: /auth/signup
Method: POST
Authentication: Not required
Request Body:
email (string, required): The email of the user
password (string, required): The password of the user

Example Request:

POST /auth/signup
Content-Type: application/json

{
  "username": "sourabhkattimani01@gmai.com",
  "password": "secretpassword"
}

# Login
Endpoint: /auth/login
Method: POST
Authentication: Not required
Request Body:
email (string, required): The email of the user
password (string, required): The password of the user

Example Request:

POST /auth/login
Content-Type: application/json

{
  "username": "sourabhkattimani01@gmail.com",
  "password": "secretpassword"
}

# Create Short URL

Endpoint: /url/create
Method: POST
Authentication: Required
Request Body:
url (string, required): The long URL to shorten
Example Request:

POST /url/create
Authorization: Bearer <your_token_here>
Content-Type: application/json

{
  "url": "https://www.example.com/this-is-a-very-long-url"
}

# Get Dashboard
Endpoint: /url/dashboard
Method: GET
Authentication: Required
Example Request:

GET /url/dashboard
Authorization: Bearer <your_token_here>

# Search URLs
Endpoint: /url/search
Method: GET
Authentication: Required
Example Request:

GET /url/search
Authorization: Bearer <your_token_here>

# Delete URL
Endpoint: /url/delete/{urlId}
Method: DELETE
Authentication: Required
Example Request:

DELETE /url/delete/12345
Authorization: Bearer <your_token_here>

# Redirect to URL
Endpoint: /url/redirect/{shortUrl}
Method: PUT
Authentication: Not required
Example Request:

PUT /url/redirect/abc123


