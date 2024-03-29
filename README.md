# Hospital Review Website
![project screenshot](https://user-images.githubusercontent.com/48658337/125121265-824acd80-e0a8-11eb-8064-9f4943411493.png)
[Demo Link](https://justcare.herokuapp.com/landing.html)
## Description
  Allows users to find nearby hospitals and to read and post reviews. It uses an Express backend to talk to Firebase and uses Bootstrap for frontend styling. This project was made at HealthHacks 2019 by Alex Ruiz, Alex Peng, Eric Pedley, and Andrew Vuong.

# Justcare server
Welcome. This is a guide to using the server's API endpoints.

## Setup
For local development, you can host a local server by running the following in
the `backend/` directory.
```js
npm i
npm start

...

// The server is now running on localhost:3000.
```

## `localhost:3000/hospital-list`
Accepts POST request with following data in JSON format:
```js
{
  "lat": "...",
  "long": "..."
}
// OR with zipcode
{
  "zip": "..."
}
```
Returns JSON data in following format:
```js
[
  {
    "id": "0",
    "name": "...",
    "address": "...",
    "proximity": "...", //in miles
    "lat": "...",
    "long": "...",
    "rating": {
      // all out of 5 stars
      "Cultural Sensitivity": "...",
      "Hospitality": "...",
      "Quality of Care": "..."
    }
  },
  ...
]
```

## `localhost:3000/hospital-info`
Accepts POST request with following data in JSON format:
```js
{
  "id": "..." //ID of the hospital
}
```
Returns JSON data in following format:
```js
{
  name: "",
  address: "",
  lat: "",
  long: "",
  website: "",
  reviews: [
    {
  		"id": "me@example.com",
  		"name": "Jane Doe",
      "rating": {
        // The following are all numbers from 1 to 5
        "Cultural Sensitivity": "...",
        "Hospitality": "...",
        "Quality of Care": "..."
      },
  		"comment": "..."
    },
    ...
  ]
}
```
