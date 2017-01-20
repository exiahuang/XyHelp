# SalesforceXyTools

  * [SalesforceXyTools Introduce](http://www.ibmer.info/salesforcexytools.html)
  * [SalesforceXyTools Install](http://www.ibmer.info/salesforcexytools-install.html)
  * [SalesforceXyTools Auto Create VF-Controller-DTO-DAO-Code](http://www.ibmer.info/auto-create-sfdc-code.html)
  * [SalesforceXyTools: Export Sobject To Excel](http://www.ibmer.info/export-sobject-excel.html)
  * [SalesforceXyTools Sublime Package](https://packagecontrol.io/packages/SalesforceXyTools)

## Auto Create VF-Controller-DTO-DAO-Code
Hello,I am Exia.huang.
Today I will show you how to create VisualForce/Apex quickly by using SalesforceXyTools.

## There are 5 steps.
1. Find the menu below.
  [SFDC-XY]->[SFDC Code Creator]->[Create VisualForce/Controller/DTO/DAO Code]
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/Auto%20Create%20VF-Controller-DTO-DAO-Code/SaleforceXyTools-Help000.jpg?raw=true)

2. Select your Sobject.
  I will select Blog__c.
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/Auto%20Create%20VF-Controller-DTO-DAO-Code/SaleforceXyTools-Help001.jpg?raw=true)

3. Select Custom Fields Or All Fields.
  * I will select custom fields-Include Validate.
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/Auto%20Create%20VF-Controller-DTO-DAO-Code/SaleforceXyTools-Help002.jpg?raw=true)

  * The sobject of Blog__c is as below:
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/Auto%20Create%20VF-Controller-DTO-DAO-Code/SaleforceXyTools-Help004.jpg?raw=true)

4. It will automatically create code like below
   ```
	+---sfdc-xy
	|   \---code-creator
	|           Blog.page
	|           BlogController.cls
	|           BlogDao.cls
	|           BlogDto.cls
	|           BlogList.page
	|           BlogListController.cls
	|           SfdcXyController.cls
  ```
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/Auto%20Create%20VF-Controller-DTO-DAO-Code/SaleforceXyTools-Help003.jpg?raw=true)

  
5. Upload these code and enjoy yourself.
   ```
   https://ap2.salesforce.com/apex/BlogList
   https://ap2.salesforce.com/apex/Blog
   ```
  * Edit list of Blog__c.(Source code is BlogList.page.)
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/Auto%20Create%20VF-Controller-DTO-DAO-Code/SaleforceXyTools-Help005.jpg?raw=true)
  
  * View list of Blog__c.(Source code is BlogList.page.)
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/Auto%20Create%20VF-Controller-DTO-DAO-Code/SaleforceXyTools-Help006.jpg?raw=true)
  
  * Search Blog__c Data.(Source code is BlogList.page.)
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/Auto%20Create%20VF-Controller-DTO-DAO-Code/SaleforceXyTools-Help007.jpg?raw=true)
  
  * New a Blog__c Data.(Source code is Blog.page.)
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/Auto%20Create%20VF-Controller-DTO-DAO-Code/SaleforceXyTools-Help008.jpg?raw=true)
  
  * New a Blog__c Data.(Source code is Blog.page.)
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/Auto%20Create%20VF-Controller-DTO-DAO-Code/SaleforceXyTools-Help009.jpg?raw=true)
  
  * Edit a Blog__c Data.(Source code is Blog.page.)
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/Auto%20Create%20VF-Controller-DTO-DAO-Code/SaleforceXyTools-Help010.jpg?raw=true)
