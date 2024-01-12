# Web - HTTP Tools Golang Project

## Overview
This Go-based project provides a suite of tools to streamline handling HTTP requests and responses. It's designed to simplify the process of decoding JSON from requests and encoding responses into JSON or plain text. Additionally, it includes a standardized approach to error handling in HTTP responses.

## Features
1. **JSON Request Parsing**: Easily decode JSON from incoming HTTP requests into Go structs.
2. **JSON Response Handling**: Send JSON-encoded responses with appropriate HTTP status codes.
3. **Text Response Handling**: Send plain text responses with status codes.
4. **Standardized Error Responses**: A uniform method for sending JSON formatted error messages.

## Usage

### JSON Request Parsing
Function: `JSON(r *http.Request, ptr any) (err error)`
- Decodes JSON from an HTTP request body into the provided struct pointer.
- Checks for 'application/json' content type.
- Returns custom errors for content type mismatch or JSON decoding issues.

### JSON Response Handling
Function: `JSON(w http.ResponseWriter, code int, body any)`
- Encodes the provided body as JSON and writes to the HTTP response.
- Sets appropriate content type and status code.
- Handles marshaling errors by sending an internal server error.

### Text Response Handling
Function: `Text(w http.ResponseWriter, code int, body string)`
- Sends a plain text response.
- Sets 'text/plain' content type and appropriate status code.

### Standardized Error Responses
Functions: `Error(w http.ResponseWriter, statusCode int, message string)` and `Errorf(w http.ResponseWriter, statusCode int, format string, args ...interface{})`
- Send standardized error messages in JSON format.
- Allows for custom status codes and error messages.
- Automatically defaults to internal server error for invalid status codes.
- `Errorf` allows formatted error messages.

## Installation
To use this project, simply import the package into your Go project. Ensure you have Go installed and your GOPATH is set.

```bash
go get -u github.com/bootcamp-go/web
```

## License
This project is licensed under the MIT License - see the LICENSE file for details.