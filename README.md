# FrilChain

🚧 Early Development

FrilChain is a Web3 platform for exploring, collecting, analyzing, and delivering blockchain data.

The project starts as a lightweight wallet explorer and portfolio service, with a long-term goal of evolving into a blockchain data platform powered by event-driven architecture.

---

## Project Goals

FrilChain aims to evolve through the following stages.

### Phase 1 - Wallet Explorer

Retrieve blockchain data directly from the network.

Features:

- Wallet balance lookup
- ERC20 token lookup
- Recent transaction history

---

### Phase 2 - Portfolio Platform

Manage watchlists and portfolio information.

Features:

- OAuth authentication
- Watchlist management
- Portfolio summary
- Token holdings

---

### Phase 3 - Real-Time Platform

Deliver blockchain events in real time.

Features:

- Transaction notifications
- Watchlist monitoring
- Real-time event streams

---

### Phase 4 - Blockchain Data Platform

Build a scalable event-driven blockchain data platform.

Features:

- Event indexing
- Data analytics
- Statistics APIs
- Multi-chain support

---

## Core Technical Objectives

FrilChain is designed to apply multiple communication patterns and distributed system concepts in a practical environment.

### JSON-RPC

Used for communication with blockchain nodes.

Use cases:

- Wallet balance lookup
- Token lookup
- Transaction lookup
- Block lookup

Architecture:

User → Spring API → Rust RPC Service → Blockchain Node

---

### REST API

Primary communication layer between clients and backend services.

Use cases:

- User APIs
- Portfolio APIs
- Watchlist APIs
- Authentication APIs

---

### OAuth2

External authentication providers.

Use cases:

- Google Login
- GitHub Login
- Future Wallet Login integration

---

### JWT

Stateless authentication and authorization.

Use cases:

- Access Token
- Refresh Token
- Protected APIs

---

### WebSocket

Real-time bidirectional communication.

Use cases:

- Transaction notifications
- Watchlist updates
- Live status updates

---

### Server-Sent Events (SSE)

Lightweight server-to-client event streaming.

Use cases:

- Live transaction feeds
- Event notifications

---

### Redis Pub/Sub

Inter-service event delivery.

Use cases:

- Event broker
- Notification pipeline
- Asynchronous processing

Architecture:

Rust Publisher → Redis → Spring Subscriber

---

### Apache Kafka

Large-scale event streaming and processing.

Use cases:

- Event pipelines
- Stream processing
- Blockchain indexing

Architecture:

Indexer → Kafka → Consumer → Database

---

## Technology Stack

### Frontend

- Next.js
- TypeScript
- Bun

### Backend

- Spring Boot
- Java 21
- Spring Security
- JWT
- OAuth2

### Blockchain Service

- Rust
- JSON-RPC

### Messaging

- Redis Pub/Sub
- Apache Kafka

### Database

- PostgreSQL

### Infrastructure

- Docker
- Nginx

---

## Repository Structure

```text
frilchain

├── apps
│   ├── web
│   ├── api
│   └── indexer
│
├── infra
│   ├── docker
│   └── nginx
│
├── docs
│
└── .github
```
