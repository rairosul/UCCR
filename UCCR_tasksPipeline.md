---

copyright:
  years: 2017
lastupdated: "2017-8-4"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Creating Continuous Delivery Pipeline tasks
{: #tasks_pipelineCD}

{{site.data.keyword.contdelivery_full}} pipelines automate your DevOps workflows. A pipeline is a sequence of stages that retrieve input and run jobs. You can manage your {{site.data.keyword.contdelivery_short}} pipelines with pipeline tasks. Continuous Delivery pipeline tasks are auto tasks and run as soon as they are eligible.

To create a Continuous Delivery pipeline task, complete the following steps:

1. On the Deployment Plan Details page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before you use the **Create Task** action. The new task is inserted before the selected task.

1. In the Create Task dialog box, in the **Type** list, select **Continuous Delivery Pipeline**.

1. In the **Name** field, enter a name for the task.

3. In the **Description** field, enter or paste a description. You might enter a note, a reminder, or other instructions in the field.

3. In the **Pipeline** field, enter or select the pipeline.

3. In the **Stage Name** field, enter or select the stage name. The stages defined for the selected pipeline are available.

3. In the **Tags** list, attach a tag to the task. You can select multiple tags. To create a tag, type the tag name in list's text field.

3. In the **Assigned groups and users** list, assign the task to a user or group. The assigned user runs the task during deployment.

3. In the **Owner** list, select the task owner. The default owner is the user who created the task. The **Owner** list is displayed after the task is assigned to a user or group.    

5. Click **Save**. The task is inserted into the deployment plan.

When a Continuous Delivery pipeline task runs, it runs the jobs on the specified stage for the selected pipeline.


