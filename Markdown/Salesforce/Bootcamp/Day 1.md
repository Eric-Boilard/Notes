Org
Username: tdx25@pd1-bc.1019.com
Password: password@1234

Can use login.salesforce.com

mimeo
eric.boilard@outlook.com
Apollothirteen95!

Questions:
https://shorturl.at/Z3oJL

15-Character unique case sensitive form
18-character case safe

Salesforce Id can be seen in many places but in reports and formulas they are the 15 character version, everywhere else is 18.

Collection types:

Lists
Sets
Map (key value pair)
    Key object pair
    Key can be any type

You can debug apex but you cannot debug triggers so it helps to use apex replay debugger to replay the debug logs as if it is running.

Breakpoint: pause at a specific point to examine
Checkpoint: capture heap dumps and provide richer information for all local variables, static variables, and trigger context variables.

There will be questions on the exam for the collections and types.

Important to know difference between =, ==, ===

If you exceed limits an error will be thrown and the whole operation will be rolled back.

SOQL

SQL allows SELECT * and SOQL does not, but we have SELECT FIELDS(ALL)

There will be questions on limits

SQL supports joins
SOQL does not support joins but supports relationships

You get Id without having to reference in the select statement.

% for like matches 0 or more
_ matches exactly 1 character

You can run SOQL query from the query builder, just click the switch button if you closed it to reopen. Or you can run SFDX: Execute SOQL Query with Currently Selected text

You can bind variables in SOQL but some are not supported like Last_N_Days

When you want to use a SOQL query in APEX code you must bracket it.

You can get a single account, list of accounts, or an integer.

2 types of exceptions can be raised if you dont have results or if you have more than one row
System.QueryException: List has no rows for assignment to sobject
System.QueryException: List has more than one row for sobject

?? can be used to give a default if null is returned, add this to the end of the SOQL query 

Example: Account acct = [] ?? defAcc;

you can assign to a field not declared in the select query but you cannot try to get that field in something like a system.debug.

important for exam gov limits
limits of dml
limits of soql
limit of heap
number of rows that can be altered by dml

SOQL for loop will bring in records in batches of 200 and place into a buffer and then process, then get the next 200, buffer and process.

if you used a list instead of a single sobject then it would be a SOQL for loop with implicit batching.

you can use bracket notation or database query notation.
Dynamic database query builds during runtime

Name of relationship for parent to child is the name of the parent. For example, Account to contact is an account relationship.

Child to Parent - Standard Object

you can build a query like this
SELECT Id, AccountId FROM Contact
Or specify the relationship instead of the foreign key field like this:
SELECT Id, Account.Id FROM Contact

Child to Parent - Custom Object
in custom objects the foreign key is the name of the parent, example:
SELECT Id, Course__c, Course__r.Name From Course_Delivery__c
here Course__c exists in Course_Delivery__c object but the Course Name exists only on Course__c so we use Course__r.Name

You can go 5 levels up from Chile to Parent

