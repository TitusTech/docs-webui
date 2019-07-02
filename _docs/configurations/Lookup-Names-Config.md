---
title: Lookup-Names-Config
permalink: /docs/configurations/Lookup-Names-Config/
---

# Config File

`src/data/lookupNames.json`

# Format
```
{
  "column" :
    [
      {
        "itemType": string,
        "factory": string,
        "domain": string,
        "collection": string,
        "lowSing": string,
        "lowPlur": string,
        "upSing": string,
        "upPlur": string,
        "title": string
      }
   ]
}
```
# Lookup Name
**Config for lookup names**

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `itemType?` | `string` | item type of data |
| `factory?` | `string` | factory name of data |
| `domain` | `string` | domain path of the data |
| `collection` | `string` | members name |
| `lowSing` | `string` | lowercase and singular format of item type |
| `lowPlur` | `string` | lowercase and plural format of item type |
| `upSing` | `string` | capitalized first letter per word and singular format of item type |
| `upPlur` | `string` | capitalized first letter per word and plural format of item type |
| `title?` | `string` | job form title for the item |

`? = optional fields`

**Example**
```
{
  "column" :
    [
      {
        "itemType": "Product",
        "factory": "ProductFactory",
        "domain": "/hmws/products",
        "collection": "Components",
        "lowSing": "product",
        "lowPlur": "products",
        "upSing": "Product",
        "upPlur": "Products",
        "title": "Product's Customized Title For The Form"
      }
   ]
}
```