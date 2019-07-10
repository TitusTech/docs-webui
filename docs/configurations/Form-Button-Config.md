---
title: Form Button Config
permalink: /docs/configurations/Form-Button-Config/
---

For more info see https://github.com/TitusTech/webui-lib/issues/486

### Config File
`src/data/<item>/formButtons.json`

### Format
```
{
  "Activities": [
    {
      "name": "",
      "NumberOfButtonsPerRow": 0,
      "Buttons": [
        {
          "label": "",
          "icon": "",
          "iconColor": "",
          "defaultAction": ,
          "transition": "",
          "condition": ""
        },
        {
          "label": "OK",
          "icon": "fa-check",
          "iconColor": "green",
          "defaultAction": true,
          "condition": "selectedData.Flow === 'PRO2'"
        }
      ]
    }
  ]
}

```
### Button Configurations

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `name` | `string` | Activity name |
| `NumberOfButtonsPerRow` | `number` | Number of buttons in a row this include the permanent "Dismiss" button |
| `label` | `string` | Label name of the button |
| `icon` | `string` | Icon name. Please refer to fontawesome https://fontawesome.com/icons?d=gallery |
| `iconColor` | `string` | Color of the icon. Currently not functioning. |
| `defaultAction` | `boolean` | If set to "true" then it will trigger the default onSubmit action |
| `transition` | `string` | Activity Transition name |
| `condition` | `string` | Condition if the button should appear. Defaults to true if not specified.

Please note that always add the "OK" button in the list of buttons because this will always be present in the form.

**Example**
```
{
  "Activities": [
    {
      "name": "Batch_Irradiation",
      "NumberOfButtonsPerRow": 3,
      "Buttons": [
        {
          "label": "Finalize",
          "icon": "fa-stamp",
          "iconColor": "green",
          "defaultAction": false,
          "transition": "Finalize"
        },
        {
          "label": "OK",
          "icon": "fa-check",
          "iconColor": "green",
          "defaultAction": true
        }
      ]
    }
  ]
}
```