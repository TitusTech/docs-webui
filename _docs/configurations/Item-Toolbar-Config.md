---
title: Item-Toolbar-Config
permalink: /docs/configurations/Item-Toolbar-Config/
---

# Config File
`src/data/ItemToolbarConfig.json`

# Format
```
{
  "noForms": {
    "delete": string[],
    "confirm": string[]
  }
}

```
# Button Activity Names

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `delete` | `string[]` | Activity names that will trigger the Delete Dialog |
| `confirm` | `string[]` | Activity names that will trigger the Confirm Dialog |

**Example**
```
{
  "noForms": {
    "delete": ["Deactivate", "RemoveMember", "RemoveEvent", "RemoveAddress", "RemovePurchaseOrderRow"],
    "confirm": ["CUTTING LIST", "BOM", "ASSEMBLY BOARD DRAWING", "SPLICE DRAWINGS", "WorkOrderParts_Finalize"]
  }
}
```