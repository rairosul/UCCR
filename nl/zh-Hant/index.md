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


# 開始使用 Continuous Release（測試版）

{: #gettingstartedtemplate}

IBM {{site.data.keyword.Bluemix_short}} 上的 {{site.data.keyword.uccr_full}} 服務是綜合性版本管理解決方案。使用 {{site.data.keyword.uccr_short}}，您可以為開發生命週期中的所有軟體應用程式，執行版本及部署。
{:shortdesc}

[建立 {{site.data.keyword.uccr_short}} 的實例之後](https://console.ng.bluemix.net/catalog/services/continuous-release/){:new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")，選擇您要如何開始使用。

* 如果您想要全心投入，開始建立部署計劃，請從**[建立版本及執行部署](#gs_create_plan)**開始。

* 如果您想要整合 {{site.data.keyword.uccr_short}} 與內部部署的 IBM UrbanCode&trade; Deploy 實例，請從**[安裝及配置 DevOps Connect](#gs_install_dc)** 開始。配置整合之後，您可以使用 Continuous Release 作業來管理 UrbanCode Deploy 應用程式。


## 建立版本及執行部署
{: #gs_create_plan}

1. [建立版本](/docs/services/UCCR/UCCR_releases.html##releases_create)，並將它指派給您的其中一個團隊。任何團隊成員都可以建立版本的部署計劃並執行部署。

1. 將部署計劃新增至版本。

  * [建立計劃](/docs/services/UCCR/UCCR_releases.html#releases_planAdd)，並將它指派給版本。 

  * [將作業新增至部署計劃](/docs/services/UCCR/UCCR_tasks.html#tasks_create)。每一項作業都會列在部署計劃中的個別列上。請嘗試新增不同類型的作業：手動、UrbanCode Deploy、Continuous Delivery 管線、延遲、電子郵件及 Slack。

  * 您可以使用各種方式來修改計劃中的作業清單。您可以重新定位作業、複製作業及刪除作業。 

4. 部署計劃備妥之後，使用您在前一個步驟中建立的部署計劃來執行部署。

  * [您可以透過解決部署計劃中的作業來執行部署](/docs/services/UCCR/UCCR_deployRun.html)。解決作業的方式是啟動作業，然後將其狀態變更為 `Complete`、`Fail` 或 `Skipped`。在部署計劃中的所有作業都解決之後，部署的狀態為 Done。

  * 作業可以在它們有資格啟動時啟動。資格是由計劃的執行型樣所決定。依預設，計劃的執行型樣是循序。一開始，第一個（或最前面的）作業有資格啟動。您可以將作業分組，以修改執行型樣。作業群組可具有平行執行型樣，這表示群組的作業可以依任何順序啟動，且可以同步執行。部署計劃可以有多個群組，以及巢狀位於其他群組內的群組。

  * 有些作業（稱為自動作業）會在有資格執行時立即自動啟動。UrbanCode Deploy 及 Continuous Delivery 管線類型作業會在有資格執行時立即啟動，不需要人為介入。自動作業也會更新其狀態，而無需人為介入。  

## 安裝及配置 DevOps Connect
{: #gs_install_dc}

IBM Bluemix DevOps Connect 會協調內部部署 IBM UrbanCode Deploy 安裝與 {{site.data.keyword.uccr_short}} 之間的通訊。安裝 DevOps Connect 之後，您可以建立整合，以使用 {{site.data.keyword.uccr_short}} 作業來管理 UrbanCode Deploy 應用程式。

**必要條件**

* 若要登錄 DevOps Connect，您必須具有 IBM ID。

* 在主機系統上必須具有 [Java™ Runtime Environment 第 7 版或更新版本](https://java.com/en/download/){:new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")，並將系統 PATH 變數設定為其位置。

* 您需要來自 UrbanCode Deploy 的管理授權記號。   


1. 安裝 DevOps Connect，然後用它來整合 {{site.data.keyword.uccr_short}} 與 UrbanCode Deploy。

  1.  在 {{site.data.keyword.uccr_short}} 的「開始使用」頁面上，按一下**設定**。

  1.  在「UrbanCode Deploy 整合設定」對話框中，按一下**下載**，以下載 DevOps Connect。將 JAR 檔放在可存取 UrbanCode Deploy 的電腦上。

  1.  使用對話框，複製 DevOps Connect 安裝 Script。Script 包含用來啟動 DevOps Connect 的指令，以及識別 {{site.data.keyword.uccr_short}} Bluemix 服務所需的認證。

  1.  在您放置 DevOps Connect 的電腦上，開啟指令 Shell 並將複製的 Script 貼入其中。

  1.  執行 Script。DevOps Connect 會顯示啟動訊息。

2. 登錄 DevOps Connect。

  1.  使用 Web 瀏覽器來開啟 DevOps Connect 儀表板。預設 URL 是 `https://localhost:8443`。若要變更 URL 並瞭解其他啟動選項，請參閱 [DevOps Connect 文件](https://developer.ibm.com/urbancode/plugindoc/urbancode-sync/ibm-urbancode-sync-utility/1-2/){:new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")。

  1.  在登錄頁面上，指定 DevOps Connect 安裝的名稱。

  1.  按一下**登錄**。第一次存取 DevOps Connect 時，您會收到提示，要求您使用 IBM ID 登錄它。

  1.  在**登入 IBM** 頁面上，輸入您的 IBM ID 及密碼，然後按一下**登入**。每次啟動 DevOps Connect 時都要登入。

3. 運用 DevOps Connect，使用 IBM UrbanCode Deploy for Cloud Reporting 外掛程式來建立 {{site.data.keyword.uccr_short}} 與 UrbanCode Deploy 之間的整合。

    1.  從 DevOps Connect 儀表板中，按一下**整合**，然後按一下**新增**。

    1.  在**名稱**欄位中，輸入整合的名稱。

    1.  從**整合類型**清單中，選取 **IBM UrbanCode Deploy for Cloud Reporting**。IBM UrbanCode Deploy for Cloud Reporting 外掛程式內含在 DevOps Connect 中。

    1.  在**伺服器 URI** 欄位中，輸入 UrbanCode Deploy 伺服器的公用 URL。例如，`https://my_UCD.example.com:8447`。

    1.  在**鑑別記號**欄位中，輸入或貼上 UrbanCode Deploy 產生的鑑別記號。

    1.  在**管理使用者電子郵件**欄位中，輸入您的電子郵件位址。

    1.  按一下**儲存**。

4.  執行整合，以確認它可運作。

    1.  在整合頁面上，按一下**執行**。DevOps Connect 會連接**伺服器 URI** 欄位中指定的 UrbanCode Deploy 實例。DevOps Connect 會由**鑑別記號**欄位中貼上的記號授權。

    1.  在 {{site.data.keyword.uccr_short}} 中，透過建立 UrbanCode Deploy 類型作業來確認整合成功。如果您可以選取 UrbanCode Deploy 應用程式，即表示整合成功。{{site.data.keyword.uccr_short}} 實例使用 DevOps Connect 登入及啟動參數，以識別 UrbanCode Deploy 應用程式。  
