
# Dependencies

bcrypt,express,jsonwebtoken,mongoose,multer,stripe

# installation

online movie ticket system requires [Node.js](https://nodejs.org/)  to run.

`types of user -> admin and normal user`

# get stripe key for payment
https://dashboard.stripe.com
register in stripe and get secret key


## Available Scripts

In the project directory, you can run:

### `npm start`


# API 

`1: Login Page:`
Method: POST
URL: 127.0.0.1:3000/users/login

# schema 
{
    "email": string,
    "password": string
}

```````````````````````````````````````````````````````````````````````````````````
```````````````````````````````````````````````````````````````````````````````````

`2: Register Page:`
Method: POST
URL: 127.0.0.1:3000/users/register

# schema: 
{
     "first_name": string,
     "last_name": string,
     "email": string,
     "password": string,
     "mobile": number
}

# Response:
{

        "isAdmin": false,       //need to change this in DataBase "True" if Admin 
}


```````````````````````````````````````````````````````````````````````````````````
```````````````````````````````````````````````````````````````````````````````````

`3: List Users Page:`
Method: GET
URL: 127.0.0.1:3000/users/list-users



```````````````````````````````````````````````````````````````````````````````````
```````````````````````````````````````````````````````````````````````````````````

`3) Add movie Page:`
Method: POST
URL: 127.0.0.1:3000/movies/add


Inside Body:
{
     "movie_name": string,
     "description": string,
     "runtime": number
}


```````````````````````````````````````````````````````````````````````````````````
```````````````````````````````````````````````````````````````````````````````````

`4: Update movie Page:`
Method: PUT
URL: 127.0.0.1:3000/movies/update

Request:
{
Inside Headers:

Key: Authorization
Value: Bearer (token from API 1 for admin user)

Inside Body:
{
     "_id": string,
     "movie_name": string
}
}


```````````````````````````````````````````````````````````````````````````````````
```````````````````````````````````````````````````````````````````````````````````

`API-5: Delete movie Page:`
Method: DELETE
URL: 127.0.0.1:3000/movies/delete

Request:
{
Inside Headers:

Key: Authorization
Value: Bearer (token from API 1 for admin user)

Inside Body:
{
     "_id": string
}
}

```````````````````````````````````````````````````````````````````````````````````
```````````````````````````````````````````````````````````````````````````````````

`API-6: Search movie Page:`
Method: GET
URL: 127.0.0.1:3000/movies/search

```````````````````````````````````````````````````````````````````````````````````
```````````````````````````````````````````````````````````````````````````````````

`API-7: List all movie Page:`
Method: GET
URL: 127.0.0.1:3000/movies/search


```````````````````````````````````````````````````````````````````````````````````
```````````````````````````````````````````````````````````````````````````````````

`API-8: specific movie Page:`
Method: GET
URL: 127.0.0.1:3000/movies/specificMovie

Request:
{
Inside Headers:

Key: Authorization
Value: Bearer (token from API 1 for normal user)

Inside Body:
{
      "_id": string
}
}

```````````````````````````````````````````````````````````````````````````````````
```````````````````````````````````````````````````````````````````````````````````

`API-9: Booking movie Page:`
Method: POST
URL: 127.0.0.1:3000/bookings/input

Request:
{
Inside Headers:

Key: Authorization
Value: Bearer (token from API 1 for normal user)

Inside Body:
{
      "movie_name": string,
      "date": string,
      "time": string,
      "no_of_seat": number
}
}


```````````````````````````````````````````````````````````````````````````````````
```````````````````````````````````````````````````````````````````````````````````

`API-10: Booking history of specific user Page:`
Method: GET
URL: 127.0.0.1:3000/bookings/history


```````````````````````````````````````````````````````````````````````````````````
```````````````````````````````````````````````````````````````````````````````````

`API-11: E-ticket Page:`
Method: GET
URL: 127.0.0.1:3000/bookings/eticket


```````````````````````````````````````````````````````````````````````````````````
```````````````````````````````````````````````````````````````````````````````````