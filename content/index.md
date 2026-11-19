---
title: index
---

```base
filters:
  and:
    - file.hasTag("index")
formulas:
  Related Notes: file.backlinks.length
views:
  - type: cards
    name: View
    order:
      - file.name
      - file.backlinks

```

