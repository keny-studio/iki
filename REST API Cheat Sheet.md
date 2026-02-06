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

###  ⚠️ POST to fetch data

You can use POST to fetch data - but it’s mainly justified when there’s a clear reason (complex input, sensitive data, or processing semantics).

Reasons developers use POST for reads:

1. Hiding sensitive parameters:
Data in the body (POST) isn’t in URLs, so it doesn’t appear in logs or browser history (though HTTPS still encrypts both GET URLs and POST bodies in transit).

2. Complex or large payloads:
GET URLs have length limits; when you need rich JSON queries (filters, sorts, etc.), POST is easier.

3. Non-idempotent “reads”:
If the server does extra processing (e.g., analytics) when returning data, treating it as an action via POST can align better with its semantics.

4. Legacy or tooling constraints:
Some older systems or tooling only support POST bodies, so APIs use POST for everything.

#### Trade-offs to consider:

- Breaks standard REST expectations: Clients and tools expect GET for reads, so using POST can confuse developers.

- No automatic caching: GET responses are cacheable by default; POST responses generally are not.

- Less shareable URLs: A POST body can’t be bookmarked or shared like a GET URL.

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
