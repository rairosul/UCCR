---

copyright:
 years: 2017
lastupdated: "2017-8-30"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Managing properties
{: #property_overview}

A deployment plan can contain user-defined properties. Properties can contain variable data values that can be defined at design- or run-time.

{:shortdesc}

Tasks can reference properties defined in their parent deployment plan. If a deployment plan is part of a release, its tasks can reference properties defined in the other plans in the release. In addition to the properties that you create, system properties are available to all plans.

## Creating properties
{: #property_create}

You define properties with the Deployment plan detail page's **Properties** tab. You can create a property before you use it, or you can create a property by first referencing it in a task, and then later defining the attributes.

To create a property, complete the following steps:

1. On the Deployment plan detail page, click **Properties**, and then click **Add**.

2. On the Add property window, in the **Name** field, enter the name. Property names cannot contain white spaces, `{}`, or `:`.

2. In the **Label** field, enter the label. The label appears in the UI.

3. In the **Type** list, select the property type. The available types are described in this list:
- `Text`
- `Text area`
- `Date and time`. Values are replaced by a string with the following format `day, month, year, time`. For example, `Thursday, January 1st 1970, 12:00 am UTC`. **Note**: When a `Date and time` property is used in a ServiceNow task, the value is replaced with the date and time  format expected by ServiceNow.

5. In the **Value** field, you can enter an initial value for the property.

5. In the **Default value** field, enter a value for the property. The default value is used unless the user sets another value for the property. You can leave this field blank.

6. If you want users to supply a value when they create a release that contains the property, check **Prompt for this property at release creation at the specified sequence position**.

6. In the **Display sequence position** list, select a position for the property in the list of properties.

6. Click **Save**. 

## Using properties
{: #property_using}

Use the following syntax to reference a property: `${propertyName}`. To escape the syntax pattern, use two dollar-sign symbols, $${...}.

Properties can be used by the following task types:

- [ServiceNow](/docs/services/UCCR/UCCR_tasksServiceNow.html). You might use the **Output property** field in a create change request action to store the change request ID in a property like this example, `service_now_prod_ticket_id`. Then, with another task, update the change request by referencing the property in the **System ID** field like this, `${service_now_prod_ticket_id}`.
- [Email](/docs/services/UCCR/UCCR_tasksEmail.html). You might reference a system property in the **Email subject** field like this example: `${sys:release.name}` is complete!
- [Delayed](/docs/services/UCCR/UCCR_tasksDelayed.html). You might reference user-created property in the **Delay property** field like this example: `${prodTarget}`. In this example, the task delays until the value in the `${prodTarget}` property is reached.
<!--- [Wait for approval](/docs/services/UCCR/UCCR_tasksWaitApproval.html)-->

If you create a property by referencing it in a task, it appears as text-type property on the **Properties** tab. 

You set most property values with the **Properties** tab. Some property values are set by external systems, such as ServiceNow.

## System properties
{: #property_system}

System properties enable you to access information about a deployment plan's parent release. If a deployment plan is not part of a release, the system properties are unavailable. System properties can be referenced by any property-enabled task that is part of a release.

The following table contains the available system properties:

| Property  | Description  |
| ------------------ |------------------|
|`${sys:release.name}`                 |The value in the release's **Name** field.|
|`${sys:release.description}`                        |Contains the content of the release's **Description** field.|
|`${sys:release.start}`                        |Contains the content of the release's **Start time.|
|`${sys:release.end}`                 |Contains the content of the release's **End time** field.|

{: caption="Table 1. System properties" caption-side="top"}

In the **Email message** field of an Email task, you might reference system properties like this example: Deployment for release `${sys:release.name}` - `${sys:release.description}` is complete.

You might reference a system property in a ServiceNow task's **Short description** field like this example: Staging deployment `${sys:release.name}`.}
