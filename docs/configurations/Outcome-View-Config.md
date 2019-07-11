---
title: Outcome View Config
permalink: /docs/configurations/Outcome-View/
---

### Config File
`src/data/outcomeView.json`

### Format
```
{"column": [
    {"field": ""}
  ]
}

```
### Outcome View Configuration

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `field` | `string` | Determines the page with different ui-panel width |

**Example**
```
{"column": [
    {"field": "Address"},
    {"field": "Capability"},
    {"field": "ProductCategory"},
    {"field": "Shift"},
    {"field": "Skill"}
  ]
}
```
