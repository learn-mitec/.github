# a little institution at mitec

We build developer tools and AI-powered learning platforms, primarily targeting the Vietnamese developer community.

## Products

### BookWorm

A web platform that helps Vietnamese learners read, understand, and learn English from academic/technical books.

- **Target user:** Vietnamese native speaker at B1 English level
- **Core idea:** Import a book → AI pre-populates learning content (summaries, translations, word analysis) → user learns vocabulary before reading
- **Flow:** EPUB → Markdown → Tree structure (Book → Part → Chapter → Section → Paragraph) → Word extraction with frequency analysis → AI-generated Vietnamese summaries and translations
- **Test book:** *The Black Swan* by Nassim Nicholas Taleb
- **Tech:** .NET 10, ASP.NET, EF Core + PostgreSQL, MCP server for AI-safe book access

### OpensourceLab

A microservices platform providing shared infrastructure services with access key management and usage tracking.

- **Services:** PostgreSQL provisioning, LLM gateway (via Copilot CLI), file conversion (MarkItDown), PDF processing (MinerU), email
- **Web portal:** ASP.NET MVC with magic-link auth, service request workflow with per-service resource limits, OTP approval
- **Local dev:** CPU-only Docker Compose stack with host-publish strategy for corporate proxy environments

### AgentFlow

A reusable .NET 10 NuGet package for building AI agent loops with provider-agnostic model adapters.

- **Core:** Agent loop abstractions, pipeline orchestration, DI-first design
- **Adapters:** Ollama model adapter (extensible to other providers)

## Repositories

| Repository | Purpose |
|------------|---------|
| [`opensource-lab`](https://github.com/learn-mitec/opensource-lab) | Microservices platform — Web, Gateway, Services (Postgres, LLM, MarkItDown, Email) |
| [`pdf-fordev-jobs`](https://github.com/learn-mitec/pdf-fordev-jobs) | BookWorm — background jobs, MCP server, book processing pipeline |
| [`pdfs-fordev-boostrap`](https://github.com/learn-mitec/pdfs-fordev-boostrap) | Deployment infrastructure — nginx, scripts, docker-compose |
| [`agent-loop-dotnet-10`](https://github.com/learn-mitec/agent-loop-dotnet-10) | AgentFlow NuGet package — reusable agent loop framework |
| [`contracts`](https://github.com/learn-mitec/contracts) | Shared NuGet packages — OpensourceLab.Contracts, OpenAI.Contracts |
| [`LLM-reverse-engine`](https://github.com/learn-mitec/LLM-reverse-engine) | OpenAI-compatible API server powered by GitHub Copilot CLI |
| [`software-department`](https://github.com/learn-mitec/software-department) | Agent definitions, copilot instructions, technical feasibility docs |

## Tech Stack

| Layer | Technology |
|-------|-----------|
| **Runtime** | .NET 10 (ASP.NET Minimal API + MVC) |
| **Database** | PostgreSQL + EF Core |
| **AI** | GitHub Copilot CLI (reverse-engineered as OpenAI-compatible API), MCP servers |
| **Agent framework** | AgentFlow (custom NuGet package) |
| **File processing** | MarkItDown (Python), MinerU (PDF → Markdown) |
| **Infrastructure** | Docker Compose, nginx reverse proxy |
| **CI/CD** | GitHub Actions, GitHub Packages (NuGet) |

## Technical Standards

### API

- Every API project **must** expose Swagger UI at `/swagger`
- OpenAPI spec served at `/openapi/v1.json`
- All endpoints require `.WithName()`, `.WithTags()`, `.WithSummary()` metadata

### Shared Contracts

API models consumed by multiple projects are centralized in the [`contracts`](https://github.com/learn-mitec/contracts) repo as NuGet packages. No duplicate DTOs across repos.

| Package | Scope |
|---------|-------|
| `OpensourceLab.Contracts` | Service interfaces, access key auth, job store |
| `OpenAI.Contracts` | Chat Completion request/response/chunk DTOs |

### Code Quality

- **Testing:** xUnit for unit and integration tests. Individual test functions (no test classes with shared state)
- **Performance:** Prefer `Span<T>`, `Memory<T>`, allocation-free parsing where applicable
- **Architecture:** DI-first, provider pattern for extensibility, pipeline orchestration for multi-step workflows

### Commits

Conventional commits: `feat:`, `fix:`, `docs:`, `refactor:`, `test:`, `chore:`

## Team

We use AI agent orchestration for development — each specialist agent handles a specific domain:

| Agent | Role |
|-------|------|
| **Phuong** | Orchestrator — routes tasks to specialists, never implements directly |
| **Tobi** | .NET architect — DI, pipelines, MCP server design |
| **Vu** | Performance specialist — data models, EF Core, algorithms |
| **Kathleen** | Refactoring — ASP.NET/Razor, code quality |
| **Andrew** | AI/ML — book domain, model evaluation |
| **Dusk** | Infrastructure — Docker, migrations, service management |
| **Jamie** | Chrome extension — PDF handling in browser |
| **Jasmine** | Testing — Playwright, regression, E2E |
| **Vuong** | Scrum master — sprint planning, backlog, coordination |

## Contributing

See the [`CONTRIBUTING.md`](https://github.com/learn-mitec/software-department/blob/main/CONTRIBUTING.md) in the software-department repo for guidelines on agent definitions, API standards, and technical feasibility documents.

## Project Board

Track our work on the [project board](https://github.com/orgs/learn-mitec/projects/1/views/1).
