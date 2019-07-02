---
title: Guards
permalink: /docs/Guards/
---

### Functionality description for the following:
The main function of guard components are to provide restrictions in routing level of the WebUI.

1. authorisation.guard
   * Checks if the user has successfully logged-in and is accessing a path inside the WebUI application.
1. * cristalDetailsguard
   Checks if the user can turn-on cristal details.
1. form-deactivate.guard
   * When components ItemListComponent, ItemDetailsComponent or ItemTreeComponent is deactivated then this component displays a confirmation message to discard changes in the form or not.