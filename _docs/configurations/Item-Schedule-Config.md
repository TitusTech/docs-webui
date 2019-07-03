---
title: Item Schedule Config
permalink: /docs-webui/docs/configurations/Item-Schedule-Config/
---

### Config File

`src/data/itemScheduleExceptions.json`

### Format
```
{
  "calendarEventExceptions" :
    [
      "name": string,
      "exception": {
        "name": string,
        "path": string,
        "param": string
      },
      "title": string,
      "username": string,
      "additional": {
        "name": string,
        "collection": string,
        "type": string
      }
   ],
  "redirectRoutes" :
    [
      {
        "name": string,
        "path": string
      }
   ]
}
```
### Calendar Events Config

Config where to get calendar events

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `name` | `string` | Calendar event name |
| `exception` | `string` | Where to get the events data. `default is null, null = calendarEvents` |
| `title?` | `string` | Title of Calendar Event |
| `username?` | `string` | Username to be used in redirection of event |
| `additional` | `string` | Additional Events from specific config/path `default is null. If exception is not null, additional is required` |

`? = optional fields`

### Example
```
{
  "calendarEventExceptions" :
    [
      {
      "name": "Department",
      "exception": {
        "name": "Employee",
        "path": "/hmws/employees",
        "param": "Department"
      },
      "title": "FullName",
      "username": "UserName",
      "additional": {
        "name": "Shifts",
        "collection": "Shift",
        "type": "employee"
      }
    }
   ]
}
```
### Redirect Routes Config

Config for redirection of event at calendar

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `name` | `string` | event type |
| `path` | `string` | path to redirected |

### Example
```
{
  "redirectRoutes" :
    [
      {
        "name": "employee",
        "path": "/hmws/employees"
      }
   ]
}
```