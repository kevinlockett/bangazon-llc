# Registering with the API

## Starting the Server in Debug Mode

Use the `Shift+Alt+D` keyboard shortcut to start your new API server in debug mode. When you do, you will see a new terminal window appear at the bottom of VS Code that looks like this once the API is started.

<img src="./images/hr-server-debug-startup.png" alt="Image of API running in debug mode in Visual Studio Code" width="800px" />

## Testing with API Client

Now you can test that the `/register` route works correctly.

1. Open your API client.
2. Create a new request.
3. Change method to POST.
4. Enter in `http://localhost:8000/register` for the URL.
5. Click the _Body_ tab under the URL.
6. Paste JSON like the following into the body. Change the values to be you, or even something silly. Doesn't really matter.
    ```json
    {
        "email": "name@domain.com",
        "first_name": "MyFirstName",
        "last_name": "MyLastName",
        "password": "django",
        "address": "404 Unknown Route",
        "account_type": "customer"
    }
    ```
7. Click the _Send_ button.
8. You should get a response that has the Django authorization token that looks like this. Yours will be different.
    ```json
    {
        "token": "382676acef1f23f321d4821c91cc4e66"
    }
    ````

> This token is unique for every user, and is used by Django to determine who the user is.

<img src="./images/honey-rae-registration-thunder-client.gif" alt="Animaation of testing registration API route with Thunder Client" width="800px" />
