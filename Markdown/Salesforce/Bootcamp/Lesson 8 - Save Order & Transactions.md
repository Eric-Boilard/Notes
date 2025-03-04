Formula fields only calculate when the record is being read.

Instructor has a video on youtube to explain order of execution. Try to find this.

1. Load original record into memory
2. addes new values
3. performs some system validations (like date)
4. executes before record trigger flow and then before apex trigger
5. runs again most system validations
6. then finally custom validations
7. executes duplicate rules
8. Gets saved to the database...but not committed and Id gets generated
9. execute all after save triggers
10. execute workflow rules
11. if you do make changes in the workflow we execute all before update triggers
12. then we execute most system validations
13. save the record to the database again, but not commit
14. Execute all after update apex triggers
15. execute processes if the process updates a field
16. this diverts again to run any before update triggers
17. execute system validations and custom validations
18. save to the database again
19. execute after update apex triggers
20. execute workflow rules
21. could execute process again due to recursion
22. after save record trigger flow if the flow updates a field
23. execute before update apex triggers
24. execute most system and all custom validations
25. savethe updated record to database...not commit
26. execute after update apex triggers
27. perform calcs from rollup summary fields or cross object workflow on ancestors working from parent upward.
28. execute criteria based sharing rules
29. commit logic

French Fries - FF- Fast Fields
Pirate something...

You should only have one trigger for each object.

on rollup summary fields the child runs through the whole process up until its step then the master has to roll through the entire process as well and there is only one commit.

What happens if there is a failure? you rollback all of the changes and nothing gets committed to the database. This can be bypassed with a database.insert with the correct perameters because we can save the ones that pass and rollback those that fail.

failures rollback the entire transaction even if there are multiple dml executions that were successful.

static variables are scoped to the transactions
so if we have two users each creating a contact at the same time, there are two transactions which means the static variables belong to their respective transaction.




