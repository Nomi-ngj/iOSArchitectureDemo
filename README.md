# iOSArchitectureDemo

> A production-style iOS architecture demo using **Clean Architecture + MVVM + Coordinator + Repository Pattern + Dependency Injection + Swinject + Swift Concurrency**.

---

| Concept              | Implementation              |
| -------------------- | --------------------------- |
| Architecture         | Clean Architecture          |
| Presentation         | MVVM                        |
| Navigation           | Coordinator                 |
| Dependency Injection | Swinject                    |
| Data Access          | Repository Pattern          |
| Networking           | URLSession                  |
| Concurrency          | Swift Concurrency           |
| Authentication       | Access + Refresh Token      |
| Serialization        | Codable                     |
| Decoder              | `convertFromSnakeCase`      |
| Cancellation         | `Task` cancellation         |
| Token Refresh        | Actor + shared Task         |
| Testing              | Protocol-based dependencies |


## Architecture
                         ┌──────────────────────┐
                         │         APP          │
                         │ Composition Root     │
                         │      + Swinject      │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │     Coordinator      │
                         │      Navigation      │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │   ViewController     │
                         │         View         │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │     ViewModel        │
                         │ Presentation Logic   │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │       UseCase        │
                         │   Business Logic     │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │ Repository Protocol  │
                         │       Domain         │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │ Repository           │
                         │   Implementation     │
                         │        Data          │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │      API Client      │
                         │      URLSession      │
                         └──────────────────────┘
