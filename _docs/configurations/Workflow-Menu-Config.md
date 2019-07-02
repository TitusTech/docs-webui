---
title: Workflow-Menu-Config
permalink: /docs/configurations/Workflow-Menu-Config/
---

# Config File

`src/data/workflowMenu.json`

# Format
```
{
  "column" :
    [
      { 
        "label": string,
        "icon": string, 
        "routerLink": string[ ] 
      }
    ]
}
```
# Workflow Menu

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `label` | `string` | Label of the menu |
| `icon` | `string` | icon of the menu (font awesome) |
| `routerLink` | `string [ ]` | path of the menu |

**Example**
```
{
  "column" :
    [
      { 
        "label": "Products",
        "icon": "fa-usb", 
        "routerLink": ["/hmws/products"] 
      }
    ]
}
```