# Developer Biginner Trail

<link>

## Modules

* Salesforce Platform Basics
* Platform Development Basics
* Get Started with Salesforce Development
* Data Modeling
* Lightning Experience Customization
* Formulas and Validations
* Flow Builder Basics
* Apex Basics & Database
* Apex Triggers
* Lightning Web Component Basics

### Salesforce Platform Basics

Repeat from Admin Trails

### Platform Development Basics

Repeat from Admin Trails

### Get Started with Salesforce Development

This module goes over the basics of how to setup your salesforce developer environment with visual studio code and what items you need to install.

* Install VSCode
* Install SDK version supported by salesforce
* Install CLI
* Install Salesforce Expansion Pack
* Install Node and NPM

Create new projects and authorize them to a specific org to connect to that Org vis vscode.

Objects can be created from spreadsheets like a .csv file. These auto map fields and allow you to create objects faster.

The ability to access data and schema of custom objects via API. The object schema and all of the records you've created can be accessed using an automatically generated REST API. 

Salesforce Postman Collection https://github.com/forcedotcom/postman-salesforce-apis

You can pull in changes from the UI by selecting the cloud icon next to resources you havent pulled in yet or you can retrieve source from Org if you have already pulled in the item before.

You can also retrieve metadata using the CLI. For example, execute the command below in the terminal to retrieve all other metadata items listed below.

* sf project retrieve start --metadata CustomApplication:Dreamhouse CustomTab:House__c "Layout:House__c-House Layout"

Apex is the strongly typed, object-oriented programming language that's optimized to run in the Salesforce multitenant architecture. Apex allows developers to automate complex backend business processes, and gets compiled into Java bytecode.

The Apex language is optimized to interact with Salesforce data and is tightly integrated with the Salesforce persistence layer. Apex provides SOQL (Salesforce Object Query Language), similar to SQL, for executing queries and DML (Data Manipulation Language) statements for performing database operations with the objects you created earlier.

Create Apex classes easily by right clickling in the class folder and create Apex Class. You can also test any method in an APEX class by creating an apex script in the scripts/apex folder. These scripts are not saved to metadata and are simply used for development.

You can also store soql queries in the Apex/soql folder for easy use later on.

In as small project...We use a Base Lightning component lightning-map to plot the dataset on a Map. Base components wrap up a lot of functionality. In this example, you didn’t have to write HTML markup to produce a map UI or code as much JavaScript to integrate with Google Maps.

``` Html
<template>
  <lightning-card title="Housing Map">
    <!-- Explore all the base components via Base component library
    (https://developer.salesforce.com/docs/component-library/overview/components)-->
      <lightning-map map-markers={mapMarkers}> </lightning-map>
  </lightning-card>
</template>
```

The Lightning web component invokes the Apex class HouseService you wrote in the previous section to fetch the data. This code shows how to retrieve data by invoking an Apex method using the @wire decorator.

To allow an Apex method to be used in an LWC, you annotate it with the @AuraEnabled annotation. You can import the @AuraEnabled method to LWC as a function (shown in line 2). When used with the @wire decorator (line 8), the component retrieves data via the method.

``` Apex
import { LightningElement, wire } from "lwc";
import getHouses from "@salesforce/apex/HouseService.getRecords";
export default class HousingMap extends LightningElement {
    mapMarkers;
    error;
    @wire(getHouses)
    wiredHouses({ error, data }) {
        if (data) {
         // Use JavaScript Map function to transform the Apex method response wired to the component into the format required by lightning-map
          this.mapMarkers = data.map((element) => {
                return {
                    location: {
                        Street: element.Address__c,
                        City: element.City__c,
                        State: element.State__c
                    },
                    title: element.Name
                };
            });
            this.error = undefined;
        } else if (error) {
            this.error = error;
            this.mapMarkers = undefined;
        }
    }
}
```

You can also edit the xml file within a LWC to change some settings and behaviors of the lwc.

```
<?xml version="1.0" encoding="UTF-8"?>
<LightningComponentBundle xmlns="http://soap.sforce.com/2006/04/metadata">
 <apiVersion>59.0</apiVersion>
 <isExposed>true</isExposed>
  <targets>
 <target>lightning__HomePage</target>
</targets>
</LightningComponentBundle>
```

Notice that we have the target attribute set to lightning__HomePage. This means the administrators will have the component available to drop on the Home page. There are additional targets that developers can add here to expose the components for other parts of the Salesforce UI.  Sometimes a component's target includes additional context, such as input data. 

### Quick Start: Tour the Sample App Gallery

Trailhead sample apps provide code examples on a variety of developer features on the Salesforce platform. We've built the sample apps to help you ramp up on the latest and greatest Salesforce technology. 

Trailhead Sample Apps live in their own GitHub org. Here’s how to find them.

* Go to github.com/trailheadapps

In addition to the tooling included in the Salesforce command line, we use some tools that run with npm. So even though most projects don’t use Node.js in any runtime Salesforce code, we still have a package.json to import and configure the developer tools with npm. 

npm is the default package manager for Node.js. It consists of a package registry, a command line interface (CLI), and the npmjs.com website. It is widely adopted for building apps to implement developer tools and even general-purpose command line tools, including the Salesforce CLI and the open CLI framework (OCLIF).

In our sample apps we’re using the npm command line with several developer tools that perform code linting, code formatting, unit testing, and application lifecycle management (ALM) automation. The easiest way to install npm is to install Node.js, which bundles npm.

The high-level packages we use are:
* prettier: for formatting code
* eslint: for code linting
* @salesforce/sfdx-lwc-jest: the Jest extension for testing Lightning web components
* husky: to execute actions that verify code before committing to version control

We’ve also encapsulated certain common commands here in the scripts config. In each case, the command is executed using npm run. For instance notice the test:unit script key. You can execute your Lightning web component unit tests by running npm run test:unit from the command line.

(https://developer.salesforce.com/sample-apps)

### Data Modeling

Repeat from Admin Trails

### Lightning Experience Customization

Repeat from Admin Trails

### Formulas and Validations

Repeat from Admin Trails

### Flow Builder Basics

This module goes over the basics of what flows are and what components make up flows. 

Flows are used to create logic automation in your salesforce Org. They use Elements, connectors, and resources to automate tasks for users.

* Variables are used to store data like text, dates, formulas, and constants. Varaibles are resources.

* Elements are what you put on the flow canvas and these could be assignments, loops, get records etc.

* Connectors just connect the elements of a flow together to make the order of exectuion path.

You can create custom coded elements for flows like actions or components in Apex but there is a lot of out of box functionality.

### Apex Basics & Database

#### Quick Start: Apex

Apex is a strongly typed, object-oriented programming language that allows developers to execute flow and transaction control statements on the Salesforce platform.

If you’re used to Java or .NET development, you’ll find the programming in Apex fairly straightforward. If you’ve never coded before, you might be surprised by how easy it is to access and manipulate data using Apex. In this Quick Start, you'll create a simple Apex class to update old Account records.

* You dont have to create apex classes only in visual studio code, you can create them in the developer console as well.

What is Apex?

* Apex is a programming language that uses Java-like syntax and acts like database stored procedures. Apex enables developers to add business logic to system events, such as button clicks, updates of related records, and Visualforce pages.

* Hosted—Apex is saved, compiled, and executed on the server—the Lightning Platform.
* Object oriented—Apex supports classes, interfaces, and inheritance.
* Strongly typed—Apex validates references to objects at compile time.
* Multitenant aware—Because Apex runs in a multitenant platform, it guards closely against runaway code by enforcing limits, which prevent code from monopolizing shared resources.
* Integrated with the database—It is straightforward to access and manipulate records. Apex provides direct access to records and their fields, and provides statements and query languages to manipulate those records.
* Data focused—Apex provides transactional access to the database, allowing you to roll back operations.
* Easy to use—Apex is based on familiar Java idioms.
* Easy to test—Apex provides built-in support for unit test creation, execution, and code coverage. Salesforce ensures that all custom Apex code works as expected by executing all unit tests prior to any platform upgrades.
* Versioned—Custom Apex code can be saved against different versions of the API.

Like other object-oriented programming languages, these are some of the language constructs that Apex supports:

* Classes, interfaces, properties, and collections (lists, maps, and sets).
* Object and array notation.
* Expressions, variables, and constants.
* Conditional statements (if-then-else) and control flow statements (for loops and while loops).

You can write Apex both in visual studio code or directly in the developer console.

Apex supports the following data types.

* A primitive, such as an Integer, Double, Long, Date, Datetime, String, ID, Boolean, among others.
* An sObject, either as a generic sObject or as a specific sObject, such as an Account, Contact, or MyCustomObject__c (you’ll learn more about sObjects in a later unit.)
* A collection, including:
    * A list of primitives, sObjects, user defined objects, objects created from Apex classes, or collections
    * A set of primitives, sObjects, user defined objects, objects created from Apex classes, or collections
    * A map from a primitive to a primitive, sObject, or collection
* A typed list of values, also known as an enum
* User-defined Apex classes
* System-supplied Apex classes

The following two declarations are equivalent. The colors variable is declared using the List syntax.

`List<String> colors = new List<String>();`

Alternatively, the colors variable can be declared using array notation.

`String[] colors = new List<String>();`

Grow collections as needed by using the List.add() method to add new elements.

```Apex
// Create a list and add elements to it in one step
List<String> colors = new List<String> { 'red', 'green', 'blue' };
// Add elements to a list after it has been created
List<String> moreColors = new List<String>();
moreColors.add('orange');
moreColors.add('purple');
```

Apex Classes

* One of the benefits of Apex classes is code reuse. Class methods can be called by triggers and other classes.

* You can run these classes and most Apex code dirently from the Debug | Open Execute Anonymous Window.

Inspect Debug Logs

* Debug logs are useful for debugging your code. When Apex methods execute, the calls are logged in the debug log. Also, you can write your own debug messages to the log, which helps in debugging your code in case there are errors. The inspectResults() helper method, which is called by sendMail(), writes messages to the log by using the System.debug() method to indicate whether the email send operation was successful or had errors. You can look for these messages in the debug log that was generated when you executed the method.

In the example we used a class that doesnt take advantage of class members and since it does not, when we call it with execute anonymous we dont have to create a new instance of the object, we can just call the class.method name and then pass in the arguments. Just make sure the method is static. Like this:

``` Apex
public static void sendMail(String address, String subject, String body)
```

Before
``` Apex
EmailManager em = new EmailManager();
em.sendMail('Your email address', 'Trailhead Tutorial', '123 body');
```

After
``` Apex
EmailManager.sendMail('Your email address', 'Trailhead Tutorial', '123 body');
```

Use sObjects

* Because Apex is tightly integrated with the database, you can access Salesforce records and their fields directly from Apex. Every record in Salesforce is natively represented as an sObject in Apex. For example, the Acme account record corresponds to an Account sObject in Apex. The fields of the Acme record that you can view and modify in the user interface can be read and modified directly on the sObject as well.

* Each Salesforce record is represented as an sObject before it is inserted into Salesforce. Likewise, when persisted records are retrieved from Salesforce, they’re stored in an sObject variable.

* If you’ve added custom objects in your organization, use the API names of the custom objects in Apex. For example, a custom object called Merchandise corresponds to the Merchandise__c sObject in Apex.

Create sObject Variables

* To create an sObject, you need to declare a variable and assign an sObject instance to it. The data type of the variable is the sObject type.

``` Apex
Account acct = new Account(Name='Acme');
```

sObject and Field Names

* Apex references standard or custom sObjects and their fields using their unique API names.

* API names of object and fields can differ from their labels. For example, the Employees field has a label of Employees and appears on the account record page as Employees but its API name is NumberOfEmployees. To access this field in Apex, you’ll need to use the API name for the field: NumberOfEmployees.

* For custom objects and custom fields, the API name always ends with the __c suffix. For custom relationship fields, the API name ends with the __r suffix. For example:

    * A custom object with a label of Merchandise has an API name of Merchandise__c.
    * A custom field with a label of Description has an API name of Description__c.
    * A custom relationship field with a label of Items has an API name of Items__r.

* In addition, spaces in labels are replaced with underscores in API names. For example, a custom field name of Employee Seniority has an API name of Employee_Seniority__c.

Create sObjects and Adding Fields

* Before you can insert a Salesforce record, you must create it in memory first as an sObject. Like with any other object, sObjects are created with the new operator:

``` Apex
Account acct = new Account();
```




### Apex Triggers


### Lightning Web Component Basics

