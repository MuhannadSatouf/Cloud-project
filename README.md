# Cloud-project

# How to use this myCirculationAPI <br>

## Original repository if you want to check commits history

```sh
https://github.com/labeginit/myCirculationAPI
```

## Disclamer: All the methods requiring authentication might return

> {
> "error": "Unauthorized"
> }

## End point _/users_ method GET<br>

**Requires authentication!**

Returns a list of all users<br>

### Response<br>

> [<br>
>
> > {<br>
> > "\_id": "62596177438505704b60b2b2",<br>
> > "email": "email@gmail.com",<br>
> > "firstName": "Name",<br>
> > "lastName": "Surname",<br>
> > "birthDate": "yyyy-MM-dd",<br>
> > "password": "some hashed password",<br>
> > "**v": 0<br>
> > },<br>
> > {<br>
> > "\_id": "62596360a3796f2fb417497b",<br>
> > "email": "...@gmail.com",<br>
> > "firstName": "Name",<br>
> > "lastName": "Surname",<br>
> > "birthDate": "yyyy-MM-dd",<br>
> > "password": "some hashed password",<br>
> > "**v": 0<br>
> > }<br>
> > ]<br>

## End point _/register_ method POST<br>

Creates a user with a unique email address. A hashed version of the password is saved in the DB<br>

### Example of such request<br>

> https://obscure-bayou-38424.herokuapp.com/register + object <br>
> {<br>
> email: "xxxx@email",<br>
> firstName: "firstName",<br>
> lastName: "lastName",<br>
> birthDate: "yyyy-MM-dd",<br>
> password: "password"<br>
> }<br>

### Response<br>

> "62596360a3796f2fb417497b" - the ID of the newly created record<br>

## End point _/stats/[user_id]_ method GET<br>

Returnsan a JSON with two values: the total count of records in the DB and the records count of the logged in user<br>

### Example of such request<br>

> https://obscure-bayou-38424.herokuapp.com/stats/62596360a3796f2fb417497b <br>

### Response<br>

> {<br>

    "totalRecordsCount": 28,<br>
    "userRecordsCount": 8<br>

}<br>

## End point _/login_ method POST<br>

Returns a single user by email address and password (status 200 or a message (status 404). Session stores the user object<br>

### Example of such request<br>

> https://obscure-bayou-38424.herokuapp.com/login + object<br>

> {<br>
> "email": "mymail@gmail.com",<br>
> "password": "password"<br>
> }<br>

## End point _/login_ method GET<br>

**Requires authentication!**

Returns the current user stored in the session<br>

### Example of such request<br>

> https://obscure-bayou-38424.herokuapp.com/login <br>

### Response<br>

> {<br>
> "\_id": "62596177438505704b60b2b2",<br>
> "email": "mymail@gmail.com",<br>
> "firstName": "Name",<br>
> "lastName": "Surname",<br>
> "birthDate": "yyyy-MM-dd",<br>
> }<br>
> OR "Not logged in"<br>

## End point _/login_ method DELETE<br>

**Requires authentication!**

Deletes the current user stored in the session<br>

### Response<br>

> "Logged out"<br>

## End point _/records/[user_id]_ method GET<br>

**Requires authentication!**

Will return all records for a specified user.<br>

### Example of such request<br>

> https://obscure-bayou-38424.herokuapp.com/records/625987150ae68c9cb02e8f1f<br>

### Response<br>

> [<br>
>
> > {<br>
> > "\_id": "6259887a2d5216427152a740",<br>
> > "userID": "625987150ae68c9cb02e8f1f",<br>
> > "systolic": 120,<br>
> > "diastolic": 65,<br>
> > "heartRate": 63,<br>
> > "createdAt": "2022-04-15T15:00:10.611Z",<br>
> > "updatedAt": "2022-04-15T15:00:10.611Z",<br>
> > "**v": 0<br>
> > },<br>
> > ...<br>
> > {<br>
> > "\_id": "6259899b84996afd09cf5ec1",<br>
> > "userID": "625987150ae68c9cb02e8f1f",<br>
> > "systolic": 90,<br>
> > "diastolic": 63,<br>
> > "heartRate": 75,<br>
> > "createdAt": "2022-04-15T15:04:59.858Z",<br>
> > "updatedAt": "2022-04-15T15:04:59.858Z",<br>
> > "**v": 0<br>
> > }<br>
> > ]<br>

## End point _/records/[user_id]_ method POST<br>

**Requires authentication!**

Adds a health status record for a specified user. Returns evaluation of current health status of the user.<br>

### Example of such request<br>

> https://obscure-bayou-38424.herokuapp.com/records/62596360a3796f2fb417497b' + object <br>
> {<br>
> systolic: 87,<br>
> diastolic: 65,<br>
> heartRate: 72<br>
> }<br>

### Response<br>

> {<br>
> "\_id": "6259887a2d5216427152a740",<br>
> "verdict": "You might need to contact a doctor" OR other text<br>
> }<br>

## End point _/records/[user_id]_ method DELETE<br>

**Requires authentication!**

Deletes a health status record for a specified user. Returns the deleted record or nothing.<br>

### Example of such request<br>

> https://obscure-bayou-38424.herokuapp.com/records/62596360a3796f2fb417497b' + object <br>
> {<br>
> "\_id": "6259887a2d5216427152a740"<br>
> }<br>

# react-cloud-frontend

## Original repository if you want to check commits history

```sh
https://github.com/MuhannadSatouf/cloud-project-frontend
```

## Running Locally

```sh
$ npm install
$ npm start

```

## Font-End

```sh
$ Using JavaScript, React framework , JSX, and CSS

```

## Libraries

```sh
$ "@mui/material": "^5.7.0"
$  "axios": "^0.26.1"
$ "bootstrap": "^5.1.3"
$ "cors": "^2.8.5"
$ "rc-slider": "^10.0.0"
$ "react": "^18.0.0"
$ "react-cookie": "^4.1.1"
$ "react-dom": "^18.0.0"
$ "react-router": "^6.3.0"
$ "react-router-dom": "^6.3.0"
$ "react-scripts": "^5.0.1"
```

## Node and NPM versions

```sh
$ "node": "16.13.2"
$ "npm" : "8.6.0"
```

## End-points

```sh
$ Landing page: "https://desolate-stream-78141.herokuapp.com"
$ Login page: "https://desolate-stream-78141.herokuapp.com/login"
$ Register page : "https://desolate-stream-78141.herokuapp.com/register"
$ Home page: "https://desolate-stream-78141.herokuapp.com/home" need to login first

```

## Wrong endpoint return

> {
> "error": "404"
> shows 404 page
> }
