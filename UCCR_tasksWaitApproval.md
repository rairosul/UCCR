---

copyright:
  years: 2017
lastupdated: "2017-8-7"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Creating wait for approval tasks
{: #tasks_waitApproval}

A Wait for approval task pauses a deployment until a designated user provides approval. Email notifications are sent to users when the task starts. 

To create a Wait for approval task, complete the following steps:

1. On the Deployment Plan Details page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before you use the **Create Task** action. The new task is inserted before the selected task.

1. In the Create Task dialog box, in the **Type** list, select **Wait for approval**.

1. In the **Name** field, enter a name for the task.

3. In the **Approval prompt** field, enter the text that you want to include in the email message. The text is displayed in the **Task Details** section of the email.

3. In the **Approvers** list, select the users or groups designated to approve the task. Team members and groups are available to choose.

3. In the **Required approver** area, specify whether all the approvers must approve the task, or just a single approver is sufficient.

5. Click **Save**. The task is inserted into the deployment plan.

When the task runs, email notifications are sent to the selected approvers. The deployment plan cannot progress until the task is approved or skipped. Approval is granted by completing the task in the deployment plan.
