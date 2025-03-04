Triggers dont have access to the recycle bin.

Trigger.new gets all of the new items from the trigger

we can compare previous values with new values by creating a map from old to new

Trigger.oldMap.get(new.id)

Trigger.new, the new is a trigger context variable

If you dont want to see null reference exceptions, use a safe navigation operator which is '?'.

If you are using trigger.new or trigger.old, it automatically behaves like a SOQL for loop when inside a for loop.

addError will prevent the DML operations from persisting to the DB.

The active flag on triggers is only available in sandboxes

metadata types are available to cash and are deployable.

