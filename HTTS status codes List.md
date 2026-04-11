## $${\color{red}HTTP \ Status \ Codes \ List}$$

### 🔵 1xx — Informational (Rare in everyday dev)

**Used during request lifecycle, mostly low-level**

* **100 Continue**
  Client can continue sending body (used with large uploads)

* **101 Switching Protocols**
  Used for protocol upgrades (e.g. WebSockets)

* **102 Processing** (WebDAV)
  Server is processing but no response yet

* **103 Early Hints**
  Allows browser to preload resources (e.g. `<link rel="preload">`)

---

### 🟢 2xx — Success

#### Core responses

* **200 OK**
  Standard success (GET, PUT, PATCH)

* **201 Created**
  Resource created
  👉 Should include `Location` header

* **202 Accepted**
  Async job started
  👉 Return job ID / status endpoint

* **204 No Content**
  Success, no body
  👉 Ideal for DELETE or idempotent updates

---

#### Less common but useful

* **205 Reset Content**
  Client should reset UI (rarely used)

* **206 Partial Content**
  Used for range requests (video streaming, downloads)

---

### 🟡 3xx — Redirection

#### SEO & browser behavior critical

* **301 Moved Permanently**
  👉 SEO passes link equity
  👉 Cached aggressively

* **302 Found**
  👉 Temporary redirect (historically ambiguous)

* **303 See Other**
  👉 Forces GET after POST (Post/Redirect/Get pattern)

* **304 Not Modified**
  👉 Used with caching headers (`ETag`, `If-Modified-Since`)

---

#### Modern correct redirects

* **307 Temporary Redirect**
  👉 Same as 302 but **preserves HTTP method**

* **308 Permanent Redirect**
  👉 Same as 301 but **preserves method**

---

### 🔴 4xx — Client Errors

---

#### 🔹 Validation & request issues

* **400 Bad Request**
  👉 Generic malformed request
  ❌ Avoid overusing (too vague)

* **422 Unprocessable Entity**
  👉 VALID syntax, INVALID data
  ✔ Best for form/API validation errors

```json
{
  "error": "Validation failed",
  "fields": {
    "email": "Invalid format"
  }
}
```

---

#### 🔹 Authentication & authorization

* **401 Unauthorized**
  👉 Missing/invalid authentication
  ✔ Should include `WWW-Authenticate` header

* **403 Forbidden**
  👉 Auth OK, but access denied

👉 Rule of thumb:

* Not logged in → **401**
* Logged in but blocked → **403**

---

#### 🔹 Resource issues

* **404 Not Found**
  👉 Resource doesn’t exist

* **410 Gone**
  👉 Resource permanently deleted (stronger than 404)

---

#### 🔹 Method & format

* **405 Method Not Allowed**
  👉 Endpoint exists, method doesn’t

* **406 Not Acceptable**
  👉 Server can't match `Accept` header

* **415 Unsupported Media Type**
  👉 Wrong `Content-Type` (e.g. XML instead of JSON)

---

#### 🔹 Request limits

* **408 Request Timeout**
  👉 Client too slow

* **413 Payload Too Large**
  👉 File upload too big

* **414 URI Too Long**
  👉 URL too long (GET abuse)

* **429 Too Many Requests**
  👉 Rate limiting
  ✔ Include:

```http
Retry-After: 60
```

---

#### 🔹 Conflict & state

* **409 Conflict**
  👉 Duplicate resource / version conflict

* **412 Precondition Failed**
  👉 `If-Match` / `If-Unmodified-Since` failed

---

### ⚫ 5xx — Server Errors

---

#### 🔹 Core failures

* **500 Internal Server Error**
  👉 Generic backend crash

* **501 Not Implemented**
  👉 Feature not supported

* **502 Bad Gateway**
  👉 Upstream (API, microservice) failed

* **503 Service Unavailable**
  👉 Server overloaded / maintenance
  ✔ Use with:

```http
Retry-After: 120
```

* **504 Gateway Timeout**
  👉 Upstream took too long

---

#### 🔹 Advanced / edge cases

* **505 HTTP Version Not Supported**
  👉 Protocol mismatch

* **507 Insufficient Storage** (WebDAV)
  👉 Server out of space

* **508 Loop Detected**
  👉 Infinite loop in processing

---

### 🧩 API DESIGN BEST PRACTICES

---

#### ✅ Status code selection strategy

| Scenario             | Best Code |
| -------------------- | --------- |
| Successful GET       | 200       |
| Resource created     | 201       |
| No response needed   | 204       |
| Validation error     | 422       |
| Unauthorized         | 401       |
| Forbidden            | 403       |
| Not found            | 404       |
| Conflict (duplicate) | 409       |
| Rate limit           | 429       |
| Server crash         | 500       |

---

#### ✅ Consistent error format

Use structured JSON:

```json
{
  "status": 422,
  "error": "Validation error",
  "code": "INVALID_EMAIL",
  "details": {
    "field": "email"
  }
}
```

---

#### ✅ Idempotency rules

* **GET, PUT, DELETE → idempotent**
* **POST → not idempotent**

👉 Example:

* Calling DELETE twice → still **204**, not error

---

#### ✅ Caching headers (tie with 304)

```http
ETag: "abc123"
Cache-Control: max-age=3600
```

---

#### ✅ Rate limiting pattern

```http
HTTP/1.1 429 Too Many Requests
Retry-After: 60
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 0
```

---

### 🧪 DEBUGGING SHORTCUT

---

#### If you see:

* **4xx** → Problem is **client-side**
* **5xx** → Problem is **server-side**

---

#### Fast diagnosis:

| Code | What to check          |
| ---- | ---------------------- |
| 400  | Request body / JSON    |
| 401  | Auth headers / token   |
| 403  | Permissions            |
| 404  | URL / routing          |
| 409  | Duplicate / state      |
| 422  | Validation             |
| 429  | Rate limits            |
| 500  | Logs                   |
| 502  | API gateway / upstream |
| 503  | Server load            |
| 504  | Timeout chain          |

---

### ⚡ Real-world patterns

---

### 🔁 Post/Redirect/Get

* POST → **303** → GET → **200**

---

### 📦 File upload

* Success → **201**
* Too large → **413**

---

### 🔄 REST update

* PUT → **200** or **204**
* PATCH → **200**

---

### 🚫 Auth flow

* No token → **401**
* Invalid role → **403**

---

### 🌐 CDN / caching

* Cached → **304**
* Fresh → **200**

