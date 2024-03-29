---
title: REST API Calls
description: Types of REST API calls with examples.
date: 2023-04-23
cover: restapi.png
tags:
  - api
---

1. **GET Request:**
   - Purpose: GET requests are used to retrieve data from a server. They are the most common type of API call and are typically used when you want to fetch information from a server without modifying it.
   - Example: Retrieving weather data from a weather API.In this example, a GET request is made to the WeatherAPI to retrieve current weather data for New York.
     ```jsx
     fetch(
       "https://api.weatherapi.com/v1/current.json?key=YOUR_API_KEY&q=New York"
     )
       .then((response) => response.json())
       .then((data) => console.log(data));
     ```
2. **POST Request:**
   - Purpose: POST requests are used to send data to a server to create or update a resource. They are commonly used when submitting form data or sending data to a server to be processed.
   - Example: Creating a new user account.In this example, a POST request is made to an API endpoint to create a new user account with the specified username, email, and password.
     ```jsx
     fetch("https://api.example.com/users", {
       method: "POST",
       headers: {
         "Content-Type": "application/json",
       },
       body: JSON.stringify({
         username: "example_user",
         email: "example@example.com",
         password: "password123",
       }),
     })
       .then((response) => response.json())
       .then((data) => console.log(data));
     ```
3. **PUT Request:**
   - Purpose: PUT requests are used to update existing data on the server. They replace the entire resource with the new data provided in the request.
   - Example: Updating a user's profile information.In this example, a PUT request is made to update the user with the ID 123 with the new username and email provided in the request body.
     ```jsx
     fetch("https://api.example.com/users/123", {
       method: "PUT",
       headers: {
         "Content-Type": "application/json",
       },
       body: JSON.stringify({
         username: "new_username",
         email: "new_email@example.com",
       }),
     })
       .then((response) => response.json())
       .then((data) => console.log(data));
     ```
4. **DELETE Request:**
   - Purpose: DELETE requests are used to delete data from the server.
   - Example: Deleting a user account.In this example, a DELETE request is made to delete the user with the ID 123 from the server.
     ```jsx
     fetch("https://api.example.com/users/123", {
       method: "DELETE",
     }).then((response) => {
       if (response.ok) {
         console.log("User deleted successfully");
       } else {
         console.error("Failed to delete user");
       }
     });
     ```
5. **PATCH:** The PATCH method is similar to PUT but is used to partially update a resource with a set of changes. It allows for making modifications to specific fields of a resource without having to send the entire updated resource.

   Example: Updating only the email address of a user in a database.

   ```bash
   bashCopy code
   PATCH /users/{id}
   ```

6. **OPTIONS:** The OPTIONS method is used to request information about the communication options available for a given resource. It can be used to determine the supported HTTP methods, headers, or other capabilities of a server.

   Example: Checking which HTTP methods are allowed for a particular resource.

   ```bash
   OPTIONS /users
   ```

7. **HEAD:** The HEAD method is similar to the GET method, but it retrieves only the headers of a response without the body content. It is often used to check the status or metadata of a resource without actually retrieving the resource itself.

   Example: Checking the metadata of a file without downloading the file content.

   ```bash
   HEAD /files/{filename}
   ```
