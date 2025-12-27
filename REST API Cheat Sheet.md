## ${\color{red}REST \ API \ Cheat \ Sheet}$

**REST (Representational State Transfer)** is an architectural style for building APIs using HTTP, stateless communication, and resource-based URLs.

**API (Application Programming Interface)** is a set of rules and definitions that allows different software applications to communicate with each other.

An API defines:
- **What requests can be made**
- **How requests should be structured**
- **What data is returned**
- **How systems interact without exposing internal logic**

---

## Core Principles
- Client–Server separation
- Stateless requests
- Cacheable responses
- Uniform interface
- Layered system

---

## HTTP Methods
| Method | Purpose | Example |
|------|--------|--------|
| GET | Retrieve resource | `/users` |
| POST | Create resource | `/users` |
| PUT | Replace resource | `/users/1` |
| PATCH | Partially update | `/users/1` |
| DELETE | Remove resource | `/users/1` |
| HEAD | Headers only | `/users` |
| OPTIONS | Allowed methods | `/users` |

---

## Resource Naming Best Practices
- Use **nouns**, not verbs  
- Use **plural** names  
- Use hierarchical structure  

**Examples**
- `/users`
- `/users/1/orders`

---

## HTTP Status Codes
| Code | Meaning |
|----|--------|
| 200 | OK |
| 201 | Created |
| 204 | No Content |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 409 | Conflict |
| 422 | Validation Error |
| 500 | Internal Server Error |

---

<br>

## Request Example
```http
POST /users HTTP/1.1
Host: api.example.com
Authorization: Bearer TOKEN
Content-Type: application/json

{
  "name": "John",
  "email": "john@example.com"
}
````
<br>

## Response Example

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 1,
  "name": "John",
  "email": "john@example.com"
}

```
<br>

## Error Response Example

```http
{
  "error": "Validation failed",
  "details": {
    "email": "Invalid email address"
  }
}

```
<br>

## Idempotency

Idempotent: GET, PUT, DELETE

Non-idempotent: POST

<br>

## Common Tools

Postman

curl

Insomnia

Swagger / OpenAPI

HTTPie

<br>

## Best Practices

Use proper HTTP status codes

Validate input

Return consistent JSON

Paginate large responses

Secure APIs with HTTPS

Document APIs using OpenAPI
