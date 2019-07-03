---
title: Collection Config
permalink: /docs-webui/docs/configurations/Collection-Config/
---

### Config File

`src/data/{itemType}/itemCollection.json`

### Format
```
[
  {"name": "Children"             , "header": "Children"               , "icon": "fa fa-child" },
  {"name": "PurchaseOrderRows"    , "header": "Purchase Order Rows"    , "icon": "fa fa-cash-register" }
]  
```
### Steps config

Config for displaying p-steps in item details

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `name`| `string` | Name of the collection tab |
| `header`| `string` | This is for the header of the collection tab  |
| `icon` | `string` | An icon to be set using font-awesome icons |