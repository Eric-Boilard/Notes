SOSL is used when we arent sure exactly what we are searching for but we can search a term or name across all objects and fields.

We can use wildcards in our search term and they are different than the wildcards in SOQL. In SOQL for like we use % or _ and in SOSL we use * or ?

'In All Fields' is the default but you can search in Name Fields, Email Fields, Phone Fields. There are some exclusions on types like maybe long text fields.

in 'returning' we can use multiple objects and fields, for example Account (Name, Address), Opportunity (Name, stage). Cert Question

If you specify the fields you want to return, the search will still search every field in the object, it just only returns the ones you specify.

SOSL can be executed in apex with bracket notations and search.query()

SOSL In apex can look like this:
List<List<sObject>> acmes = [Find 'Acme' Returning Account (Name), Opportunity(Name)]

This will search all fields that match Acme
The first collection will be the type of sObject
the second collection will be the details of the so object

SOSL has governor limits:
within a transactions-
total number of transactions = 20...there are more limits

parent to the child, look for plural