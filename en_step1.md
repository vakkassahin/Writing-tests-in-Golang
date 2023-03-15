## Writing Tests in Golang

You have a simple function in your Golang codebase that takes in two integers and returns their sum. You want to write unit tests for this function to ensure that it is working correctly.
You can create a new file called function_test.go in the same directory as your function and write a test function that uses the Golang testing package to test your function. Here's an example:
Let's install the Go package. `apk add go`

Next, let's create a new Go page. `vim goroutine.go`

After creating a new page, let's add the following code to the command screen.

package main

import (
"testing"
)

func TestSum(t \*testing.T) {
result := sum(2, 3)
expected := 5
if result != expected {
t.Errorf("Expected %d but got %d", expected, result)
}
}

In this example, we're testing the sum function and verifying that it returns the correct value for two inputs.
