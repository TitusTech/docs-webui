---
title: Details View Config
permalink: /docs/configurations/Details-View/
---

### Config File
`src/data/detailsView.json`

### Format
```
{"column": [
    {"field": "", "width": 0},
    {"field": "", "width": 0}
  ]
}

```
### Details View Configuration

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `field` | `string` | The current page displayed |
| `width` | `number` | The width for the details panel for the current page |

**Example**
```
{"column": [
    {"field": "Address",          "width": 100},
    {"field": "Capability",       "width": 100},
    {"field": "Company",          "width": 50},
    {"field": "Department",       "width": 50},
    {"field": "Employee",         "width": 50}
  ]
}
```
