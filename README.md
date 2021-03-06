# Notes App API

## Technologies

-   Backend: Flask
-   Database: MySql, Workbench

## Installation and setup

1. ```
   //Run the following command in the base directory

   $ pip install -r reqiurements.txt
   ```

    OR

    ```
    //Simply use the env created(Recommended)
     $ source env/bin/activate
    ```

2. ```
    In the models.py file, change the host, user credentials, database name.
   ```

3. ```
    //Run the following command in the base directory

   $ export FLASK_APP=flaskr
   $ export FLASK_ENV=development
   $ flask run
   ```

## Endpoints

1. User account registration:

```
[POST] /app/user

Request Data: {
'username': str,
'password': str
}
Response Data: {
'status': 'account created'
}

```

## Test

To run the endpoints, simply import the postman collection and run it locally.

2. User account login

```
[POST] /app/user/auth

Request Data: {
'username': str,
'password': str
}
Response Data: {
'status': 'success',
'userId': int
}

```

3. List Saved Notes

```
[GET] /app/sites/list/?user={userId}
Request Data: None
Response Data: [List of saved notes]

```

4. Save a new note:

```
[POST] /app/sites?user={userId}
Request Data: {
'note': str,
}
Response Data: {
'status': 'success'
}


```

## Possible errors

The `simple-crypt` module depends on `Crypto`.

`Crypto` module used a function `time.clock()` which is deprecated and is no longer used.

Replacing the function with `time.process_time()` solves the error. Please make changes in the relavant files if error occurs.
