You get constructor for free if you do not create one.

Static belongs to the class and not the instance of the class. For example it applies to the blueprint, not the record.

these get invoked by class name then the method name and any perameters you want.

final is not editable

a non static method needs an instance of the class but a static method can be invoked from the class directly.

@future must return void and must be static

@invocableMethod must also be a static method. only one invocable method is allowed per class.

@rest resource - used to expose the whole class to REST, supports http verbs like HttpGet

@aura enabled - static method enabling access to the method from a Lightning Component.

Triggers themselves should not have the business logic in them and in fact should just send anything to a handler class.

when no sharing access is declared in the class, most of the time it ignores the sharing model. Unless you run it in an anonymous block, then it respects it.

virtual classes are intended to be extended. 

abstract class means half baked food. It can contain implementations or not or some. You can not instantiate an abstract class.

Need to research these a little more as they are not 100% clear to me.

If I declare a class and say I dont want to respect record level security but I want to for one single statement, I can do that with User_Mode

