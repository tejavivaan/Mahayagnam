# API = Application Programming Interface
- Break it down:
  - **Application** → Any software (mobile app, website, backend service)
  - **Programming** → Code written by developers
  - **Interface** → A communication boundary
- So API = **A communication interface between two software applications.**
- ``An API is a messenger that allows two software systems to talk to each other.``
## What is an API?
- **An API is a set of rules and endpoints that define how one system can request data or perform actions in another system.**
### Why APIs Are Needed
- **Connect different systems**
  - Apps are built using different languages:
  - Frontend → React, Backend → Java, Mobile → Swift / Kotlin, Database → SQL
  - They can’t talk directly.
  - APIs act as a common language. 
- **Hide internal logic**
  - You never expose: Database, Business logic, Internal code
  - Instead, you expose only controlled endpoints.   
- **Provide controlled access**
  - One API can be used by: Mobile app, Web app, Backend services, Third-party partners
  - Write once → Use everywhere.     
- **Improve security**
  - APIs support: API Keys, Tokens, OAuth2, JWT, Rate limiting
  - This ensures only authorized users can access data. 
- **Enable automation**
  - DevOps pipelines, monitoring tools, cloud services — all use APIs.
  - Jenkins triggers → API
  - Grafana alerts → API 
- **Speed up development**
  - Instead of building everything from scratch, apps use existing APIs:
  - Google Maps API, Payment APIs (Razorpay, Stripe), Weather APIs, SMS APIs
  - This saves months of work. 
- **Standardize communication**
  - APIs use standard formats: JSON, XML, YAML
  - This makes communication predictable and consistent.

### Real-World Examples
- Swiggy uses restaurant APIs
- Uber uses Google Maps API
- Paytm uses bank APIs
- Weather apps use weather APIs
- Your company tools talk via internal APIs

### API = Request + Response
- Client sends request
- Server sends response
- API defines how this communication happens


## API Concept
- API that uses HTTP methods to perform actions on data.
  - GET → “Show me the items”
  - POST → “Add a new item”
  - PUT → “Update an item”
  - DELETE → “Remove an item”
- REST API Syntax (Generic Format)
  - HTTP_METHOD /api/{version}/{resource}?queryParams
    Host: domain.com
    Authorization: Bearer <token>
    Accept: application/json
    Content-Type: application/json   <-- only for POST/PUT/PATCH
- Breaking the Syntax Down
  - HTTP_METHOD → GET, POST, PUT, DELETE
  - /api/{version}/{resource} → URL path
  - ?queryParams → filters, sorting, pagination
  - Host → server domain
  - Authorization → token or API key
  - Accept → what format you want back
  - Content-Type → what format you are sending (only for POST/PUT)
- API Architecture Pattern
  - | **API Type** | **Full Form** | **[Architecture Pattern](ca://s?q=Explain_API_architecture_patterns)** | **Strengths** | **Trade‑offs** | **Best Use** |
    | --- | --- | --- | --- | --- | --- |
    | **[REST](ca://s?q=Explain_REST_API_full_form)** | Representational State Transfer | **Resource‑based architecture** (URLs represent resources; uses HTTP verbs) | Simple, universal, cache‑friendly | Over/under‑fetching, no real‑time, versioning issues | CRUD apps, public APIs |
    | **[GraphQL](ca://s?q=Explain_GraphQL_full_form)** | Graph Query Language | **Query‑based architecture** (client defines the shape of data) | No over‑fetching, flexible, single endpoint | Complex caching, schema governance, query cost issues | Dashboards, mobile apps |
    | **[SOAP](ca://s?q=Explain_SOAP_API_full_form)** | Simple Object Access Protocol | **Contract‑based architecture** (WSDL, strict XML messaging) | Secure, strict, reliable | Heavy XML, slower, complex | Banking, telecom, enterprise |
    | **[gRPC](ca://s?q=Explain_gRPC_full_form)** | Google Remote Procedure Call | **RPC‑based architecture** using Protobuf + HTTP/2 | Extremely fast, streaming, strong typing | Not browser‑friendly, binary debugging | Microservices, internal systems |
    | **[WebSockets](ca://s?q=Explain_WebSockets_full_form)** | — | **Full‑duplex, persistent connection architecture** | Real‑time, low latency | Scaling issues, connection management | Chat, gaming, live dashboards |
    | **[Webhooks](ca://s?q=Explain_Webhooks_full_form)** | — | **Event‑driven push architecture** (server → client callbacks) | Simple, no polling, lightweight | Delivery not guaranteed, security needed | Integrations, automation triggers |
