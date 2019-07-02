---
title: Creating Protractor Test
permalink: /docs/Creating-Protractor-Test/
---

Protractor is an end-to-end test framework for Angular and AngularJS applications. Protractor run

s tests against your application running in a real browser, interacting with it as a user would.
### Setup

Use npm to install Protractor globally with:

npm install -g protractor

This will install two command line tools, protractor and webdriver-manager. Try running protractor --version to make sure it's working.

The webdriver-manager is a helper tool to easily get an instance of a Selenium Server running. Use it to download the necessary binaries with:

webdriver-manager update



To execute the end to end testing:
npm e2e

### app.e2e-spec.ts
`			batch     = new Batch();
		  });
		 
		  describe('Creating a Batch ', () => {
			browser.ignoreSynchronization = true;
			it('should login successfully', () => {
			  login.navigateTo.then(() => {
				login.username.sendKeys('aaa'); 
				login.pwd.sendKeys('aaa'); 
				login.loginBtn.click(); 
			  });
			});   
		 
			it('should redirect to dashboard', () => {
				browser.wait(EC.visibilityOf(dashboard.dashboardText)).then(() => {
				  expect(dashboard.dashboardText.isPresent()).toBeTruthy();
				});
			});   
		 
			it('should create batch', () => {
			  batch.navigateTo.then(() => {
				browser.wait(EC.visibilityOf(batch.row));
				batch.row.click().then(() => {
				  browser.wait(EC.visibilityOf(batch.createNewBatchBtn)).then(() => {
					batch.createNewBatchBtn.click().then(() => {
					  browser.wait(EC.visibilityOf(batch.factoryHeader));
		   
					  browser.wait(EC.visibilityOf(batch.site)).then(() => {
						batch.site.click();
						browser.wait(EC.visibilityOf(batch.site.$('div.ng-trigger').$('div.ui-dropdown-filter-container input'))).then(() => {
						  batch.site.$('div.ng-trigger').$('div.ui-dropdown-filter-container input').sendKeys('Ivrea');
						  browser.wait(EC.visibilityOf(batch.site.$('li.ui-dropdown-item'))).then(() => {
							batch.site.$('li.ui-dropdown-item').click();
						  })
						})
					  })
		   
					  browser.wait(EC.visibilityOf(batch.product)).then(() => {
						batch.product.click();
						const product = batch.product.$('div.ui-dropdown div.ui-dropdown-panel div.ui-dropdown-items-wrapper ul.ui-dropdown-items');
						browser.wait(EC.visibilityOf(product)).then(() => {
						  product.element(by.cssContainingText('li.ui-dropdown-item > span','Lutathera')).click(); 
						});
					  });
		   
					  browser.wait(EC.visibilityOf(batch.productionLine)).then(() => {
						batch.productionLine.click();
						const productionLine = batch.productionLine.$('div.ui-dropdown div.ui-dropdown-panel div.ui-dropdown-items-wrapper ul.ui-dropdown-items');
						browser.wait(EC.visibilityOf(productionLine)).then(() => {
						  productionLine.element(by.cssContainingText('li.ui-dropdown-item > span','Line_2018-06-26_14-56-22')).click(); 
						});
					  });
		   
					  browser.wait(EC.visibilityOf(batch.batchId)).then(() => {
						batch.batchId.click();
						const batchId = batch.batchId.$('div.ui-dropdown div.ui-dropdown-panel div.ui-dropdown-items-wrapper ul.ui-dropdown-items');
						browser.wait(EC.visibilityOf(batchId)).then(() => {
						  batchId.element(by.cssContainingText('li.ui-dropdown-item > span','LT180903B-03 (9/3/2018)')).click();
						})
					  });
		 
					  browser.wait(EC.invisibilityOf(batch.batchId.$('div.ui-dropdown div.ui-dropdown-panel div.ui-dropdown-items-wrapper'))).then(() => {
						batch.okBtn.click();
					  })
					});
				  })
				});
			  })
			});
		  });
		});`

### Batch.po.ts
`'webuilib-uuid-link[ng-reflect-input="11111111"]'))
  }
 
  get createNewBatchBtn() {
    return element(by.id('CreateNewBatch'));
  }
 
  get factoryHeader(){
    return element(by.css('webuilib-item-job-form h2'));
  }
 
  get site() {
     return element(by.css('p-dropdown#Site'));
  }
 
  get finished() {
    return element(by.id('Finished'));
  }
 
  get product() {
    return element(by.css('p-dropdown#Product'));
  }
 
  get batchId() {
    return element(by.css('p-dropdown#Name'));
  }
 
  get productionLine() {
    return element(by.css('p-dropdown#ProductionLine'));
  }
 
  get okBtn() {
    return element(by.id('ok'));
  }
  
  get dismissBtn() {
    return element(by.id('dismiss'));
  }
 
  get formPanel() {
    return element(by.css('div.myFormScrollPanel'));
  }
}`

### Dashboard.po.ts
`import { browser, element, by} from 'protractor';
 
export class Dashboard {
 
  get navigateTo() {
    return browser.get('/#/dashboard');
  }
 
  get dashboardText() {
    return element(by.css('.ng-tns-c2-2 .ng-star-inserted .active-menuitem-routerlink > span'))
  }
}`

### Login.po.ts
`import { browser, element, by} from 'protractor';
 
export class Login {
 
  get navigateTo() {
    return browser.get('/#/login');
  }
 
  get username() {
    return element(by.id('agent'));
  }
 
  get pwd() {
    return element(by.id('pwd'));
  }
 
  get loginBtn() {
    return element(by.id('loginBtn'));
  }
}`