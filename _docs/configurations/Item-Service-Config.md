---
title: Item Service Config
permalink: /docs/configurations/Item-Service-Config/
---

### Config File

`src/data/itemServiceExceptions.json`


### Format
```
{
  "createExceptions":
    [
      {
        "name": string,
        "action": string
      }
    ],
  "collectionExceptions": [
      {
        "outcomeName": string,
        "collection": string,
        "collectionName": string
      }
    ]
}
```
### Create Item Config
Specific config for creating an item at item service

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `name` | `string` | factory name |
| `action` | `string` | action to be done for creating an item |

**Example**
```
{
  "createExceptions":
    [
      {
        "name": "WorkOrderFactory",
        "action": "Create"
      }
    ]
}
```
### Collection Config
Specific config for getting collections at item service

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `outcomeName` | `string` | outcome name used for specific collection config |
| `collection` | `string` | domain name of the collection |
| `collectionName` | `string` | specific member name of the collection |

**Example**
```
{
  "collectionExceptions": [
      {
        "outcomeName": "WorkOrder_Details",
        "collection": "Product",
        "collectionName": "Components"
      }
    ]
}
```