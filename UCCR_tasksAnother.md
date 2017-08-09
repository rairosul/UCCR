---

copyright:
  years: 2017
lastupdated: "2017-8-4"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Creating run another plan tasks
{: #tasks_runAnother}

A run another plan task runs a deployment for another deployment plan. The targeted plan must be created from a template. Both the template and the targeted plan must be in the same release event as plan with the run another plan task.

Note that this is an experimental task type.

To create a run another plan task, complete the following steps:

1. On the Deployment Plan Details page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before you use the **Create Task** action. The new task is inserted before the selected task.

1. In the Create Task dialog box, in the **Type** list, select **Run Another Plan**.

1. In the **Name** field, enter a name for the task.

3. In the **Plan Template Name** list, select a deployment plan template. The template must be in the same release event as the task's parent plan.

3. In the **Tags** list, attach a tag to the task. You can select multiple tags. To create a tag, type the tag name in text box.

5. Click **Save**. The task is inserted into the deployment plan.

When the task runs, a deployment starts for the deployment plan that is created from the selected template and in the same release event. If multiple plans in the release event are created from the template, deployments start for all of them. While the other deployments run, status information is provided by the run another plan task. Expand the task to see the status information. You can open the other deployments by using links on the task. While the other deployments run, the run another plan task has a status of **In Progress**.


