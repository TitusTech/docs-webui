---
title: Icon-Sets-Config
permalink: /docs/configurations/Icon-Sets-Config/
---

# Config File
`src/data/IconSets.json`

# Example
```
{
  "columns": [
      {
          "name" : "ACTIVE",
          "type" : "State",
          "icon" : "fa-play-circle",
          "color": "#0099FF"
      },
      {
          "name" : "DEACTIVATED",
          "type" : "State",
          "icon" : "fa-minus-circle",
          "color": "#E62E00"
      }
  ]
}

```
# Column
**Config for columns**

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `name` | `string` | Value of the field |
| `type` | `string` | Field name |
| `icon` | `string` | Icon to be shown |
| `color` | `string` | Color of the icon |
