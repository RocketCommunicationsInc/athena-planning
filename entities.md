# Entities
These are essentially models which would translate into database tables. It's not a complete picture because mermaid is unable to display single nodes. Also relationships like `many-many` are ambiguous due to indirection.

```mermaid
erDiagram
  ACCOUNT ||--|{ USER : one-many
  ACCOUNT ||--o{ PROJECT : one-many
  PROJECT ||--o{ STUDY : one-many
  PROJECT ||--o{ PERSONA : many-many
  STUDY ||--o{ PARTICIPANT : many-many
  STUDY ||--o{ RESEARCH-PLAN : one-many
  STUDY ||--o{ INTERVIEW : one-many
  INTERVIEW ||--o| SCRIPT : one-one
  INTERVIEW ||--o{ RECORDING : one-many
  INTERVIEW ||--o{ NOTE : one-many
  TAG }o--o{ NOTE : many-many
  TAG }o--o{ INTERVIEW : many-many
  TAG }o--o| STUDY : many-one
  RECORDING |o--o{ NOTE : one-many
```
