---
title: Item Toolbar Config
permalink: /docs/configurations/Item-Toolbar-Config/
---

### Config File
`src/data/ItemToolbarConfig.json`

### Format
```
{
  "noForms": {
    "delete": string[],
    "confirm": string[]
  }
}

```
### noForms
This config renders dialog boxes instead of side-bar forms for schema-less activities.

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `delete` | `string[]` | Activity names that will trigger the Delete Dialog |
| `confirm` | `JSON[]` | List of activity names with special properties that will trigger the Confirm Dialog |

## confirm field properties
Activities included in the `confirm` field with the same name, but in different indexes, will be evaluated from top to bottom. If the first activity found did not meet the condition, the next activity will be evaluated and so on and so forth until there are no activities with the same name is left.
| Property | Type | Meaning |
| ------------- | ------------- | ------------- |
| `activities` | `string[]` | Activity names that will trigger the Confirm Dialog when the `condition` property is truthy |
| `additionalButtons?` | `JSON[] | undefined` | Additional button to add in the Confirm Dialog; triggers transitions based on name and ID |
| `condition?` | `string | undefined` | An expression that will be evaluated (must be truthy) to determine when the activity will be assessed as schema-less |


## additionalButtons field properties
NOTE: Yes and No buttons for the dialog are hard coded and will always be present.
| Property | Type | Meaning |
| ------------- | ------------- | ------------- |
| `label` | `string` | Label of the additional dialog button |
| `icon` | `string` | Fontawesome icon of the button |
| `transitionName` | `string` | Transition name of the button that will be executed on click event |
| `transitionID` | `number` | ID of the transition |

**Basic Example**
```
{
  "noForms": {
    "delete": [ "Deactivate", "RemoveMember", "RemoveEvent" ],
    "confirm": [
      {
        "activities": [ "PAINTING" ],
        "additionalButtons": [
          { "label": "Skip", "icon": "fa fa-fast-forward", "transitionName": "Skip", "transitionID": 1 }
        ],
        "condition": "job.activity.name === 'Mask_CreationWorkflow'"
      },
      {
        "activities": [
          "PLASTER MOLDING",
          "CLAY MOLDING",
          "BUST MOLDING",
          "RETOUCHING"
        ]
      }
    ]
  },
}
```

**Activities with same name Example**
`Given:` job.activity.name = 'Furniture_CreationWorkflow'
```
{
  "noForms": {
    "delete": [ "Deactivate", "RemoveMember", "RemoveEvent" ],
    "confirm": [
      {
        "activities": [ "PAINTING" ],
        "additionalButtons": [
          { "label": "Skip", "icon": "fa fa-fast-forward", "transitionName": "Skip", "transitionID": 1 }
        ],
        "condition": "job.activity.name === 'Mask_CreationWorkflow'"
      },
      {
        "activities": [ "PAINTING" ],
        "additionalButtons": [
          { "label": "Skip", "icon": "fa fa-fast-forward", "transitionName": "Skip", "transitionID": 1 }
        ],
        "condition": "job.activity.name === 'Statue_CreationWorkflow'"
      },
            {
        "activities": [ "PAINTING" ],
        "additionalButtons": [
          { "label": "Skip", "icon": "fa fa-fast-forward", "transitionName": "Skip", "transitionID": 1 }
        ],
        "condition": "job.activity.name === 'Toy_CreationWorkflow'"
      },
      {
        "activities": [
          "PLASTER MOLDING",
          "CLAY MOLDING",
          "BUST MOLDING",
          "RETOUCHING",
          "PAINTING"
        ]
      }
    ]
  },
}
```
`Result:` A dialog box without any additional button will be displayed