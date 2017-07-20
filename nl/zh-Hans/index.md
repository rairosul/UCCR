---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# Continuous Release 入门 (Beta)

{: #gettingstartedtemplate}

IBM {{site.data.keyword.Bluemix_short}} 上的 {{site.data.keyword.uccr_full}} 服务是一种综合发布管理解决方案。使用 {{site.data.keyword.uccr_short}}，可以在开发生命周期内运行所有软件应用程序的发布和部署。
{:shortdesc}

[创建 {{site.data.keyword.uccr_short}} 实例后](https://console.ng.bluemix.net/catalog/services/continuous-release/){:new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")，请选择开始方式。

* 如果要立即开始创建部署计划，请首先**[创建发布并运行部署](#gs_create_plan)**。

* 如果要将 {{site.data.keyword.uccr_short}} 与内部部署 IBM UrbanCode&trade; Deploy 实例相集成，请首先**[安装和配置 DevOps Connect](#gs_install_dc)**。配置集成后，可以使用 Continuous Release 任务来管理 UrbanCode Deploy 应用程序。


## 创建发布并运行部署
{: #gs_create_plan}

1. [创建发布](/docs/services/UCCR/UCCR_releases.html##releases_create)，并将其分配给您的其中一个团队。任何团队成员都可以针对该发布创建部署计划并运行部署。

1. 向发布添加部署计划。

  * [创建计划](/docs/services/UCCR/UCCR_releases.html#releases_planAdd)，并将其分配给发布。 

  * [向部署计划添加任务](/docs/services/UCCR/UCCR_tasks.html#tasks_create)。部署计划中列出的每个任务独占一行。请尝试添加不同类型的任务：手动、UrbanCode Deploy、Continuous Delivery Pipeline、延迟、电子邮件和 Slack。

  * 可以通过各种方式修改计划中的任务列表。您可以调整任务位置、复制任务和删除任务。 

4. 部署计划准备就绪时，请使用上一步中创建的部署计划来运行部署。

  * [通过解决部署计划中的任务来运行部署](/docs/services/UCCR/UCCR_deployRun.html)。解决任务的方式是启动任务，然后将其状态更改为`完成`、`失败`或`已跳过`。解决完部署计划中的所有任务后，部署的状态为“完成”。

  * 任务符合启动条件时即可启动。是否符合条件由计划的执行模式确定。缺省情况下，计划的执行模式为顺序。一开始，符合启动条件的是第一个（即顶端的）任务。可以通过对任务分组来修改执行模式。任务组可以有并行执行模式，这意味着组的任务可以按任意顺序启动并可同时运行。部署计划可以有多个组，也可以将一些组嵌套在其他组中。

  * 某些任务（称为自动任务）在符合运行条件后就会立即自动启动。UrbanCode Deploy 和 Continuous Delivery Pipeline 类型的任务在符合条件后就会立即启动，而无需手动干预。自动任务还会自行更新状态，而无需手动干预。  

## 安装和配置 DevOps Connect
{: #gs_install_dc}

IBM Bluemix DevOps Connect 用于协调内部部署 IBM UrbanCode Deploy 安装与 {{site.data.keyword.uccr_short}} 之间的通信。安装 DevOps Connect 后，可以创建集成，以支持使用 {{site.data.keyword.uccr_short}} 任务来管理 UrbanCode Deploy 应用程序。

**先决条件**

* 要注册 DevOps Connect，您必须具有 IBM 标识。

* 您必须在主机系统上具有 [Java™ Runtime Environment V7 或更高版本](https://java.com/en/download/){:new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")，并将系统的 PATH 变量设置为其位置。

* 您需要来自 UrbanCode Deploy 的管理授权令牌。   


1. 安装 DevOps Connect，并用于将 {{site.data.keyword.uccr_short}} 与 UrbanCode Deploy 相集成。

  1.  在 {{site.data.keyword.uccr_short}} 中的“入门”页面上，单击**设置**。

  1.  在 UrbanCode Deploy 的“集成设置”对话框中，单击**下载**以下载 DevOps Connect。将 JAR 文件放在有权访问 UrbanCode Deploy 的计算机上。

  1.  使用该对话框来复制 DevOps Connect 安装脚本。该脚本包含用于启动 DevOps Connect 的命令以及确定 {{site.data.keyword.uccr_short}} Bluemix 服务所必需的凭证。

  1.  在 DevOps Connect 所在的计算机上，打开命令 shell 并将复制的脚本粘贴到其中。

  1.  运行该脚本。DevOps Connect 会显示启动消息。

2. 注册 DevOps Connect。

  1.  使用 Web 浏览器来打开 DevOps Connect 仪表板。缺省 URL 为 `https://localhost:8443`。要更改 URL 并了解有关其他启动选项的信息，请参阅 [DevOps Connect文档](https://developer.ibm.com/urbancode/plugindoc/urbancode-sync/ibm-urbancode-sync-utility/1-2/){:new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

  1.  在注册页面上，指定 DevOps Connect 安装的名称。

  1.  单击**注册**。第一次访问 DevOps Connect 时，系统会提示您使用自己的 IBM 标识注册。

  1.  在**登录到 IBM** 页面上，输入您的 IBM 标识和密码，然后单击**登录**。每次启动 DevOps Connect 时都需要登录。

3. 通过 DevOps Connect，使用 IBM UrbanCode Deploy for Cloud Reporting 插件来创建 {{site.data.keyword.uccr_short}} 与 UrbanCode Deploy 的集成。

    1.  在 DevOps Connect 仪表板中，单击**集成**，然后单击**添加新项**。

    1.  在**名称**字段中，输入集成的名称。

    1.  从**集成类型**列表中，选择 **IBM UrbanCode Deploy for Cloud Reporting**。DevOps Connect 随附 IBM UrbanCode Deploy for Cloud Reporting 插件。

    1.  在**服务器 URI** 字段中，输入 UrbanCode Deploy 服务器的公共 URL。例如，`https://my_UCD.example.com:8447`。

    1.  在**认证令牌**字段中，输入或粘贴由 UrbanCode Deploy 生成的认证令牌。

    1.  在**管理用户电子邮件**字段中，输入您的电子邮件地址。

    1.  单击**保存**。

4.  运行集成以确认它是否有效。

    1.  在集成页面上，单击**运行**。DevOps Connect 会连接到**服务器 URI** 字段中指定的 UrbanCode Deploy 实例。DevOps Connect 由粘贴到**认证令牌**字段中的令牌授权。

    1.  在 {{site.data.keyword.uccr_short}} 中，通过创建 UrbanCode Deploy 类型的任务来确认集成是否成功。如果可以选择 UrbanCode Deploy 应用程序，说明集成成功。{{site.data.keyword.uccr_short}} 实例会使用 DevOps Connect 登录和启动参数来确定 UrbanCode Deploy 应用程序。  
