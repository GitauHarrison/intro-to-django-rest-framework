# Django Rest Framework 

This is a [quickstart app](https://www.django-rest-framework.org/tutorial/quickstart/) 
to the django rest framework which quicky creates a simple API to view and edit the users and 
groups in the system.

Start the django app:
```python
(venv)$ python3 manage.py runserver
```

On the terminal, we can use either the `curl` command or the `http` command to test the API.

- Using the `curl` command:
    ```python
    (venv)$ curl -H 'Accept: application/json; indent=4' -u admin:password123 http://127.0.0.1:8000/users/

    # Output
    {
        "count": 2,
        "next": null,
        "previous": null,
        "results": [
            {
                "url": "http://127.0.0.1:8000/users/2/",
                "username": "harry",
                "email": "admin@example.com",
                "groups": []
            },
            {
                "url": "http://127.0.0.1:8000/users/1/",
                "username": "admin",
                "email": "admin@email.com",
                "groups": []
            }
        ]
    }
    ```

- Using `http` command:
    ```python
    # Ensure you have installed httpie (pip3 install httpie)

    (venv)$ http -a admin:password123 http://127.0.0.1:8000/users/

    # Output

    HTTP/1.1 200 OK
    Allow: GET, POST, HEAD, OPTIONS
    Content-Length: 249
    Content-Type: application/json
    Cross-Origin-Opener-Policy: same-origin
    Date: Tue, 20 Dec 2022 13:52:58 GMT
    Referrer-Policy: same-origin
    Server: WSGIServer/0.2 CPython/3.8.10
    Vary: Accept, Cookie
    X-Content-Type-Options: nosniff
    X-Frame-Options: DENY

    {
        "count": 2,
        "next": null,
        "previous": null,
        "results": [
            {
                "email": "admin@example.com",
                "groups": [],
                "url": "http://127.0.0.1:8000/users/2/",
                "username": "harry"
            },
            {
                "email": "admin@email.com",
                "groups": [],
                "url": "http://127.0.0.1:8000/users/1/",
                "username": "admin"
            }
        ]
    }
    ```