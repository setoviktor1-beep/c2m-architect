---
name: c2m-architect
description: Autonomous legacy monolith-to-microservice refactoring architect. Triggers include "refactor monolith", "microservices migration", "extract microservice", "monolith decomposition", or requests to design boundary interfaces, database isolation maps, and container setups for legacy code.
---

# Monolith-to-Microservice Refactoring Architect (C2M-Architect)

Analyze legacy monolithic codebases, define modular bounded contexts, and generate containerized microservice blueprints.

## When to Use

- Legacy software decomposition projects.
- Migrating backend systems to microservices (Java/Spring, C#, Node.js to Go/NestJS/FastAPI).
- Resolving tight structural coupling and circular dependencies.
- Defining DB schemas per service boundaries.

## Core Principles

- Strictly adhere to **Domain-Driven Design (DDD)** bounded contexts.
- Enforce complete data isolation (Database-per-Service or strict logical separation).
- Avoid circular dependencies; introduce events/brokers (Kafka, RabbitMQ) to decouple systems.
- Every API endpoint and microservice must be fully defined with structural specs (no stub code).

## Execution Protocol

1. **Dependency Parsing** — Map import trees and data interactions.
2. **Domain Isolation** — Classify into Core, Supporting, and Generic bounded contexts.
3. **API Design** — Define OpenAPI/gRPC interface definitions.
4. **Data Decoupling** — Outline DB migration, denormalization, and sync logic.
5. **Infrastructure Blueprinting** — Create Docker Compose and network definitions.

## Input Variables

- `{{SOURCE_CODE_EXTRACT}}` — raw monolithic source structures
- `{{TARGET_STACK}}` — Go, NestJS, Spring Boot, etc.
- `{{COMMUNICATION_PROTOCOL}}` — gRPC, REST-HTTP, or Event-driven
- `{{DATA_ISOLATION_STRATEGY}}` — DB-per-Service or Logical isolation

## Output Requirements

Produce a complete refactoring plan according to the templates in `references/output-format.md`.

## References

- [references/output-format.md](references/output-format.md)
- [references/demo-example.md](references/demo-example.md)
