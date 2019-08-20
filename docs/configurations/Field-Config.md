---
title: Field Config
permalink: /docs/configurations/Field-Config/
---

### Config File
`src/data/${ItemType}/itemCollection${CollectionName}.json`

`src/data/${ItemType}/masterOutcomeView.json`

`src/data/${ItemType}/itemList.json`

### Example
```
{"column": [
    {"source": "itemField", "field": "RadioButtonWithFileInvoice", "width": 60, "configurable": true, "icon": "fa fa-file-invoice" },
    {"source": "itemField", "field": "Name", "caption": "ID", "align": "left", "formula": "(value.content === 'no name') ? '' : value.content" },
    {"source": "itemField", "field": "Description", "caption": "Description", "align": "left", "formula": "(value.content === 'N/A') ? '' : value.content" },
    {"source": "itemField", "field": "Url", "caption": "URL", "align": "left", "formula": "(value.content === '') ? 'No URL available' : value.content" },
    {"source": "itemField", "field": "FromDate", "caption": "From Date", "align": "center", "format": "dateTime" },
    {"source": "itemField", "field": "ThruDate", "caption": "Thru Date", "align": "center", "format": "dateTime" },
    {"source": "itemField", "field": "Duration", "caption": "Duration", "align": "center", "format": "timeSpan minutes hours:minutes:seconds plain" },
    {"source": "itemField", "field": "AllDay", "caption": "AllDay", "align": "center", "format": "boolean", "type": "checkBox" },
    {"source": "itemField", "field": "Progress", "caption": "Progress", "align": "center", "type": "ProgressBar"},
    {"source": "itemField", "field": "State", "caption": "State", "align": "center", "icon": "iconSets" },
    {"source": "itemField", "field": "Grade", "caption": "Grade", "align": "center", "icon": "fa-square" }
  ],
  "sort": {"field": "Name" , "order": "asc" }
}
```
### Field descriptions

#### `source`

| Value | Meaning |
| ------------- | ------------- |
| itemField | `field` is a field of the master outcome of the item |
| itemProperty | `field` is a property of the item (property values can be read by querying the summary) - NOT IMPLEMENTED YET |
| `memberField` | `field` is a field of the collection member |
| `memberProperty` | `field` is a property of the collection member |
| `width` | is the width of the `field`  |
| `configurable` | is the parameter for checking if the `field` can be queried by the `ReportingDB` and if the column is configurable in the environments file  |

* For details see issue [#122 Collection item lists configurable](https://github.com/kovax/webui-primeng/issues/122)

#### `format`

| Value | Meaning |
| ------------- | ------------- |
| `boolean` | value will be formatted as `Yes/No` |
| `substr i j` | substring starting from position i (0-based) to position j-1 (for example `substr 0 5` means the first 5 characters, so positions 0-4) |
| `dateTime` | value will be formatted as `2018-05-23 00:00:00` |
| `dateFormat YYYY-MM-DD HH:mm` | value will be formatted according to the format string |
| `commaSpace` | Value will be formatted to a space following a comma (ex: "A,B,C" to "A, B, C") |
| `multilineFormat` | For lines with \n just add css class multilineFormat which replaces \n to line breaks |
| `decimal {scale}` | The value will be displayed with exactly `{scale}` decimal places. For example if we have `format='decimal 2'`, the value will be formatted to 2 decimal places |
| `timeSpan {fromFormat} {toFormat} {suffix}` | The time value will be displayed and formatted to the specified format with the specified suffix (e.x Time to transform = 42.25, `timeSpan minutes hours:minutes:seconds plain` will output `42m15s`) Where the arguments defined to format the value are: <br>1. `{fromFormat}`: The original format of the time (`minutes` or `seconds`)<br> 2. `{toFormat}`: The output format of the time to be transformed with the pattern: `unitOfTime:unitOfTime:unitOfTime` (e,x `hours:minutes:seconds`), where `unitOfTime` is the unit of time in plural <br> 3. `{suffix}`: An optional parameter, the suffix for every `unitOfTime` which can either be `simple` or `APA`. The `simple` suffix will append `h`, `m`, or `s` to the appropriate `unitOfTime` while `APA` will append APA standard references (`hr`, `min`, `sec`) to the `unitOfTime`. If no suffix was specified, the default suffix '`:`' will be appended instead.<br><br> The string `-spaced` can be appended to the suffix (e.x `plain-spaced` will yield to `42m 15s`) to include spaces between suffixes.

#### `formula`

* The value of this field is an expression that is evaluated in the item list to determine the value to be displayed.
* E.g. the expression `(value.content === 'none') ? '' : value.content` will display an empty string if the value of `value.content` is `none`. If not, the value of `value.content` will be displayed.

| Value | Meaning |
| ------------- | ------------- |
| `record` | the array that contains the retrieved records from the Reporting DB |
| `value` | a record that is processed on the iteration of the record variable |
| `value.field` | the field name of the data member of the value variable |
| `value.content` | the value of the data member of the value variable |

#### `icon`
| Value | Meaning |
| ------------- | ------------- |
| `fontawesome icon` | field renders an icon before value(ex. `fa-square`) |
| `iconSets` | field renders an icon based on the value [(Icon Sets Config)](https://github.com/TitusTech/webui-lib/wiki/Icon-Sets-Config) |


#### `type`
| Value | Meaning |
| ------------- | ------------- |
| `checkBox` | field is shown as checkbox |
| `progressBar` | field is shown as progress bar |
