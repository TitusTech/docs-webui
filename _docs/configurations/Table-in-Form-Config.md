---
title: Table in Form Config
permalink: /docs/configurations/Table-in-Form-Config/
---

### Config File
`src/data/${ItemType}/${TableName}TableInForm.json`

### Example
```
{
  "caption":"Products",
  "sortMode":"multiple",
  "sortField":"Product",
  "sortOrder":1,
  "sortFields":[
      {"field":"Product", "order":1},
      {"field":"RequisitionID", "order":1}
  ],
  "columns": [
      {"name": "Product", "width": 28, "sortableColumnDisabled":true},
      {"name": "RequisitionID", "width": 0},
      {"name": "RequiredQuantity", "width": 13},
      {
        "name": "PickedQuantity", 
        "width": 13,
        "style": {
           "textAlign": "right"
        },
        "keyUpFormula": "element.style.backgroundColor = rowData['MissingQuantity'] == 0 ? '' : '#ffff66'",
        "blurFormula": "rowData['RequiredQuantity'] = parseFloat(rowData['RequiredQuantity']).toFixed(3)",
        "initFormula": "row[element.field + 'style'].backgroundColor = parseFloat(rowData['MissingQuantity']) == 0 ? '' : '#ffff66';"
      },
      {"name": "MissingQuantity", "width": 13},
      {
        "name": "ETA", 
        "width": 13,
        "blurFormula": "element.style.backgroundColor = rowData['ETA'] ? '' : '#ffff66'",
        "onSelectFormula": "element.style.backgroundColor = rowData['ETA'] ? '' : '#ffff66'",
      },
      {"name": "UOM", "width": 10}
  ],
  "disableAddRemoveRow": true
}

```
### Caption
**Config for caption**

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `caption?` | `string` | customized title of the table |

### Columns Sorting
**Config for Add Row and Remove Row buttons**

| Field | Type | Meaning | 
| ------------- | ------------- | ------------- |
| `sortMode` | `string` | Options are "single" and "multiple". "single" sort is done by single column only while "multiple" can sort the table using multiple columns. |
| `sortField?` | `string` | Enter sortField if sortMode is "single". This is the name of the field or column that can be sorted on initial load of the table. |
| `sortOrder?` | `number` | Enter sortOrder if there is a sortField and sortMode is "single". Options are 1 for ascending order and -1 for descending.|
| `sortFields?` | `array of fields` | List the fields if sortMode is "multiple". These are the fields or columns that will be used to sort the table. |

### SortFields
**Config for sortFields**

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `field` | `string` | This is the name of the field or column that can be sorted. |
| `order` | `string` | Options are 1 for ascending order or -1 for descending. |

### Column
**Config for columns**

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `name` | `string` | field name of the column |
| `width` | `integer` | width(percentage) of the column |
| `style?` | `object` | css style format of the column |
| `keyUpFormula?` | string | A Javascript expression that is being evaluated for every `keyUp` field event.<br/><br/>List of variables that can be used inside the `keyUpFormula` property: <br/><ul><li>`field` - Contains the column field name</li><li>`rowIndex` - Contains the current row index</li><li>`element` - Contains the HTML element of the table cell</li><li>`inputElement` - Contains the HTML element of the input field</li></ul> |
| `blurFormula?` | string | A Javascript expression that is being evaluated in every `onBlur` field event.<br/><br/>List of variables that can be used inside the `blurFormula` property: <br/><ul><li>`field` - Contains the column field name</li><li>`rowIndex` - Contains the current row index</li><li>`element` - Contains the HTML element of the table cell</li><li>`inputElement` - Contains the HTML element of the input field</li></ul> |
| `onSelectFormula?` | string | A Javascript expression that is being evaluated in every `OnSelect` field event.<br/><br/>List of variables that can be used inside the `OnSelect` property: <br/><ul><li>`index` - Contains the current row index</li><li>`element` - An Object that holds the configuration of the column element</li><li>`rowData` - Contains the data of the row</li><li>`row` - An Object that will be used when creating the table</li></ul> |
| `initFormula?` | string | A Javascript expression that is being evaluated before creating the table.<br/><br/>List of variables that can be used inside the `initFormula` property: <br/><ul><li>`index` - Contains the current row index</li><li>`element` - An Object that holds the configuration of the column element</li><li>`rowData` - Contains the data of the row</li><li>`row` - An Object that will be used when creating the table</li></ul> |
| `sortableColumnDisabled?` | `boolean` | If set to true then enable the sorting in the particular column |

### Add Row and Remove Row buttons
**Config for Add Row and Remove Row buttons**

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `disableAddRemoveRow` | `boolean` | set as `true` if you want to disable add and remove buttons |

? = optional fields

`columns` is an ordered list containing the fields of the table-in-form

if not specified, `textAlign` (under the `style` property) default value is 'left'

the sum of all the `width` should be equal to 100
