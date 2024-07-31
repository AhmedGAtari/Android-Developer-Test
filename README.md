# Android Developer Test

This repository was created to explain the test and provide you with the necessary resources to complete it.

## Overview
1. Create a simple login page based on the provided design.
2. Apply the provided data validation.
3. Make an API request to the provided endpoint and process the response.

## Start
Create a new Android project and choose either Kotlin or Java.

## View Task
You are required to create a simple login page, which is provided to you in this repository (Login.png + Login-Error.png). Please follow the same design and use the provided assets to complete the test.

The app must support both portrait and landscape modes.

Please note that the Error Drop Down Box has to be animated. Refer to the recorded video in this repository and apply the same animation.

The app must retain any data entered if the user fills in the text fields.

## API Task
Once the user clicks login, a POST HTTP request must be sent with the following body:

```json
{
    "emailAddress": "",
    "password": ""
}
```

It is expected to either get an error response or a success response.

### In Case of Error Response

1. **HTTP Response Status:** 401 (Unauthorized)
2. **Expected Response Body:**

    ```json
    {
        "error": {
            "status": 401,
            "error": "Unauthorized",
            "message": "Invalid email address or password"
        }
    }
    ```

    You must use the `"message"` value and display it in the Error Drop Down Box view.
    
    
### In Case of Success Response

If the API returns a success response, the following is expected:

1. **HTTP Response Status:** 200 (OK)
2. **Expected Response Body:**

    ```json
    {
        "success": {
            "firstName": "Jane",
            "lastName": "Doe",
            "accountStatus": "Active",
            "token": "token"
        }
    }
    ```

    Ensure that you process and handle this response appropriately.


### Optional

To mimic these responses, you can use any tool you prefer or the following online tool: [Beeceptor](https://beeceptor.com).


## Data Task

You are expected to create objects for each request and response, in addition to a User Object that contains the following fields:

- `firstName`
- `lastName`
- `accountStatus`
- `emailAddress`

### Data Storage

Only when you receive a success response, you are expected to store the User data sent by the API. You are free to choose any database or data storage tool.

Please ensure that the password and the token are stored securely. Accessing them should be done through the User Object using a getter for the token and another getter for the password.

### Data Validation

When the user enters the email address and password, data validation must be performed before sending the API request. Use the following regular expressions for validation:

- **Email Address:** `^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$`
- **Password:** `^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[!@#$%^&*()_+={}\[\]|;:'",.<>?/~`]).{8,}$`

If any of the validations fail, an appropriate message should be presented in the Error Drop Down Box view (e.g., "Invalid Email Address").



# Colors Used
```
    {
        White: (red: 255/255, green: 255/255, blue: 255/255, alpha: 1.0)
        Red: (red: 164/255, green: 38/255, blue: 51/255, alpha: 1.0)
    }
```

