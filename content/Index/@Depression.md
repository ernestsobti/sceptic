---
tags:
  - homepage
up: "[[content/index|index]]"
aliases:
  - "20.30"
---
```base
filters:
  and:
    - file.hasLink(this.file)
properties:
  file.name:
    displayName: Notes
views:
  - type: table
    name: View
    order:
      - aliases
      - file.name
    columnSize:
      note.aliases: 180
      file.name: 390

```