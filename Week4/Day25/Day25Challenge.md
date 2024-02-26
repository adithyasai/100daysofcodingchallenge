

# Day 25: Async/Await, Fetch API for AJAX, and Error Handling in Asynchronous Code

## Async/Await

Async/Await is a modern syntax for handling asynchronous operations in JavaScript. It provides a more concise and readable way to write asynchronous code, making it resemble synchronous code.
````markdown
### Using Async/Await with Functions

```javascript
// Async/Await example
async function fetchData() {
  try {
    let response = await fetch("https://api.example.com/data");
    if (!response.ok) {
      throw new Error("Network response was not ok");
    }
    let data = await response.json();
    console.log("Data from API:", data);
  } catch (error) {
    console.error("Error fetching data:", error);
  }
}

// Call the async function
fetchData();
```
````

The `async` keyword is used to define a function as asynchronous. The `await` keyword is used inside the function to wait for a Promise to resolve.

## Fetch API for AJAX

The Fetch API is a modern and more powerful alternative to the traditional XMLHttpRequest. It provides a simple and consistent interface for making HTTP requests.

```javascript
// Fetch API example
fetch("https://api.example.com/data")
  .then((response) => {
    if (!response.ok) {
      throw new Error("Network response was not ok");
    }
    return response.json();
  })
  .then((data) => {
    console.log("Data from API:", data);
  })
  .catch((error) => {
    console.error("Error fetching data:", error);
  });
```

The Fetch API returns a Promise, making it easy to chain `.then()` and `.catch()` to handle success and error scenarios.

## Error Handling in Asynchronous Code

Handling errors in asynchronous code is crucial for providing a smooth user experience and diagnosing issues during development.

### Try/Catch with Async/Await

```javascript
// Async/Await with try/catch for error handling
async function fetchData() {
  try {
    let response = await fetch("https://api.example.com/data");
    if (!response.ok) {
      throw new Error("Network response was not ok");
    }
    let data = await response.json();
    console.log("Data from API:", data);
  } catch (error) {
    console.error("Error fetching data:", error);
  }
}
```

Using `try/catch` with Async/Await allows you to gracefully handle errors within asynchronous functions.

## Real-Life Example: Uploading File with Fetch API

```javascript
// Uploading a file using Fetch API
const fileInput = document.getElementById("fileInput");
const uploadButton = document.getElementById("uploadButton");

uploadButton.addEventListener("click", async () => {
  try {
    const file = fileInput.files[0];
    const formData = new FormData();
    formData.append("file", file);

    const response = await fetch("https://api.example.com/upload", {
      method: "POST",
      body: formData,
    });

    if (!response.ok) {
      throw new Error("File upload failed");
    }

    const result = await response.json();
    console.log("Upload result:", result);
  } catch (error) {
    console.error("Error uploading file:", error);
  }
});
```

This example demonstrates using the Fetch API to upload a file asynchronously and handle potential errors during the process.

## Assignment: Create a Weather App

Build a weather app that fetches real-time weather data using a public API. Use Async/Await, Fetch API, and implement error handling to display meaningful messages in case of network issues or API errors.

**Requirements:**

1. Utilize the [OpenWeatherMap API](https://openweathermap.org/api) or any other weather API.
2. Implement an input for users to enter the city.
3. Display real-time weather information, including temperature, weather conditions, and other relevant details.
4. Handle errors gracefully, providing user-friendly messages.

This assignment will enhance your skills in working with asynchronous code, APIs, and error handling.

## LinkedIn Post for Achievement

"Day 25 of my coding journey, and I'm conquering Async/Await, mastering the Fetch API for AJAX, and ensuring smooth error handling in asynchronous code! ⚡️ Building a weather app with real-time data fetching adds a practical touch to the learning. 🌦️ #Day25 #100DaysOfCoding #AsyncAwait #FetchAPI #WebDevProject #CodeWithAadi

**Follow us:**

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)

```

Feel free to customize and adapt this content as needed for your context!
```
