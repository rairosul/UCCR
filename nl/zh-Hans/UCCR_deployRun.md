---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# 运行部署
{: #deployment_run}

使用 {{site.data.keyword.uccr_short}} 可运行软件部署。通过解决部署计划中的任务来完成部署。
{:shortdesc}

部署会在计划的其中一个符合启动条件的任务启动时启动。如果安排的部署中某个符合启动条件的任务是自动任务（例如，UrbanCode Deploy 或延迟类型的任务），那么该部署会按安排的时间自动启动。否则，请通过启动计划中的其中一个符合启动条件的任务来开始部署。如果计划包含多个符合启动条件的任务，那么可以启动其中任一任务。您可以随时手动启动部署。也可以在安排的时间之前手动启动安排的部署。   

部署计划的执行模式将确定任务何时符合启动条件。如果计划具有顺序执行模式（这是缺省模式），那么任务会从第一个任务开始按其在计划中列出的顺序变为符合启动条件。第一个任务解决后，第二个任务变为符合启动条件。通过单击任务的**启动**按钮，可启动符合启动条件的手动任务。自动任务（例如，UrbanCode Deploy 任务）在符合启动条件后就会立即自动启动。

使用并行执行模式的组中的任务会同时变为符合启动条件。并行组中的任务可以按任意顺序启动。嵌套组和具有特别依赖关系的任务可能会影响执行模式。

可以在启动部署后修改部署计划。您可以添加、删除和修改任务。

解决完所有任务之后，部署即完成。如果任务的状态为`完成`、`失败`或`已跳过`，说明任务已解决。如果在部署完成后重新打开任务或添加任务，那么部署状态会更改为`进行中`。

## 手动启动部署
{: #deployment_start}

可以随时手动启动部署，包括安排为以后启动的部署。

部署计划中的任务可能不适用于部署。如果没有为 UrbanCode Deploy 任务指定版本或环境，那么这些任务不适用。创建 UrbanCode Deploy 任务时，可以使用**使用版本**选项延迟选择环境和版本。部署启动之前，请确保所有 UrbanCode Deploy 任务均适用于即将进行的部署。    

可以有意将任务排除在部署之外。通过将任务的标记排除在部署之外，可以使被标记的任务不适用。具有已排除标记的任务不适用于部署。  

不适用任务的状态为`不适用`。无法启动状态为`不适用`的任务。如果不适用的任务是活动任务的先决条件，那么将忽略此依赖关系。  

要启动部署，请完成以下步骤：

1. 在“部署计划”页面上，单击要用于部署的部署计划。这将显示“部署详细信息”页面。

2. 要使已标记任务不适用于当前部署，请单击**版本**，然后在**标记**区域中清除相应标记。如果任务有多个标记，请清除所有标记。

2. 要为任何不适用的 UrbanCode Deploy 任务选择版本或环境，请单击**版本**，然后选择该环境和版本。对于已经选择其环境和版本的任务，还可以更改所选环境和版本。

1. （可选）单击**隐藏不适用的任务**以从显示的任务列表中除去不适用的任务。隐藏的任务不会从部署计划中除去。

1. 针对计划中的其中一个符合启动条件的任务，单击**启动**操作 <img class="inline" src="images/task-start.png"  alt="“启动”任务操作">。如果有多个任务符合启动条件，那么可以启动其中任一任务。只有符合启动条件的任务才会显示“启动”按钮。已启动的任务在解决之前，其状态为`进行中`。

部署启动后，计划的状态会更改为`进行中`。在解决完所有任务之前，状态会保持为`进行中`。解决完所有任务之后，计划的状态会更改为`完成`。

## 解决任务
{: #deployment_taskComplete}

通过解决部署计划中的任务来完成部署。当已启动任务的状态更改为`完成`、`失败`或`已跳过`时，说明该任务已解决。

可使用相应的状态操作来解决手动任务。自动任务（例如，UrbanCode Deploy 任务）在条件更改时会立即更改状态。不过，您也可以手动解决自动任务。例如，可手动使耗时太长而未完成的 UrbanCode Deploy 任务失败。

要解决已启动的任务，请应用以下某个状态：

<ul>
<li>单击**完成** <img class="inline" src="images/task-complete.png"  alt="“完成”任务操作"> 以完成任务。`完成`表示任务已完成，并返回预期的结果。
</li>
<li>单击**跳过** <img class="inline" src="images/task-skip.png"  alt="“跳过”任务操作"> 以跳过当前部署的任务。
</li>
<li>单击**失败** <img class="inline" src="images/task-fail.png"  alt="“失败”任务操作"> 以结束任务。`失败`表示任务未完成，或虽已完成，但返回意外的结果。
</li>
<li>单击**重新打开任务** <img class="inline" src="images/task-reopen.png"  alt="“重新打开任务”任务操作"> 以打开已解决的任务。如果所有任务均已完成，那么重新打开任务将重新打开部署。
</li>
</ul>

## 运行安排的部署
{: #deployment_startSchedule}

如果安排的部署中有任何自动任务符合启动条件，那么该部署会按安排时间自动启动。如果部署计划不包含任何符合启动条件的自动任务，请通过手动启动其中一个符合启动条件的任务来启动部署。

可以随时手动启动安排的部署，即便计划中有符合启动条件的自动任务也不例外。
