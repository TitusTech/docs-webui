---
title: Global-Setting-Configuration
permalink: /docs/configurations/Global-Setting-Configuration/
---

# Global Setting Configuration
`src/environments/environment.prod.ts`
`src/environments/environment.ts`

# Format
```
  production: false,
  serverBaseUrl: '',
  debug: false,
  cristalDetailsOn: false,
  viewPointDetailsOn: false,
  showExport: true,
  showDynamicButtons: false,
  showRadioButton: true,
  manuallyAppendAutoCompleteLabel: true,
  clearParamsUponSearch: true,
  project: 'hmws',
  barcodeDelimiter: '<BC>',
  superUsers: [
    'kevin',
    'ramir',
    'isa',
    'ronnie',
    'russ'
  ],
  columnDataToHyperLink: [
    'Name',
    'ID',
    'Username',
    'Item Code',
    'PO',
    'Invoice Number'
],
  reportingDBItems: [
    'Batch',
    'Site',
    'Product',
    'Device',
    'Equipment',
    'ProductionLine',
  ],
  reportingDBCollections: [
    'Equipments',
    'NonMandatoryDevices',
    'Products',
    'Sites',
    'Batches'
  ]

```
# Configuration
| Config Name | Type | Description |
| ------------- | ------------- | ------------- |
|production|boolean|If true then the build will be package for production.|
|serverBaseUrl|string|Returns the base url of the application|
|debug|boolean|If true then a debug panel will be shown in html|
|cristalDetailsOn|boolean|If true then item's UUID and properties will be displayed in details page|
|showExport|boolean|If true then export button will be shown in the toolbar of the item list|
|showDynamicButtons|boolean|If true then dynamic buttons with its activity names will be shown in the toolbar|
|showRadioButton|boolean||
|manuallyAppendAutoCompleteLabel|boolean||
|clearParamsUponSearch|boolean|If true then it will reset the filter to empty in every search to reporting database|
|project|string|provides project name information|
|barcodeDelimiter|string|This is used to format the barcode value and remove the delimiters|
|superUsers|string array||
|columnDataToHyperLink|string array||
|reportingDBItems|string array|List of item names that will use Reporting DB on the item list's table|
|reportingDBCollections|string array|List of collection names that will use Reporting DB on the item collections's table|
