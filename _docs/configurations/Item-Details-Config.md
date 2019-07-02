---
title: Item-Details-Config
permalink: /docs/configurations/Item-Details-Config/
---

# Config File

`src/data/itemDetailsExceptions.json`

# Format
```
  {
    "detailsExceptions": [
      {
        "name": string,
        "path": string,
        "finalize":  string,
        "sequence": string,
        "factory": string,
        "steps": string
      }
    ]
  }
```
# Steps config

Config for displaying p-steps in item details

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `name`| `string` | name for specific item-details configuration |
| `path `| `string` | domain path |
| `finalize` | `string` | view point name of the config for finalize |
| `sequence` | `string` | view point name of the config for sequence |
| `factory` | `string` | factory name of the config |
| `steps` | `strings` | steps name of the config |

# Example
```
  {
    "detailsExceptions": [
      {
        "name": "WorkOrder",
        "path": "/hmws"
        "finalize":  "WorkOrder_Finalize",
        "sequence": "WorkOrder_ProductionSequence",
        "factory": "WorkOrderFactory",
        "steps": "Production State"
      }
    ]
  }
```