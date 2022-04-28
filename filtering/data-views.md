---
description: Configuring data views in Konstrukt, the back office UI builder for Umbraco.
---

# Data Views

{% hint style="info" %}
**Work in Progress:** The documentation for this page is currently in progress.
{% endhint %}

## Defining data views

Data views allow you to define multiple, pre-filtered views of the same data source. This can be useful when entities exist in different states and you want a way to toggle between them.

#### **AddDataView(string name, Lambda whereClauseExpression) : KonstruktCollectionConfigBuilder&lt;TEntityType&gt;**

Adds a data view with the given name and where clause filter expression. Expression must be a `boolean` expression.

````csharp
// Example
collectionConfig.AddDataView("Active", p => p.IsActive);
````

#### **AddDataView(string group, string name, Lambda whereClauseExpression) : KonstruktCollectionConfigBuilder&lt;TEntityType&gt;**

Adds a data view with the given group, name and where clause filter expression. Expression must be a `boolean` expression.

````csharp
// Example
collectionConfig.AddDataView("Status", "Active", p => p.IsActive);
````