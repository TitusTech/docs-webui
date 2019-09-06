---
title: Root Menu Config
permalink: /docs/configurations/Root-Menu-Config/
---

### Config File

`src/data/MenuConfigurations/rootMenu.json`

### Format
```
{
  "row" :
    [
      { 
        "label": string,
        "icon": string, 
        "routerLink": string[ ],
        "command"?: boolean,
        "items"?: string,
        "roles"?: string | string[]
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
| `command` | `boolean | null` | the function to execute when an event is applied to the menu item |
| `items` | `string | null` | submenu items name |
| `roles` | `string | string[] | null` | agent roles who can view the menu; default is everyone

**Examples**
```
{
  "row" :
    [
      { 
        "label": "Organization Chart",
        "icon": "fa-sitemap", 
        "routerLink": ["/orgchart"] 
      }
    ]
}
```
```
{
  "row" :
    [
      { 
        "label": "Reports",
        "icon": "fa fa-file-signature", 
        "routerLink": ["/reports"],
        "command": (ev) => this.clearBreadCrumbs,
        "items": reportsMenu
        "roles": ["Admin", "manager"]
      }
    ]
}
```