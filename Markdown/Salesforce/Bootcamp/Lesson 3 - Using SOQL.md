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

You can go 5 levels up from Child to Parent

Parent to Child

the relationships are now plural
before we went from Contact to Account and the relationship was the Account relations
now we go from Account to Contact and the relationship is Contact(s). Plural! This is the only way to get to the child from the parent for standard objects.

okay so before we went from Course_Deliveries__c to Course__c and the relationship was Course__r, now when we go from Course__c to Course_Delivery__c the relationship is Course_Deliveries__c. it becomes plural just like our other example.