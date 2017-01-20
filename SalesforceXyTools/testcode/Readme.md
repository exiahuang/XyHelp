# SalesforceXyTools

  * [SalesforceXyTools Introduce](http://www.ibmer.info/salesforcexytools.html)
  * [SalesforceXyTools Install](http://www.ibmer.info/salesforcexytools-install.html)
  * [SalesforceXyTools Auto Create VF-Controller-DTO-DAO-Code](http://www.ibmer.info/auto-create-sfdc-code.html)
  * [SalesforceXyTools: Export Sobject To Excel](http://www.ibmer.info/export-sobject-excel.html)
  * [SalesforceXyTools Sublime Package](https://packagecontrol.io/packages/SalesforceXyTools)


## Auto Create VF-Controller-DTO-DAO-Code
Hello,I am Exia.huang.
Today I will show you how to create testclass quickly by using SalesforceXyTools.

## There are 5 steps.
1. Open the apex code, and find the menu below.
  [SFDC-XY]->[SFDC Code Creator]->[Create Test Code]
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/testcode/Image%20001.jpg?raw=true)
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/testcode/Image%20002.jpg?raw=true)
  
  * The class code which I have selected is like below.
  ```java
/**
* @author huangxy
*/
public with sharing class BlogController extends SfdcXyController {

        // DTO Bean
        public BlogDto blogDto {get;set;}

        public BlogController() {
            search();
        }

        private void search(){
            String id = ApexPages.currentPage().getParameters().get('id');
            if(String.isBlank(id)){
                this.blogDto = new BlogDto();
            }else{
                this.blogDto = new BlogDto(BlogDao.getBlogById(id));
            }
        }

        /**
         * upsert Dto
         */
        public PageReference doSave() {
            Boolean result;

            Savepoint sp = Database.setSavepoint();
            try {
                upsert blogDto.getSobject();
                result = true;
            } catch(DMLException e) {
                Database.rollback(sp);
                System.debug('saveDto DMLException:' + e.getMessage());
                result = false;
            } catch(Exception e) {
                Database.rollback(sp);
                System.debug('saveDto Exception:' + e.getMessage());
                result = false;
            }
            return null;
        }

        /**
         * Go Next
         */
        public override PageReference doNext() {
            Boolean result = doCheck();
            setNextMode(result);
            return null;
        }

        /**
         * Go Back
         */
        public override PageReference doBack() {
            Boolean result = true; 
            setBackMode(result);
            return null;
        }

        /**
         * do Check
         */
        public override Boolean doCheck() {
            Boolean result = true;

            return result;
        }
}
  ```  
  
  * Select [Create Test Code], the test code will be created automatically like below.
  ```java
/**
* @author huangxy
*/
@isTest
private class BlogControllerTest {

    /**
     * This is a test method for BlogController
     */
    static testMethod void test_BlogController() {

        // PageReference pageRef = Page.Blog;
        // Test.setCurrentPage(pageRef);
        // pageRef.getParameters().put('param1', 'param1');

        Test.startTest();

    BlogController blogController = new BlogController();


        Test.stopTest();

        // Check
        // System.assert(ApexPages.hasMessages());
        // for(ApexPages.Message msg : ApexPages.getMessages()) {
        //     System.assertEquals('Upload file is NULL', msg.getSummary());
        //     System.assertEquals(ApexPages.Severity.ERROR, msg.getSeverity());
        // }
    }


    /**
     * This is a test method for doSave
     */
    static testMethod void test_doSave() {

        // PageReference pageRef = Page.Blog;
        // Test.setCurrentPage(pageRef);
        // pageRef.getParameters().put('param1', 'param1');

        Test.startTest();

    BlogController blogController = new BlogController();
    PageReference resultDoSave = blogController.doSave();


        Test.stopTest();

        // Check
        // System.assert(ApexPages.hasMessages());
        // for(ApexPages.Message msg : ApexPages.getMessages()) {
        //     System.assertEquals('Upload file is NULL', msg.getSummary());
        //     System.assertEquals(ApexPages.Severity.ERROR, msg.getSeverity());
        // }
    }


    /**
     * This is a test method for doNext
     */
    static testMethod void test_doNext() {

        // PageReference pageRef = Page.Blog;
        // Test.setCurrentPage(pageRef);
        // pageRef.getParameters().put('param1', 'param1');

        Test.startTest();

    BlogController blogController = new BlogController();
    PageReference resultDoNext = blogController.doNext();


        Test.stopTest();

        // Check
        // System.assert(ApexPages.hasMessages());
        // for(ApexPages.Message msg : ApexPages.getMessages()) {
        //     System.assertEquals('Upload file is NULL', msg.getSummary());
        //     System.assertEquals(ApexPages.Severity.ERROR, msg.getSeverity());
        // }
    }


    /**
     * This is a test method for doBack
     */
    static testMethod void test_doBack() {

        // PageReference pageRef = Page.Blog;
        // Test.setCurrentPage(pageRef);
        // pageRef.getParameters().put('param1', 'param1');

        Test.startTest();

    BlogController blogController = new BlogController();
    PageReference resultDoBack = blogController.doBack();


        Test.stopTest();

        // Check
        // System.assert(ApexPages.hasMessages());
        // for(ApexPages.Message msg : ApexPages.getMessages()) {
        //     System.assertEquals('Upload file is NULL', msg.getSummary());
        //     System.assertEquals(ApexPages.Severity.ERROR, msg.getSeverity());
        // }
    }


    /**
     * This is a test method for doCheck
     */
    static testMethod void test_doCheck() {

        // PageReference pageRef = Page.Blog;
        // Test.setCurrentPage(pageRef);
        // pageRef.getParameters().put('param1', 'param1');

        Test.startTest();

    BlogController blogController = new BlogController();
    Boolean resultDoCheck = blogController.doCheck();


        Test.stopTest();

        // Check
        // System.assert(ApexPages.hasMessages());
        // for(ApexPages.Message msg : ApexPages.getMessages()) {
        //     System.assertEquals('Upload file is NULL', msg.getSummary());
        //     System.assertEquals(ApexPages.Severity.ERROR, msg.getSeverity());
        // }
    }


    /**
     * This is a test method for all
     */
    static testMethod void test_all() {

        // PageReference pageRef = Page.Blog;
        // Test.setCurrentPage(pageRef);
        // pageRef.getParameters().put('param1', 'param1');

        Test.startTest();

    //  test BlogController
    BlogController blogController = new BlogController();

    //  test doSave
    PageReference resultDoSave = blogController.doSave();

    //  test doNext
    PageReference resultDoNext = blogController.doNext();

    //  test doBack
    PageReference resultDoBack = blogController.doBack();

    //  test doCheck
    Boolean resultDoCheck = blogController.doCheck();



        Test.stopTest();

        // Check
        // System.assert(ApexPages.hasMessages());
        // for(ApexPages.Message msg : ApexPages.getMessages()) {
        //     System.assertEquals('Upload file is NULL', msg.getSummary());
        //     System.assertEquals(ApexPages.Severity.ERROR, msg.getSeverity());
        // }
    }


}
  ```

2. Insert Test Data(All Field) 
  I will select Blog__c.
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/testcode/Image%20003.jpg?raw=true)
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/testcode/Image%20004.jpg?raw=true)
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/testcode/Image%20005.jpg?raw=true)

   ```java
  List<Blog__c> blogList = new List<Blog__c>();
for(Integer i=0; i<5; i++){
    Blog__c blog = new Blog__c();
    blog.comment__c = 'CoaM5Vy' + string.valueof(i) ;    //評価
    blog.comment_status__c = 'spam';    //評価ステータス
    blog.content__c = 'biKtXlF' + string.valueof(i) ;    //内容
    blog.excerpt__c = 'QVbhcE8' + string.valueof(i) ;    //概要
    blog.status__c = 'Draft';    //ステータス
    blog.title__c = '52lF1IP' + string.valueof(i) ;    //タイトル
    blogList.add(blog);
}
insert blogList;
   ```


3. Insert Test Data(From SOQL) 
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/testcode/Image%20006.jpg?raw=true)
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/testcode/Image%20007.jpg?raw=true)
  ![SOS](https://github.com/exiahuang/XyHelp/blob/master/SalesforceXyTools/testcode/Image%20008.jpg?raw=true)
  ```sql
  select id,name,comment__c,content__c from Blog__c limit 2
  ```

  * Select [Insert Test Data(From SOQL) ] Menu, the sql will be change to apex code like below.

  ```java
    List<Blog__c> blogList = new List<Blog__c>();
    Blog__c blog0 = new Blog__c();
    // blog0.id = 'a096F00001yVNHWQA4';    // カスタムオブジェクト ID
    blog0.name = 'ID-0004';   // ブログNo
    blog0.comment__c = '評価';   // 評価
    blog0.content__c = '評価';   // 内容
    blogList.add(blog0);

    Blog__c blog1 = new Blog__c();
    // blog1.id = 'a096F00001yVNHRQA4';    // カスタムオブジェクト ID
    blog1.name = 'ID-0003';   // ブログNo
    blog1.comment__c = '評価1e';   // 評価
    blog1.content__c = '内容';   // 内容
    blogList.add(blog1);

    upsert blogList;
  ```
