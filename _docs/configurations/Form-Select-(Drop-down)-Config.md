---
title: Form Select (Drop-down) Config
permalink: /docs/configurations/Form-Select-(Drop-down)-Config/
---

### Config File
`src/data/${ItemType}/formSelect${JobName}.json`

### Example
```
{
    "fields": [{
        "name": "PurchaseOrder",
        "itemField": "Customer",
        "querySequence": "0",
        "querySequenceChanged": "2"
    }]
}

```
### Column
**Config for fields**

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `name` | `string` | name of the drop down field with updateScriptRef |
| `itemField` | `string` | field name to be filtered in the script |
| `querySequence` | `string` | querySequence used in the query script for initial load |
| `querySequenceChanged` | `string` | querySequence used in the query script upon changing selection in the drop down |

`fields` list of drop down field or fields that has to be filtered based on the given `itemField`