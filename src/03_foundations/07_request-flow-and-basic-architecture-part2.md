---
learning_level: "Beginner"
prerequisites: ["Request Flow and Basic Architecture (Part 1)"]
estimated_time: "25 minutes"
learning_objectives:
  - "Recognize when to separate web server and database"
  - "Understand API response formats and traffic sources"
  - "Apply architectural separation principles"
related_topics:
  prerequisites:
    - ./07_request-flow-and-basic-architecture-part1.md
  builds_upon:
    - ./07_request-flow-and-basic-architecture-part1.md
  enables:
    - ../04_principles/03_scalability.md
    - ../05_building-blocks/02_load-balancers.md
    - ../07_case-studies/01-scalefromzerotomillonusers/README.md
  cross_refs: []
---

# Request Flow and Basic Architecture (Part 2)

## Separating Web Server and Database

### Why Separation Is Needed

As traffic grows, running everything on one server creates bottlenecks:

- **Resource Contention**: Web processing and database I/O compete for CPU and memory
- **Scaling Constraints**: Cannot scale web and database independently
- **Performance Issues**: Database queries slow down web request processing

### Improved Architecture

Separate web tier from data tier:

```mermaid
graph TB
    User[User] -->|HTTPS| DNS[DNS]
    DNS -->|IP| WebServer[Web Server<br/>Application + API]
    WebServer -->|Queries| Database[(Database Server<br/>Dedicated)]
    
    style WebServer fill:#e1f5ff
    style Database fill:#fff4e1
```

### Benefits of Separation

- ✅ **Independent Scaling**: Scale web and database separately
- ✅ **Better Performance**: Dedicated resources for each tier
- ✅ **Clear Separation**: Easier to optimize each component
- ✅ **Fault Isolation**: Database issues don't directly crash web server

## DNS in System Architecture

### What Is DNS?

Domain Name System (DNS) translates human-readable domain names to IP addresses.

**Example**:

- Domain: `api.example.com`
- IP Address: `192.168.1.100`

### Key Points

- **Third-Party Service**: DNS is typically managed by external providers (AWS Route 53, Cloudflare, etc.)
- **Caching**: DNS responses are cached to reduce lookup time
- **TTL (Time To Live)**: Controls how long DNS responses are cached
- **Multiple Record Types**: A records (IPv4), AAAA records (IPv6), CNAME (aliases)

### DNS Role in Scaling

DNS becomes critical for:

- **Load Distribution**: Route traffic to multiple servers
- **Geographic Routing**: Direct users to nearest data center
- **Failover**: Switch to backup servers during outages
- **CDN Integration**: Route static content to edge locations

## API Response Formats

### JSON as Standard

Modern APIs primarily use JSON (JavaScript Object Notation) for responses.

**Why JSON**:

- ✅ Lightweight: Smaller than XML
- ✅ Human-readable: Easy to debug
- ✅ Language-agnostic: Works with any programming language
- ✅ Efficient serialization: Fast parsing and generation

### REST Endpoint Example

```
GET /users/123
```

**Example API Response**:

```json
{
  "id": 123,
  "name": "John Doe",
  "email": "john@example.com",
  "created_at": "2025-01-15T10:30:00Z"
}
```

## Traffic Sources

### Web Applications

- **Server-Side**: Java, Python, Node.js, .NET, etc.
- **Client-Side**: HTML, CSS, JavaScript
- **Rendering**: Server generates HTML or serves static files

### Mobile Applications

- **Communication**: HTTP/HTTPS protocol
- **Format**: JSON for API responses
- **No HTML**: Mobile apps render UI natively
- **API-First**: Backend serves data, not presentation

## Architectural Evolution Path

### Phase 1: Single Server

Everything runs on one machine:

- Web application
- Database
- Static files

**Use Case**: Prototypes, MVPs, very small scale

### Phase 2: Separated Tiers

Web server and database on separate machines:

- Independent scaling
- Better performance
- Clear separation of concerns

**Use Case**: Growing applications, medium scale

### Phase 3: Multiple Servers

Multiple web servers with load balancer:

- Horizontal scaling
- High availability
- Distributed architecture

**Use Case**: Large-scale applications

## Key Takeaways

1. **Separate Concerns**: Split web and database as you grow
2. **DNS Matters**: Critical for routing and scaling
3. **JSON Standard**: Modern APIs use JSON for data exchange
4. **Plan Evolution**: Design with future separation in mind
5. **Independent Scaling**: Separation enables independent scaling of components
6. **Traffic Sources**: Web and mobile apps have different requirements

---

*Previous: [Request Flow and Basic Architecture (Part 1)](./07_request-flow-and-basic-architecture-part1.md)*  
*Next: Learn about [Scalability Principles](../../04_principles/03_scalability.md) or explore [DNS](../../05_building-blocks/01_dns.md) in detail.*

