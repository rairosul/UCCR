---

copyright:
  years: 2017
lastupdated: "2017-9-1"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Managing ServiceNow tasks
{: #tasks_ServiceNow}

A ServiceNow task can create and update ServiceNow change requests. A ServiceNow task can perform one of the following actions:

* **Create** creates a ServiceNow change request. You can set the values for all request fields, and pass the request ID to update, and wait tasks.
* **Update** can update the values for all request fields.
* **Wait** waits for a particular value in a specific field. The field can be any field on the change request.

ServiceNow task prerequisites:
* ServiceNow tasks work with Internet-accessible instances of ServiceNow, such as <code>my_instance.service-now.com</code>.
* ServiceNow tasks work with the Jakarta release of ServiceNow, and references the current API version.
* The user supplying credentials for the task must have access to the ServiceNow API, and permission to see and modify all change request fields. At a minimum, the user must be in a ServiceNow role that has the **Create Change** permission.

A ServiceNow task can include ServiceNow properties and {{site.data.keyword.uccr_short}} properties. ServiceNow properties have the following syntax: `propertyName=value`.

To create a ServiceNow task, complete the following steps:

1. On the Deployment Plan Details page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before you use the **Create Task** action. The new task is inserted before the selected task.

1. In the Create Task dialog box, in the **Type** list, select **ServiceNow**.

1. In the **Name** field, enter a name for the task.

3. In the **Tags** list, you can attach a tag to the task. You can select multiple tags. To create a tag, type the tag name in text box.

3. In the **Connection settings** area, enter the URL of the ServiceNow instance, and the user ID, and password of the ServiceNow user.

3. In the **Action** list, select the action type for the task. The action types are defined in this list:

*  The **create** action creates a ServiceNow change request with the properties defined in the task. 
*  The **update** action modifies properties in change request. 
*  The **wait** action waits for a specific value in a change request field.  

7. Complete the action-specific parameters, as described in the following tables:

| Create action | Description |
| ------------------ |------------------|
| Request type | You can use the ServiceNow default types or a user-created type. Default types are normal, emergency, and standard.|
| Short description                 | The text you enter is displayed in the ServiceNow ticket's **Short description** field. |
| Assignment group                 | The ServiceNow agent or group responsible for resolving the ServiceNow ticket. Possible assignees include agents and groups available to the ServiceNow instance.|
| Additional properties                 | The Service properties set by this task. Separate properties by commas. For example, a simple request might include the following fragment: `approval=requested, state=-4, impact=3`. |
| Output property                 | Captures the ServiceNow ticket ID. For example, if you specify `service_now_stage_ticket_id`, you can use it with update and wait actions to identify the ticket. |
---

| Update action | Description |
| ------------------ |------------------|
| System ID                 |The ID of the ServiceNow change request. If you capture the ID with a create action **Output property** field, you can use it here. For example, if you specify `service_now_stage_ticket_id` in the **Output property** field of a create action, you can use the ID by specifying `${service_now_stage_ticket_id}`. [See the Properties reference for information about properties](/docs/services/UCCR/UCCR_property_ref.html#property_overview)|
| Additional properties                 |The ServiceNow properties set by this task. Separate properties by commas. |
---

| Wait action | Description |
| ------------------ |------------------|
| System ID                 |The ID of the ServiceNow change request. If you capture the ID with a create **Output property** field, you can use it here. For example, if you specify `service_now_stage_ticket_id` in the **Output property** field of a create action, you can use the ID by specifying `${service_now_stage_ticket_id}`.|
| Field                 |The name of the affected field in the ServiceNow change request. The value in the field is checked for updates on an interval defined by the Check request interval field. For example, if you are checking the **approval** field, you might specify `approval`. |
| Value                 |The value expected in the ServiceNow field as defined by the **Field** property. For example, if you are checking the **approval** field, you might specify `approved`. In this example, when the value in the **approval** field changes to `approved`, the task completes successfully.|
| Check request interval                 |The value defines how frequently ServiceNow is checked for updates. The value represents minutes. The default value is `1`, which mean ServiceNow is polled every minute.|
---
{: caption="Table 1. ServiceNow actions" caption-side="top"}

When the task starts, it has the status of **In progress**. The status changes to **Complete** when the related ServiceNow action is resolved.
