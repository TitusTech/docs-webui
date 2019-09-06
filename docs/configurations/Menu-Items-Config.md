---
title: Menu Items Config
permalink: /docs/configurations/Menu-Items-Config/
---

### Config File

`src/data/MenuConfigurations/{items}.json`

### Format
```
{
  "{items}" :
    [
      { 
        "label": string,
        "icon": string, 
        "routerLink": string[ ],
        "roles"?: string | string[]
      }
    ]
}
```
### Workflow Menu

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `label` | `string` | Label of the menu |
| `icon` | `string` | icon of the menu (font awesome) |
| `routerLink` | `string [ ]` | path of the menu |
| `roles` | `string | string [] | null` | agent roles who can view the submenu item; default is everyone |

### {items}
See /docs/configurations/Root-Menu-Config/

**Examples**
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

```
{
  "column" :
    [
      { 
        "label": "Electronics",
        "icon": "fa-usb", 
        "routerLink": ["/electronics"],
        "roles": "manager"
      }
    ]
}
```