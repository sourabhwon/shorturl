URL Shortener API Documentation
Base URL
All endpoints are relative to the base URL: https://example.com/api/v1

Authentication
Some endpoints require authentication. To authenticate, you need to include an Authorization header in your requests with a valid JSON Web Token (JWT) token.

Example:

makefile
Copy code
Authorization: Bearer <your_token_here>
To obtain a JWT token, you need to send a POST request to the /auth/login endpoint with your credentials (username and password). The response will include a JWT token that you can use for subsequent authenticated requests.

Endpoints
Sign up
Endpoint: /auth/signup
Method: POST
Authentication: Not required
Request Body:
username (string, required): The username of the user
password (string, required): The password of the user
Example Request:

bash
Copy code
POST /auth/signup
Content-Type: application/json

{
  "username": "john_doe",
  "password": "secretpassword"
}
Login
Endpoint: /auth/login
Method: POST
Authentication: Not required
Request Body:
username (string, required): The username of the user
password (string, required): The password of the user
Example Request:

bash
Copy code
POST /auth/login
Content-Type: application/json

{
  "username": "john_doe",
  "password": "secretpassword"
}
Quick Create URL
Endpoint: /url/quick_create
Method: POST
Authentication: Not required
Request Body:
url (string, required): The long URL to shorten
Example Request:

bash
Copy code
POST /url/quick_create
Content-Type: application/json

{
  "url": "https://www.example.com/this-is-a-very-long-url"
}
Create Short URL
Endpoint: /url/create
Method: POST
Authentication: Required
Request Body:
url (string, required): The long URL to shorten
Example Request:

bash
Copy code
POST /url/create
Authorization: Bearer <your_token_here>
Content-Type: application/json

{
  "url": "https://www.example.com/this-is-a-very-long-url"
}
Get Dashboard
Endpoint: /url/dashboard
Method: GET
Authentication: Required
Example Request:

sql
Copy code
GET /url/dashboard
Authorization: Bearer <your_token_here>
Search URLs
Endpoint: /url/search
Method: GET
Authentication: Required
Example Request:

sql
Copy code
GET /url/search
Authorization: Bearer <your_token_here>
Delete URL
Endpoint: /url/delete/{urlId}
Method: DELETE
Authentication: Required
Example Request:

sql
Copy code
DELETE /url/delete/12345
Authorization: Bearer <your_token_here>
Redirect to URL
Endpoint: /url/redirect/{shortUrl}
Method: PUT
Authentication: Not required
Example Request:

bash
Copy code
PUT /url/redirect/abc123
That's the API documentation for the provided code. Make sure to replace <your_token_here> with a valid JWT token obtained through the login endpoint
