# API = Application Programming Interface
- Break it down:
  - **Application** → Any software (mobile app, website, backend service)
  - **Programming** → Code written by developers
  - **Interface** → A communication boundary
- So API = **A communication interface between two software applications.**
- ``An API is a messenger that allows two software systems to talk to each other.``
## What is an API?
- **An API is a set of rules and endpoints that define how one system can request data or perform actions in another system.**
## Why APIs Are Needed
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

## Real-World Examples
- Swiggy uses restaurant APIs
- Uber uses Google Maps API
- Paytm uses bank APIs
- Weather apps use weather APIs
- Your company tools talk via internal APIs

## API = Request + Response
- Client sends request
- Server sends response
- API defines how this communication happens
