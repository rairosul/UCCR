---

copyright:
  years: 2017
lastupdated: "2017-8-4"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Creating Slack tasks
{: #tasks_slack}

A Slack task sends a message to a Slack channel when it runs. The message can contain text and hyperlinks. A Slack task starts as soon as it is eligible to run.

To create a Slack task, complete the following steps:

1. On the Deployment Plan Details page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before you use the **Create Task** action. The new task is inserted before the selected task.

1. In the Create Task dialog box, in the **Type** list, select **Slack**.

1. In the **Name** field, enter a name for the task.

3. In the **Webhook URL** field, enter the URL of the Slack channel where you want the message delivered, for example, `https://hooks.slack.com/services/my_webhook`.

3. In the **Message** box, enter the message body.  The message can contain text and hyperlinks.

3. In the **Duration (minutes)** field, enter the number of minutes that you expect the task to run until it is completed. The estimated duration is used to calculate expected deployment times.

3. In the **Tags** list, attach a tag to the task. You can select multiple tags. To create a tag, type the tag name in text box.

3. In the **Assigned groups and users** list, assign the task to a user or group. The assigned user runs the task during deployment.

5. Click **Save**. The task is inserted into the deployment plan.

When the task runs, the message defined in the Message field is sent to the Slack channel specified in the Webhook URL field.

