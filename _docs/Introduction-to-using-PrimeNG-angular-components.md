---
title: Introduction to using PrimeNG’s angular components
permalink: /docs/Introduction-to-using-PrimeNG-angular-components/
---

PrimeNG is a rich set of open source native Angular UI components.
### Download

PrimeNG is available at npm, if you have an existing application run the following command to download it to your project.


npm install primeng --save

npm install primeicons --save

### Load Configuration

PrimeNG is distributed in commonjs format, a module manager of your choice is required and this guide provides samples for SystemJS, WebPack and Angular CLI.
### Import

UI components are configured as modules, once PrimeNG is downloaded and configured, modules and apis can be imported from 'primeng/*' shorthand in your application code. Documentation of each component states the import path.


import {AccordionModule} from 'primeng/accordion';     //accordion and accordion tab
import {MenuItem} from 'primeng/api';                 //api


### Additional Information on Components

https://www.primefaces.org/primeng/#/