---

copyright:
  years: 2017
lastupdated: "2017-8-4"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Creating delayed tasks
{: #tasks_delayed}

Delayed-type tasks represent milestones or critical events during a deployment. With delayed tasks, you can ensure that important tasks start at the expected time. Typically, delayed tasks are prerequisites for other important tasks.

A delayed task starts as soon as it is eligible to run, and it finishes at a user-specified time. A started delayed-type task has a status of `In Progress` until it reaches its planned-for time, when it then changes its status to `Complete`. When a delayed tasks completes, auto tasks that are dependent on it start running.

Complete the following tasks to create a delayed task:

1. On the Deployment Plan Details page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before using the **Create Task**. The new task is inserted above the selected task.

1. In the Create Task dialog box, in the **Type** list, select **Delayed**.

1. In the **Name** field, enter a name for the task.

3. In the **Time** field, enter or select the time that the task will be completed.

3. In the **Time Zone** list, select the time zone for the value that is entered in the **Time** field.    

5. Click **Save**. The task is inserted into the deployment plan.


