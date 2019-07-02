---
title: Global-Setting-Service
permalink: /docs/Global-Setting-Service/
---

# Global Setting Service
`src/lib/service/global-settings.service.ts`

# Public Method of Global Setting Service

Method

| Method | Returned Type | Description |
| ------------- | ------------- | ------------- |
| debugOn(compName?: string) | boolean| If true then a debug panel will be shown in html |
| isCristalDetailsOn() |boolean| If true then item's UUID and properties will be displayed in details page. |
| getDomainRootForMenu() |string| unused |
| getServiceBaseURL() |string| Returns the base url of the application |
| isViewPointDisplayOn() |boolean | If true then viewpoints panel will be displayed in details page. |
| showExport() |boolean| If true then export button will be shown in the toolbar of the item list. |
| showDynamicButtons() |boolean| If true then dynamic buttons with its activity names will be shown in the toolbar. |
| showRadioButton |boolean||
| getProject() |string| provides project name information |
| isUsingReportingDB() |boolean| If true then it will sync the data with the existing reporting database |
| getSuperUsers() |string[]||
| getBarcodeDelimiter() |string| This is used to format the barcode value and remove the delimiters |
| getColumnDataToHyperLink() |string[]| |
| manuallyAppendAutoCompleteLabel() |boolean||
| convertTimezone() |boolean| If true then the form date field will be converted to timezone. |
| clearParamsUponSearch() |boolean| If true then it will reset the filter to empty in every search to reporting database |
| defaultDateFormat() |string| Returns the default date format for date field in the form.|
