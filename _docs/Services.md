---
title: Services
permalink: /docs/Services/
---

### Functionality description for the following services: 
1. authentication-interceptor.service
    * Intercepts HttpRequest and check authentication. Redirect to login page if HttpResponse contains errors 401 or 504
1. authorisation.service
   * Handles login authorization.
1. breadcrumbs.service
   * Handles breadcrumbs. Push or removes breadcrumbs.
1. domain-path.service
   * Keeps track of domain path
1. form-edit.service
   * Keeps track of the boolean value that tells if the current form is edited or not.
1. form-save.service
   * Emits event when saving a form. Those components and services listening to that event will be triggered.
1. global-settings.service	
   * Handles global settings of the WebUI. This is mostly like a switch turning on/off some of the features like debugging options, dynamic buttons, export buttons, details view, view points as well as getting values of project environment and base url.
1. item-name-lookup.service
   
1. item.service
   * Gets data and related information related to an item. Also perform creation of an item in Cristal.
1. lookup.service
   * Performs item search in a domain
1. menu-items.service
   * Retrieves activities from a workflow and handles tracking of activity. If an activity has previously been selected then it will be removed from the menu of activities.
1. notification.service
   * Handles HttpErrorResponse and creates error messages.
1. resource.service
   * Retrieves schema related information, Schema Form Template and Schema View Template
1. schedule-settings.service
1. ui-config.service
   * Provides necessary UI configuration in the form of json returned from rest api that will be used another service or components.
1. util.service
   * Common services like setting of headers in the request.

### Discussion on pipes

Every application starts out with what seems like a simple task: get data, transform them, and show them to users. Getting data could be as simple as creating a local variable or as complex as streaming data over a WebSocket.

Once data arrives, you could push their raw toString values directly to the view, but that rarely makes for a good user experience. For example, in most use cases, users prefer to see a date in a simple format like April 15, 1988 rather than the raw string format Fri Apr 15 1988 00:00:00 GMT-0700 (Pacific Daylight Time).

Clearly, some values benefit from a bit of editing. You may notice that you desire many of the same transformations repeatedly, both within and across many applications. You can almost think of them as styles. In fact, you might like to apply them in your HTML templates as you do styles.

Introducing Angular pipes, a way to write display-value transformations that you can declare in your HTML.

Example:
### ui-config.service.ts
`
		if ( ! format ) {
		  return value;
		}
	 
		const firstSpace = format.indexOf(' ');
		switch (firstSpace > -1 ? format.substr(0, firstSpace) : format) {
		  case 'dateTime':
			return moment(value).format('YYYY-MM-DD HH:mm:ss');
		  case 'dateFormat':
			return moment(value).format(format.substr(firstSpace + 1));
		  case 'dateOnly':
		  return moment(value).format('YYYY-MM-DD');
		  case 'substr':
			const secondSpace = format.indexOf(' ', firstSpace + 1);
			return secondSpace > -1
			  ? value.substr(format.substr(firstSpace + 1, secondSpace), format.substr(secondSpace + 1))
			  : value.substr(format.substr(firstSpace + 1));
		  case 'boolean':
			return value ? 'Yes' : 'No';
		  case 'commaSpace':
			return value.replace(/,/g, ', ');
		  default:
			return value;
		}
	  }
	 
	}
`