# a little institution at mitec

We build developer tools and AI-powered learning platforms for the Vietnamese developer community.

## Products

### 📚 BookWorm

A web platform that helps Vietnamese learners read and understand English academic books.

Import a book, and AI prepares everything you need before reading — Vietnamese summaries for each chapter, word translations ranked by difficulty, pronunciation guides, and collocations. You learn the vocabulary first, then read with confidence.

### 🔧 OpensourceLab

A shared infrastructure platform that gives developers instant access to common services — databases, LLM APIs, file conversion, email — through a simple web portal with access key management.

### 🔄 AgentFlow

A reusable NuGet package for building AI agent loops in .NET — provider-agnostic, DI-first, pipeline-ready.

## How We Build

We hold ourselves to a high bar. Here's what that looks like in practice.

🧩 **Plug it in, swap it out** — Every major component is designed to be replaced without touching anything else. Change the AI provider, the database, the file converter — zero downtime, zero rewrite. This isn't accidental; it's architectural discipline.

🔍 **We know before you do** — Every service reports its health. Every operation leaves a trail. When something breaks at 2 AM, we already know where and why — before anyone files a ticket.

🧠 **Context first, action second** — Our AI reads the entire chapter before translating a single word. Our developers study existing patterns before writing new code. We never guess when we can know.

🛡️ **Security is not a feature — it's the foundation** — Rate limiting, credential isolation, path-traversal protection, hardened proxies, API key authentication. All baked in from day one. Not bolted on later.

🪞 **One pattern, everywhere** — When we solve a problem once, we replicate the exact same approach across every domain. Consistency isn't laziness — it's how you scale quality.

📦 **Shared contracts, zero drift** — Common data models are published as packages across all repositories. When a contract changes, every consumer knows immediately. No surprise breakages in production.

⚡ **Fail loud, fail fast** — If a required setting is missing, the app crashes on startup with a clear error — not silently 30 minutes later when a user hits it. We'd rather wake up to a clear failure than a mystery.

🧪 **Tested at every layer** — Unit tests for logic, integration tests for full-stack flows, end-to-end tests for critical user journeys. Bugs are caught before they ship — not after.

🏗️ **One command, full stack** — Databases, AI services, web servers, reverse proxies — the entire environment spins up from a single command. Every deployment is reproducible and identical.

🤖 **AI that knows our codebase** — Our AI assistants aren't generic. They're trained on our conventions, our architecture, our workflows. They work like senior developers who've been here since day one.

🎯 **We ship what matters first** — Every ticket is ordered deliberately. Dependencies are mapped, feasibility is assessed, and quick wins with high impact go to the top. We don't just work hard — we work on the right things in the right order.

> 📄 For the full technical details, see our [engineering standards](https://github.com/learn-mitec/software-department/blob/main/engineering-standards.md).

## Repositories

| Repository | Purpose |
|------------|---------|
| [`opensource-lab`](https://github.com/learn-mitec/opensource-lab) | OpensourceLab platform |
| [`pdf-fordev-jobs`](https://github.com/learn-mitec/pdf-fordev-jobs) | BookWorm backend and book processing |
| [`pdfs-fordev-boostrap`](https://github.com/learn-mitec/pdfs-fordev-boostrap) | Deployment infrastructure |
| [`agent-loop-dotnet-10`](https://github.com/learn-mitec/agent-loop-dotnet-10) | AgentFlow NuGet package |
| [`contracts`](https://github.com/learn-mitec/contracts) | Shared API contracts (NuGet) |
| [`LLM-reverse-engine`](https://github.com/learn-mitec/LLM-reverse-engine) | OpenAI-compatible API via Copilot CLI |
| [`software-department`](https://github.com/learn-mitec/software-department) | Team processes and documentation |

## Contributing

See [`CONTRIBUTING.md`](https://github.com/learn-mitec/software-department/blob/main/CONTRIBUTING.md) for guidelines.

## Project Board

Track our work on the [project board](https://github.com/orgs/learn-mitec/projects/1/views/1).
