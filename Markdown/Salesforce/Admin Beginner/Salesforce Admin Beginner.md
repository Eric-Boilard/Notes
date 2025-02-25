# Admin Beginner Trail

https://trailhead.salesforce.com/content/learn/trails/force_com_admin_beginner

## Modules

* Salesforce Platform Basics
* Data Modeling
* Data Management
* Lightning Experience Customization
* User Engagement
* Reports & Dashboards


### Salesforce Platform Basics

This section really just goes over uses for the platform and how to navigate Setup and the AppExchange.

### Data Modeling

Goes over what standard and custom objects are. Goes into detail about the different types of object relationships and Schema Builder.

* Lookup Relationships
    + A lookup relationship essentially links two objects together so that you can “look up” one object from the related items on another object

* Master-Detail Relationships
    + In this type of relationship, one object is the master and another is the detail. The master object controls certain behaviors of the detail object, like who can view the detail’s data. If a record on the master object is deleted, all its related detail records are deleted as well. When you’re creating master-detail relationships, you always create the relationship field on the detail object.

* Hierarchical Relationship
    +  Hierarchical relationships are a special type of lookup relationship. The main difference between the two is that hierarchical relationships are only available on the User object. You can use them for things like creating management chains between users.

* Schema Builder can be used to see how objects and fields are all related to eachother. You can also create objects and fields very quickly with the schema builder itself.

### Data Management

This Module goes over how to import and export data and the different tools within salesforce we can use to do so.

* Import
    + Data Import Wizard - Access through setup, less than 50k records, standard object and some custom objects.
    + Data Loader - client app for up to 150 million records of any data type from database or file connection. Can be operated through UI or command line. Can use to automate using API calls.
    + Use app exchange if you need to import more records.

* Export 
    + Data Export Service - in browser, export data manually or automatically at weekly or monthly intervals, varies by edition.
    + Data Loader - client app, user interface or command line, great for more flexible automation.

### Lightning Experience Customization

This module goes over creating and editing objects, fields, apps, list views, highlights and compact layouts, page components, buttons and links, and quick actions.

* Lightning Apps
    + We can create apps and customize how they look with themes and logos and we can also select what tabs appear at the top of the page.

* List Views
    + List views, like the app, are pretty basic and you can control the fields on the list view along with how it gets filtered. One cool thing I learned is you can create charts from a list view.
    + When you create a list view chart for an object, such as Opportunities or Leads, the chart is associated with the object. The chart is available for any list view that you have permission to see for that object, except the Recently Viewed list. 

* Compact Layouts
    + Compact layouts control which fields your users see in the highlights panel at the top of a record. They also control the fields that appear in the expanded lookup card you see when you hover over a link in record details, and in the details section when you expand an activity in the activity timeline.
    + Compact layouts also control how records display in the Salesforce mobile app. If your company uses the Salesforce mobile app, you can help your users see what they need on mobile screens, where space is limited and quick recognition of records is important.

* Record Page Components
    + You can customize and personalize many things on object record pages using a combination of the Lightning App Builder and page layouts.
    + Most of the pages you see in Lightning Experience, such as the Home page and record pages, are Lightning pages. Lightning pages are a collection of components arranged in regions on the page. You can customize the structure of the page, the position of its components, and the record detail fields it displays with the Lightning App Builder.

* Buttons and Links
    + Custom links can link to an external URL, such as www.google.com, a Visualforce page, or your company’s intranet. Custom buttons can connect users to external applications, such as web pages, and launch custom links.
    + List button—Appears on a related list on an object record page.
    + Detail page link—Appears in the Links section of the record details on an object record page.
    + Detail page button—Appears in the action menu in the highlights panel of a record page.

* Quick Actions
    + Actions let your users quickly do tasks, such as create records, log calls, send emails, and more. With custom actions, you can make your users’ navigation and workflow as smooth as possible by giving them quick access to information that’s most important.
    + Object-specific actions have automatic relationships to other records and let users quickly create or update records, log calls, send emails, and more, in the context of a particular object
    + You create global actions in a different place in Setup than you create object-specific actions. They’re called global actions because they can be put anywhere actions are supported. Use global actions to let users log call details, create records, or send email, all without leaving the page they’re on.
        + If an object page layout isn’t customized with actions, then the actions on those object record pages are inherited from the global publisher layout.

### User Engagement

In this module we go over user engagement in the form of prompts. These prompts are basically popups that can guide the users in your org down the right path or share useful information. To get access to be able to customize prompts you will likely need to download some managed packages.

* Floating Prompts - A floating prompt is a nonintrusive way to nudge users toward a feature or opportunity. You can place a floating prompt in one of nine positions on a page. 
* Targeted Prompts - Targeted prompts have all of the same benefits as a floating prompt without being confined to nine placement positions. Connect a targeted prompt to a specific page element to show your users exactly what you’re referring to.
* Docked Prompts - Docked prompts are helpful when users need to refer to content while exploring a feature on their own. Unlike the floating and targeted prompts, the docked prompt stays in place as the user navigates through the app

### Reports & Dashboards

In this module we go over reports and dashboards and how and when we should use them.

* Reports - In its simplest form, a report is a list of records (like opportunities or accounts) that meet the criteria you define. But reports are much more than simple lists. To get the data you need, you can filter, group, and do math on records. You can even display them graphically in a chart!
* Report Types - A report type is like a template. Choosing the right report type is important in building a report, because when you choose a report type, you’re selecting the records and fields that are available for your report.
* Dashboards - A dashboard is a visual display of key metrics and trends for records in your org. Each dashboard widget is based on a single source report.Each dashboard has a running user, whose security settings determine which data to display in a dashboard. If the running user is a specific user, all dashboard viewers see data based on the security settings of that user—regardless of their own personal security settings.

#### Report Filters

| Filter Type | Description |
| -------- | -------- |
| Standard Filter | Most objects include standard filters. Different objects have different standard filters, but most include the standard filters Show Me and Created Date. Show Me filters the object around common groupings (like My accounts or All accounts). Date Field filters by a field (such as Created Date or Last Activity) and a date range (such as All Time or Last Month). |
| Field Filter | Field filters are available for reports, list views, workflow rules, and other areas of the application. For each filter, set the field, operator, and value. To add a field filter, use the search bar in the Filters tab or drag the field from the Fields list. |
| Filter Logic | Add Boolean conditions to control how field filters are evaluated. You must add at least 1 field filter before applying filter logic. Filter logic applies to field filters, but not standard filters. |
| Cross Filter | Filter a report by a child object using WITH or WITHOUT conditions. Add subfilters to further filter by fields on the child object. For example, if you have a cross filter of Accounts with Opportunities, click Add Opportunity Filter and create the Opportunity Name equals ACME subfilter to include only those opportunities. |
| Row Limit | For ungrouped (tabular) reports, select the maximum number of rows to display, choose a field to sort by, and specify the sort order. You can use a tabular report as the source report for a dashboard table or chart component if you limit the number of rows it returns.|

* If you have multiple filters you can add filter logic and if you want to lock your filters so that other users cannot change them when looking at the report you can do so from the run page.

* Different Types of Reports
    + Tablular Reports - Tabular reports are the simplest and fastest way to look at your data. Similar to a spreadsheet, they consist simply of an ordered set of fields in columns, with each matching record listed in a row
    + Summary Reports - Summary reports are similar to tabular reports, but also allow you to group rows of data, view subtotals, and create charts. Summary reports give us many more options for organizing the data, and are great for use in dashboards.
    + Matrix Reports - Matrix reports allow you to group records both by row and by column. These reports are the most time-consuming to set up, but they also provide the most detailed view of your data
        + Often when viewing a matrix report its a good idea to toggle off report details to make it easier to read.

* Dashboards are fairly simple and are widgets that allow us to visually represent reports in a grid builder layout.

* Dynamic Dashboards - With dynamic dashboards, each user sees the data they have access to without needing to create separate dashboards for each user.
    + You can’t save a dynamic dashboard in a private folder.

* Report Charts - If you don’t want to create a dashboard, but just want to add a chart to your report, then report charts may be right for you. Report charts allow you to place a single chart right at the top of your report, so that when you view the report, you can see the chart and the report results in one view.