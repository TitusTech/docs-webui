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
  },
  "Button": [{
      "label": string,
      "icon": string,
      "iconColor": string,
      "activityName": string,
      "actsOnSelected": boolean,
      "hiddenWhen": string,
      "subButtons": [{
        "label": string,
        "icon": string,
        "activityName": string,
        "actsOnSelected": boolean
      }, {
        "label": string,
        "icon": string,
        "activityName": string,
        "actsOnSelected": boolean
      }]
    }, {
      "label": string,
      "icon": string,
      "iconColor": string,
      "activityName": string,
      "actsOnSelected": boolean,
      "runScript": boolean,
      "scriptName": string,
      "message": string,
      "hiddenWhen": string
    }]
}

```
### NoForms

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `delete` | `string[]` | Activity names that will trigger the Delete Dialog |
| `confirm` | `string[]` | Activity names that will trigger the Confirm Dialog |

### Button 

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `label` | `string` | Button's label |
| `icon` | `string` | Icon in the button using fontawesome. Please see [fontawesome](https://fontawesome.com/icons)|
| `iconColor` | `string` | Color of button's icon |
| `activityName` | `string` | Assigned activity in the button |
| `actsOnSelected` | `boolean` | |
| `hiddenWhen` | `string` | This expression is evaluated during runtime. Depends when the expression returns true then the button is hidden otherwise the button remains visible. |
| `runScript` | `boolen` | When true then a script will run when the button is clicked. |
| `scriptName` | `string` | The name of the script to run when runScript is true. |
| `message` | `string` | |
| `subButtons` |  | Sub-buttons have same properties as the Button|


**Example**
```
{
  "noForms": {
    "delete": ["Deactivate", "RemoveMember", "RemoveEvent", "RemoveAddress", "RemovePurchaseOrderRow"],
    "confirm": ["CUTTING LIST", "BOM", "ASSEMBLY BOARD DRAWING", "SPLICE DRAWINGS", "WorkOrderParts_Finalize"]
  },
 "Button": [{
      "label": "Timekeeping",
            "icon": "fa-clock",
      "iconColor": "icon-black button-group-right ",
      "activityName": "New",
      "actsOnSelected": false,
      "hiddenWhen": "jobActivityNameArray.includes( 'DONE' ) || jobActivityNameArray.includes( 'Finalize' ) || jobActivityNameArray.includes( 'WorkOrderParts_Finalize' ) || (outcomeData.WorkOrder.State === 'DEACTIVATED')",
      "subButtons": [{
        "label": "Start Time",
        "icon": "fa fa-play icon-green",
        "activityName": "WorkOrder_StartTimeEmployee",
        "actsOnSelected": true
      }, {
        "label": "End Time",
        "icon": "fa fa-square icon-red",
        "activityName": "WorkOrder_EndTimeEmployee",
        "actsOnSelected": true
      }]
    }, {
      "label": "Print Non-Prod WO",
      "icon": "fa-print",
      "iconColor": "icon-black split-button-div button-group-right",
      "activityName": "NonProdWorkOrder_Print",
      "actsOnSelected": false,
      "runScript": true,
      "scriptName": "NonProdWorkOrder_Print",
      "message": "Printing Non-Productive WorkOrders...",
      "hiddenWhen": "!superUsers.includes(loggedInUser) || jobActivityNameArray.length !== 0"
    }]  
}
```