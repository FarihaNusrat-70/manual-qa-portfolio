# API Testing using Postman

## Overview
This project demonstrates basic API testing practice using Postman.
I tested public APIs by sending GET and POST requests and validated responses.

## Tool Used
- Postman

## API Tested
- https://jsonplaceholder.typicode.com/posts

## Test Scenarios

### GET Request
- Verify status code is 200
- Verify response is in JSON format
- Verify response body is not empty

### POST Request
- Verify status code is 201
- Verify response contains id

## DELETE Request Testing

### Endpoint
DELETE {{base_url}}/posts/1

### Scenario
Verify that an existing post can be deleted successfully.

### Observation
Initially, a 500 Internal Server Error was returned because a non-JSON body was sent with the DELETE request.

### Root Cause
DELETE requests generally do not require a request body. Sending plain text instead of valid JSON caused a parsing error on the server.

### Fix
Removed the request body and resent the DELETE request.

### Result
API responded successfully after correcting the request.
