---
title: Error Handling
permalink: /docs-webui/docs/Error-Handling/
---

### Specific Error Messages
Specific error messages can be returned by the groovy script attached to the activity by putting the error message between `[errorMessage]` and `[/errorMessage]` tags, like this:

> `throw new InvalidDataException("[errorMessage]Cannot allocate to a Finalized WorkOrder[/errorMessage]")`

(from the class : import org.cristalise.kernel.common.InvalidDataException)

The error message will be shown at the top of the form and the activity cannot be executed (the form cannot be saved) until the error is fixed.

### Config
For this to work, your `local.clc` file for the rest server (located at `restAPI/src/main/conf/local.clc`) should contain:
> `REST.Debug.errorsWithBody=true`

### Confirmation Messages
...to be described...
