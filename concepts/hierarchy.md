---
description: The tree-like structure in which your workspaces are structured.
---

# Entity Hierarchy

The overall structure looks like this:

```yaml
- owner (ex. elonmusk@tesla.com)
  - workspace (ex. spacex)
    - project (ex. api)
      - environment (ex. dev=default, staging, prod)
        - secrets/variables
```
