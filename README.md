# EnterpriseHub

A multi-tenant business management platform built as a hands-on Laravel
laboratory — customers, products, stock, orders, invoicing, receivables and
payables for multiple companies on one shared codebase, used as the vehicle
to demonstrate a broad, coherent slice of Laravel 13+ in a project realistic
enough to hold up as a portfolio piece: queues, events, observers,
notifications, Sanctum, caching, testing, and observability, applied because
the domain actually needs them — not bolted on for show.

> **Status: Phase 1 — Architecture.** No application code yet. This
> repository currently holds the system design that every later phase is
> built against. See [Roadmap](docs/architecture.md#24-roadmap).

## Why this project exists

Built in public as a learning project and a portfolio piece — the goal is
to show real command of Laravel's toolbox on a system with enough moving
parts (multi-tenancy, stock concurrency, async invoicing, RBAC) that the
"why" behind each architectural choice is a genuine trade-off, not a
tutorial default. Every non-trivial decision is documented, including where
a heavier pattern (Repository, Event, Job) was deliberately **not** used.

## Development process

Designed and built with **Claude Code** (Anthropic) as an architecture and
implementation partner — used the way a senior pair-programmer would be:
proposing options and trade-offs, writing the first draft of code and docs,
running and fixing tests. Every architectural decision, scope choice, and
phase gate was directed and reviewed by the project owner; the reasoning
behind each one is written down in [docs/architecture.md § Architectural
decisions](docs/architecture.md#architectural-decisions) rather than left
implicit. Commit history doesn't carry AI co-author trailers — this section
is the disclosure instead.

## Documentation

| Doc | Contents |
|---|---|
| [docs/architecture.md](docs/architecture.md) | system overview, modules, multi-tenancy, auth/authorization, folder structure, process flows, queue/event/cache/storage/API architecture, testing strategy, Docker, roadmap, architectural decisions |
| [docs/database.md](docs/database.md) | ER diagrams, full table reference, enums, indexes, known risk areas |

More docs (`api.md`, `queues.md`, `testing.md`, `deployment.md`, ...) are
added as the corresponding phase is implemented, per the roadmap.

## Stack

PHP 8.3+, Laravel 13+, MySQL 8, Redis, Docker/Docker Compose, Nginx,
PHP-FPM, Vite. Frontend starts as Blade + Livewire, with the backend kept
API-first enough that a future React/Vue/mobile client can consume
`/api/v1` without a rewrite.

## Getting started

Not available yet — installation, Docker setup, environment variables,
migrations, seeders, and demo users are documented here starting in
**Phase 2** (Infrastructure).

## Roadmap

| Phase | Scope | Status |
|---|---|---|
| 1 | Architecture | ✅ done |
| 2 | Infrastructure (Docker, Laravel, MySQL, Redis, Nginx, queue, scheduler) | planned |
| 3 | Core (Users, Companies, Roles, Permissions, Auth) | planned |
| 4 | Business (Customers, Products, Stock, Orders) | planned |
| 5 | Finance (Invoices, Payments, Receivables, Payables) | planned |
| 6 | Advanced Laravel (Events, Jobs, Queues, Notifications, Cache, Storage) | planned |
| 7 | API (Sanctum, Resources, Versioning, Rate limiting) | planned |
| 8 | Reports (PDF, Excel, CSV, background processing) | planned |
| 9 | Testing (Unit, Feature, API, Queue, Event) | planned |
| 10 | Production (Performance, Observability, CI/CD, Security) | planned |

Full detail in [docs/architecture.md § 24](docs/architecture.md#24-roadmap).
