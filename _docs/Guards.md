---
title: Guards
permalink: /docs/Guards/
---

The main function of guard components are to provide restrictions in routing level of the WebUI.

Functionality description for the following:

| Component File | Description |
| ------------- | ------------- |
| authorisation.guard | Checks if the user has successfully logged-in and is accessing a path inside the WebUI application. |
| cristalDetails.guard | Checks if the user can turn-on cristal details. |
| form-deactivate.guard | When components ItemListComponent, ItemDetailsComponent or ItemTreeComponent is deactivated then this component displays a confirmation message to discard changes in the form or not. |