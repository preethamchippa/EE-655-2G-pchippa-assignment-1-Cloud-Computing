# EE-655-2G-pchippa-assignment-1-Cloud-Computing

## Assignment - 2
## Blogging Platform API
A Restful API for a simple blogging platform. This API allows users to create, retrieve, search, and delete blog posts. Built with Node.js and MongoDB, it supports operations on blog posts such as adding new posts, fetching posts by username, searching posts by keywords in titles or content, and deleting posts.

**Features**

- Create blog posts with title, content, and associated username.
- Retrieve all blog posts or filter by username.
- Search for blog posts containing specific keywords in their titles or content.
- Delete all blog posts by a specific username or containing a specific keyword in their content.

**Getting Started**
Prerequisites
Node.js
npm or yarn
MongoDB
Installation

**Install dependencies:**

npm install

**Configure your environment variables:**
Create a .env file in the root directory and specify your MongoDB URI:

MONGODB_URI=your_mongodb_uri

**Start the server:**

npm start

The API server will be running on http://localhost:3000.

**API Endpoints**

Create a New Blog Post
POST /posts

**Creates a new blog post.**

Body Parameters

userName (required): The username of the post creator.
title (required): The title of the blog post.
content (required): The content of the blog post.
Retrieve All Blog Posts

**GET /posts**

Retrieves all blog posts.

Retrieve Blog Posts by Username

**GET /posts/user/:userName**

Retrieves all blog posts by a given username.

Retrieve Blog Posts by Title Keyword

**GET /posts/title/:searchWord**

Retrieves all blog posts that contain a given word in the title.

Retrieve Blog Posts by Content Keyword

**GET /posts/content/:searchWord**

Retrieves all blog posts that contain a given word in the content.

Delete All Posts by Username

**DELETE /posts/user/:userName**

Deletes all blog posts by a given username.

Delete All Posts Containing a Keyword in Content

**DELETE /posts/content/:searchWord**

Deletes all blog posts that contain a certain word in the content.

Get Post Count by Username

**GET /posts/count/:userName**

Returns the number of blogs posted by a given username along with the username.

## Assignment-1
**IoT Device Management API Documentation**

Base URL
http://localhost:3000

1. Device Registration
Endpoint

POST /register

Request Body

deviceId: Unique identifier for the device. (Required)
deviceType: Type of the device. (Required)

Example Request:

{
  "deviceId": "device123",
  "deviceType": "temperature_sensor"
}

Response

Status: 201 Created
Body: Success message if registration is successful.
Error Responses
Status: 400 Bad Request
Body: Error message if deviceId or deviceType is missing or invalid.
Status: 409 Conflict
Body: Error message if the device already exists.

2. Displaying Devices
Endpoint

GET /show

Response

Status: 200 OK
Body: List of registered devices.
Error Responses
Status: 500 Internal Server Error
Body: Error message if there's an issue retrieving the devices.

3. Receiving Device Data
Endpoint

POST /data

Request Body
deviceId: Unique identifier for the device. (Required)
data: Data sent by the device. (Required)

Example Request

{
  "deviceId": "device123",
  "data": "25°C"
}

Response

Status: 200 OK
Body: Success message if data is received successfully.
Error Responses
Status: 400 Bad Request
Body: Error message if deviceId or data is missing or invalid.

4. Sending Commands to Devices
Endpoint

POST /command

Request Body
deviceId: Unique identifier for the device. (Required)
command: Command to be sent to the device. (Required)

Example Request

{
  "deviceId": "device123",
  "command": "turn_on"
}

Response

Status: 200 OK
Body: Success message if command is sent successfully.
Error Responses
Status: 400 Bad Request
Body: Error message if deviceId or command is missing or invalid.
