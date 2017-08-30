---

copyright:
  years: 2017
lastupdated: "2017-8-28"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Creating email tasks
{: #tasks_email}

An email task sends an email message when the task runs. You specify the email's recipients and message when you create the task. Email tasks are auto tasks and run as soon as they are eligible.

To create an email task, complete the following steps:

1. On the Deployment Plan Details page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before you use the **Create Task** action. The new task is inserted before the selected task.

1. In the Create Task dialog box, in the **Type** list, select **Email**.

1. In the **Name** field, enter a name for the task.

3. In the **Recipients** field, enter or select the email's recipient. The list of available recipients includes the users and groups who are members the team that manages the task. You can also type the email addresses of non-team members. You can specify multiple recipients.

3. In the **Email subject** field, enter the email topic. You can use properties in this field.

3. In the **Email message** field, enter or paste the email message. You can use properties in this field. You example, you might notify email recipients that a release is started by using a message similar to this one, "The `${sys:release.name}` release has started." [See the Properties reference for information about properties](/docs/services/UCCR/UCCR_property_ref.html#property_overview). 

5. Click **Save**. The task is inserted into the deployment plan.

When the task runs, the recipients receive an email from **IBM Continuous Release** with the subject you specified when you created the task.


