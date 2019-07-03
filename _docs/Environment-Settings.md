---
title: Environment Settings
permalink: /docs/Environment-Settings/
---

`src/environments/environment.ts`

### Sample Environment Settings
```
export const environment = {
  production: true,
  version: '0.0.0',
  serverBaseUrl: '',
  showExport: true,
  project: 'hmws',
  useReportingDB: true,
  showRadioButton: true,
  manuallyAppendAutoCompleteLabel:true,
  clearParamsUponSearch: true,
  barcodeDelimiter: '<BC>',
  superUsers: [
    'user1',
    'user2'
  ],
  columnDataToHyperLink: [
    'Name',
    'ID',
    'Username',
    'Item Code',
    'PO',
    'Invoice Number'
  ]
};
```