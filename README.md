# TypeScript CRUD API

Simple CRUD API using Express, Sequelize, and MySQL.

## Setup

1. Install dependencies:
   ```bash
   npm install
   ```
2. Start MySQL (XAMPP or similar).
3. Update `config.json` if needed.

## Run

```bash
npm run start:dev
```

Server runs at:

```text
http://localhost:4000
```

## Endpoints

- `POST /users` — create user
- `GET /users` — list users
- `GET /users/1` — get user 1
- `PUT /users/1` — update user 1
- `DELETE /users/1` — delete user 1

## Example request body

```json
{
  "title": "Mr",
  "firstName": "Jane",
  "lastName": "Smith",
  "email": "jane@example.com",
  "password": "secret123",
  "confirmPassword": "secret123",
  "role": "User"
}
```

## Quick PowerShell tests

```powershell
Invoke-RestMethod -Uri "http://localhost:4000/users"
```

```powershell
Invoke-RestMethod -Method Post -Uri "http://localhost:4000/users" -ContentType "application/json" -Body '{ "title":"Mr","firstName":"Jane","lastName":"Smith","email":"jane@example.com","password":"secret123","confirmPassword":"secret123","role":"User" }'
```

```powershell
Invoke-RestMethod -Method Put -Uri "http://localhost:4000/users/1" -ContentType "application/json" -Body '{ "firstName":"Janet","password":"newsecret456","confirmPassword":"newsecret456" }'
```

```powershell
Invoke-RestMethod -Method Delete -Uri "http://localhost:4000/users/1"
```

## Validation test

Send an incomplete `POST /users` body, for example:

```json
{ "firstName": "Bob" }
```

You should get a `400` response with a validation error message.
