## $${\color{red}API \ Types \ Cheat \ Sheet}$$

### Common API Types:

| Type       | Description                            |
| ---------- | -------------------------------------- |
| REST       | Resource-based, uses HTTP methods      |
| SOAP       | XML-based, strict contract (WSDL)      |
| GraphQL    | Client defines requested data          |
| RPC        | Remote procedure calls                 |
| WebSockets | Real-time, bidirectional communication |



## 1️⃣ REST (Representational State Transfer)

**Most common web API style**

### Key Characteristics

* Stateless requests
* Resource-based URLs
* Uses standard HTTP methods
* Typically JSON responses

### Example

```
GET /api/v1/products/42
```

### Pros

* Simple and predictable
* Easy to cache
* Widely supported
* Great for CRUD apps

### Cons

* Over-fetching / under-fetching data
* Multiple requests for related resources
* No strict contract by default

### Best Use Cases

* Web & mobile apps
* Public APIs
* Microservices

---

## 2️⃣ SOAP (Simple Object Access Protocol)

**Enterprise-grade, contract-first API**

### Key Characteristics

* XML-based only
* Strong schema (WSDL)
* Strict rules and validation
* Transport-agnostic (HTTP, SMTP)

### Example

```xml
<soap:Envelope>
  <soap:Body>
    <GetUserRequest />
  </soap:Body>
</soap:Envelope>
```

### Pros

* Strong typing
* Built-in security (WS-Security)
* Reliable transactions

### Cons

* Verbose XML
* Harder to debug
* Slower development

### Best Use Cases

* Banking
* Government systems
* Legacy enterprise software

---

## 3️⃣ GraphQL

**Client-driven data fetching**

### Key Characteristics

* Single endpoint
* Strongly typed schema
* Client defines response shape
* Supports queries, mutations, subscriptions

### Example

```graphql
query {
  user(id: 1) {
    name
    email
  }
}
```

### Pros

* No over-fetching
* Fewer requests
* Excellent frontend performance
* Strong introspection

### Cons

* Caching complexity
* More complex backend
* Query abuse risk

### Best Use Cases

* Complex UIs
* Mobile apps
* Data aggregation APIs

---

## 4️⃣ RPC (Remote Procedure Call)

**Function-oriented APIs**

### Key Characteristics

* Calls functions, not resources
* Action-based endpoints
* Tight coupling client ↔ server

### Example

```
POST /getUser
```

### Pros

* Simple mental model
* High performance
* Strong contracts

### Cons

* Poor discoverability
* Less REST-friendly
* Versioning is harder

### Best Use Cases

* Internal services
* Microservices
* High-performance systems

---

## 5️⃣ gRPC

**Modern, high-performance RPC**

### Key Characteristics

* Built on HTTP/2
* Uses Protocol Buffers (binary)
* Strongly typed contracts
* Supports streaming

### Example

```proto
rpc GetUser (UserRequest) returns (UserResponse);
```

### Pros

* Extremely fast
* Low bandwidth
* Code generation
* Bi-directional streaming

### Cons

* Harder to debug
* Browser limitations
* Less human-readable

### Best Use Cases

* Microservices
* Internal APIs
* Real-time systems

---

## 6️⃣ WebSockets API

**Persistent real-time communication**

### Key Characteristics

* Full-duplex connection
* Server can push data
* Stateful connection

### Example

```js
socket.send("message");
```

### Pros

* Real-time updates
* Low latency
* Efficient for live data

### Cons

* Harder to scale
* Stateful connections
* Requires fallback strategies

### Best Use Cases

* Chat apps
* Live dashboards
* Online games

---

## 7️⃣ Webhooks

**Event-driven callbacks**

### Key Characteristics

* Server-to-server
* Push-based
* Triggered by events

### Example

```
POST https://client.app/webhook
```

### Pros

* Near real-time
* No polling
* Lightweight

### Cons

* Delivery reliability
* Security concerns
* Debugging difficulty

### Best Use Cases

* Payment notifications
* CI/CD triggers
* SaaS integrations

---

## 8️⃣ Streaming APIs

**Continuous data flow**

### Key Characteristics

* Persistent data streams
* Event-based
* Push or pull models

### Examples

* Kafka APIs
* SSE (Server-Sent Events)

### Pros

* Scales well
* Handles large data volumes
* Real-time analytics

### Cons

* More complex setup
* Harder error handling

### Best Use Cases

* Logs
* Metrics
* IoT data

---

## 9️⃣ Public vs Private vs Partner APIs

| Type    | Description                  |
| ------- | ---------------------------- |
| Public  | Open for external developers |
| Private | Internal use only            |
| Partner | Restricted access            |

---

## 🔍 Comparison Overview

| Type       | Speed     | Flexibility | Complexity |
| ---------- | --------- | ----------- | ---------- |
| REST       | Medium    | Medium      | Low        |
| GraphQL    | Medium    | High        | Medium     |
| SOAP       | Low       | Low         | High       |
| gRPC       | Very High | Medium      | High       |
| WebSockets | High      | High        | Medium     |

---

## 🧠 Choosing the Right API Type

* CRUD → **REST**
* Complex frontend → **GraphQL**
* High performance → **gRPC**
* Real-time → **WebSockets**
* Events → **Webhooks**
* Legacy enterprise → **SOAP**

---
