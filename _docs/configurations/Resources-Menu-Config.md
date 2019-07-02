---
title: Resources Menu Config
permalink: /docs/configurations/Resources-Menu-Config/
---

### Config File

`src/data/resourcesMenu.json`

### Format
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
### Resource Menu
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
        "label": "Organization Chart",
        "icon": "fa-sitemap", 
        "routerLink": ["/orgchart"] 
      }
    ]
}
```