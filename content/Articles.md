---
tags:
  - index
aliases:
  - "22.105"
---
```base
filters:
  and:
    - file.hasLink(this.file)
views:
  - type: list
    name: View

```


```mermaid
flowchart TD
    A[Start] --> B[Learn Finance]
    B --> C{Understand Concept?}
    C -->|Yes| D[Make Notes]
    C -->|No| E[Read Again]
    E --> B
    D --> F[End]

```

