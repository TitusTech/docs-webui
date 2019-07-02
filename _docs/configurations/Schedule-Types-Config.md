---
title: Schedule Types Config
permalink: /docs-webui/docs/configurations/Schedule-Types-Config/
---

### Config File

`src/data/scheduleTypes.json`

### Format
```
{
  "types" :
    [
      {
        "name": string,
        "label": string,
        "path": string
      }
   ],
  "schedules" :
    [
      {
        "name": string,
        "scheduleFor": string,
        "display": string,
        "textColor": string,
        "backgroundColor": string,
        "borderColor": string
      }
   ]
}
```
### Types Config
Kinds or Types of schedules

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `name` | `string` | type code or name |
| `label` | `string` | label or display name for type |
| `path?` | `string` | path where to get schedules |

`? = optional fields`

**Example**
```
{
  "types" :
    [
      {
        "name": "holiday",
        "scheduleFor": "employee",
        "display": "Public Holiday",
        "textColor": "#ffffff",
        "backgroundColor": "#008000",
        "borderColor": "#008000"
      }
   ]
}
```
### Schedules Config
Config for display of schedule calendar and settings

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `name` | `string` | schedule code or name |
| `scheduleFor` | `string` | schedule type |
| `display` | `string` | label for schedule type |
| `textColor` | `string` | hexcode color format for text |
| `backgroundColor` | `string` | hexcode color format for background |
| `borderColor` | `string` | hexcode color format for border |

**Example**
```
{
  "schedules" :
    [
      {
        "name": "holiday",
        "scheduleFor": "employee",
        "display": "Public Holiday",
        "textColor": "#ffffff",
        "backgroundColor": "#008000",
        "borderColor": "#008000"
      }
   ]
}
```