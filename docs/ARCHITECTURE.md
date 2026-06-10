# Architecture

## Overview

FrilChain is a Web3 platform designed to explore, collect, analyze, and deliver blockchain data.

The system is intentionally separated into multiple services so that each component can focus on a single responsibility.

---

## Architecture Goals

- Clear separation of concerns
- Independent service development
- Event-driven communication
- Scalable blockchain indexing
- Real-time data delivery

---

## High-Level Architecture

```text
Browser
    │
    ▼
Next.js
    │
 REST API
    │
    ▼
Spring Boot
    │
    ├──────── PostgreSQL
    │
    ├──────── Redis Pub/Sub
    │
    └──────── Rust Service
                    │
               JSON-RPC
                    │
                    ▼
            Blockchain Node
```

---

## Service Responsibilities

### Web

Location:

```text
apps/web
```

Responsibilities:

- User Interface
- Wallet Explorer
- Portfolio View
- Real-Time Dashboard

Technology:

- Next.js
- TypeScript
- Bun

---

### API

Location:

```text
apps/api
```

Responsibilities:

- Authentication
- Authorization
- Watchlist Management
- Portfolio APIs
- Event Distribution

Technology:

- Spring Boot
- Spring Security
- OAuth2
- JWT

---

### Indexer

Location:

```text
apps/indexer
```

Responsibilities:

- Blockchain Communication
- JSON-RPC Requests
- Event Collection
- Indexing Pipeline

Technology:

- Rust

---

## Communication

### REST API

Used between:

```text
Web
↓
API
```

---

### JSON-RPC

Used between:

```text
Indexer
↓
Blockchain Node
```

---

### WebSocket

Used between:

```text
API
↓
Browser
```

---

### Redis Pub/Sub

Used between:

```text
Indexer
↓
API
```

---

### Kafka

Planned for large-scale event processing.

```text
Indexer
↓
Kafka
↓
Consumers
```

---

## Database Strategy

Initial stages:

- users
- oauth_accounts
- watchlists

Blockchain data will not be fully stored during the early phases.

The project starts as a wallet explorer and gradually evolves into a blockchain data platform.

---

## Future Direction

Phase 1:

Wallet Explorer

Phase 2:

Portfolio Platform

Phase 3:

Real-Time Platform

Phase 4:

Blockchain Data Platform
