## Writing integration tests for an HTTP server

In this scenario, you have an HTTP server written in Golang that serves a REST API. You want to write integration tests to verify that the API is working correctly.

You can use the Golang net/http/httptest package to write integration tests for your HTTP server. Here's an example:

package main

import (
"net/http"
"net/http/httptest"
"testing"
)

func TestGetUser(t \*testing.T) {
req, err := http.NewRequest("GET", "/users/1", nil)
if err != nil {
t.Fatal(err)
}

    rr := httptest.NewRecorder()
    handler := http.HandlerFunc(GetUserHandler)

    handler.ServeHTTP(rr, req)

    if rr.Code != http.StatusOK {
        t.Errorf("Expected status code %d but got %d", http.StatusOK, rr.Code)
    }

    // Verify response body
    expected := `{"id":1,"name":"John Doe"}`
    if rr.Body.String() != expected {
        t.Errorf("Expected response body %s but got %s", expected, rr.Body.String())
    }

}

In this example, we're testing a hypothetical GetUser API endpoint and verifying that it returns the correct status code and response body for a given input.
