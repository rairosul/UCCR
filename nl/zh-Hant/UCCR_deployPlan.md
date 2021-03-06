---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---


<!-- Common attributes used in the template are defined as follows: -->
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# 管理部署計劃
{: #plan_overview}

部署計劃是作業的容器。作業會定義由團隊執行以完成軟體部署的活動。

{:shortdesc}

您可透過下列方式來建立部署計劃：指派團隊來管理計劃，然後在計劃中新增作業。團隊成員將作業新增至計劃中，並在部署期間執行作業。管理團隊也會判斷哪些 IBM UrbanCode Deploy 應用程式可供使用。運用 DevOps Connect 配置整合之後，即可在 {{site.data.keyword.uccr_short}} 中使用 IBM UrbanCode Deploy 的團隊所管理的所有應用程式。  

作業會定義由團隊執行以完成部署的活動。您可以建立新作業、複製其他部署計劃中的作業，或從 CSV 檔案匯入作業。當計劃符合您的要求時，您即可排定部署。您也可以透過啟動計劃的其中一個作業，來隨時執行部署。

作業會顯示在部署計劃的個別列上。每一列都會包含可識別作業的資訊並提供其狀態。每一列也都會包含部署期間所使用的動作圖示，例如**啟動**作業或**跳過**作業

依預設，作業會從計劃中的第一個作業或最前面的作業開始循序執行。第一個作業完成之後，才能執行第二個作業，依此類推。作業有資格執行的順序稱為執行順序。

您可以將作業結合為群組，來修改執行順序。[當您建立群組時](/docs/services/UCCR/UCCR_tasks.html#tasks_groups)，會設定群組的執行型樣（循序或平行）。如果群組具有循序執行型樣，則會從第一個作業開始循序執行其作業。部署計劃的預設執行型樣是循序。如果群組具有平行執行型樣，則可以依任何順序啟動群組中的作業，且可以同步執行。如果計劃完全由平行作業組成，則您可以啟動任何作業，而不論它在清單中的位置為何。

作業資格也會受到作業相依關係的影響。[如果作業具有任何必要條件](/docs/services/UCCR/UCCR_tasks.html#tasks_dependencies)，則在解決所有必要作業之前將無法啟動作業，即使作業符合其他資格。

有些作業會在有資格執行時立即自動啟動，而其他作業則為手動啟動。不論作業是否自動啟動，都會相依於其類型。顧名思義，手動作業是以手動方式予以啟動。UrbanCode Deploy 及延遲類型作業會在有資格執行時立即自動啟動。

合格作業會顯示**啟動作業**按鈕。若要啟動部署，請啟動計劃的其中一個合格作業。如果合格作業是可自動啟動的類型（例如 UrbanCode Deploy），則排程的部署會在排程的時間自動啟動。

## 建立部署計劃
{: #plan_create}
您可以從未定義作業的空白計劃開始，或是複製現有計劃。您也可以從計劃範本開始。當您複製計劃或使用範本時，即已定義數個作業。

請完成下列步驟來建立部署計劃：

1. 在「版本」頁面或「版本詳細資料」頁面上，按一下**建立部署計劃**。

2. 在「建立部署計劃」視窗中，於**範本**清單中，指定要作為計劃基礎的範本。預設值是**無**。

2. 在**計劃名稱**欄位中，輸入計劃名稱。

3. 在**團隊**清單中，選取要管理計劃的團隊。您所屬的所有團隊皆可供使用。團隊成員可以修改計劃，以及管理作業。UrbanCode Deploy 中的團隊所管理的 UrbanCode Deploy 應用程式可以指派給 UrbanCode Deploy 類型作業。

4. 若要排定計劃的部署，請按一下**開始時間**，然後選取部署的日期和時間。如果計劃包含合格自動作業，則排程的部署會在排程的時間自動啟動。您可以排定任何未來時間的部署。

5. 在**版本**清單中，選取您要在其中新增計劃的版本。屬於您的其中一個團隊的版本皆可供使用。如果您選取版本，部署計劃即會顯示在「版本詳細資料」頁面上。

6. 按一下**儲存**。如果您已在「版本詳細資料」頁面上建立計劃，則計劃屬於所選取的版本。

在您儲存計劃之後，請按一下**編輯**，以修改計劃詳細資料。

## 將作業匯入部署計劃
{: #plan_importTasks}

您可以將逗點區隔值 (CSV) 檔案中所定義的作業匯入至部署計劃。您可以使用從 IBM UrbanCode Release 或另一個可建立 CSV 檔案的應用程式匯入的 CSV 檔案。

**重要事項：**當您匯入作業時，會改寫部署計劃中已定義的作業並取代為 CSV 檔案中的作業。

請完成下列步驟，以將作業匯入至部署計劃。

1. 在「部署計劃詳細資料」頁面上，按一下**匯入作業**。

3. 在「匯入作業」對話框中，按一下**選擇檔案**，然後選取 CSV 檔案。您也可以將檔案拖曳至**選擇檔案**欄位。

6. 按一下**匯入**。即會將作業新增至部署計劃。如果匯入處理程序未成功，請按一下**檢視報告**以顯示錯誤日誌。

當您從 IBM UrbanCode Release 匯入部署計劃時，會將區段轉換為執行型樣與原始區段相同的群組。將區段作業括上 note-type「開始區段」及「結束區段」作業。在匯入期間會保留作業相依關係。區段相依關係是以與「結束區段」作業的相依關係代表。

下表包含在 IBM UrbanCode Release 部署計劃中定義作業的欄位。CSV 檔案中的第一列會包含直欄標頭，而其對應至表格的**欄位**直欄。第一列後面的列會包含作業資料，一列一個作業。直欄的順序並不重要。

若要瞭解從 IBM UrbanCode Release 匯出的部署計劃，請從「匯入作業」對話框中下載 `SamplePlan.csv` 檔案。

如果您要以 CSV 檔案建立作業，則必須包括下表中以星號字元 (*) 識別的必要欄位。

| 欄位  | 說明  |
| ------------------ |------------------|
|segmentName*                 |名稱區段。必要欄位。|                                                    
|name*                        |部署作業的名稱。必要欄位。|                                                                
|type*                        |作業類型。可能的值為 `note`、`waitfortimetask`、`ucdtask` 或 `manual`。在匯入期間，如果欄位包含無法辨識的值，則作業會獲指派 manual 類型。|
|description                 |部署計劃的說明。|                                                                                                    
|property:processId           |IBM UrbanCode Deploy 中對應至作業的處理程序 ID。|
|property:task-environments   |作業可用的應用程式環境。|
|property:mailRecipients|傳送通知時，接收電子郵件訊息之使用者的電子郵件位址。|
|taskTagNames                 |與作業相關聯之標籤的名稱。|
|taskPrequisiteIds         |必須完成才能啟動此作業之作業的 ID 清單（以逗點區隔）。|
|segmentPrerequisitelds       |與現行區段具有相依關係之區段的 ID 清單（以逗點區隔）。|
|taskPrequisiteNames         |必須完成才能啟動此作業之作業的名稱清單（以逗點區隔）。|
|segmentPrerequisiteNames       |與現行區段具有相依關係之區段的名稱清單（以逗點區隔）。|
|assignedUserEmail                |指派給現行作業之使用者的電子郵件位址。|
|executorGroup                |指派給現行作業的使用者群組。|
|segmentPattern                |所選取區段的執行型樣。|

{: caption="表 1. IBM UrbanCode Release 部署計劃欄位" caption-side="top"}

## 複製及提升部署計劃
{: #plan_copyPromote}

您可以透過提升及複製部署計劃來進行複製。已複製或已提升計劃的狀態為 `draft`，即使原始計劃的狀態為 `done` 或 `in progress`。

若要複製計劃，請使用「部署計劃」頁面上的**複製此計劃**動作。當您複製計劃時，會將名稱為「`plan_name` 副本」的新計劃插入「部署計劃」頁面中。複製的計劃包含原始計劃中定義的所有作業。如果 UrbanCode Deploy 作業在計劃中，則也會在複製的計劃中選取原始計劃中所選取的應用程式、版本及環境。應用程式、版本及環境會顯示在「部署計劃詳細資料」頁面的**版本**標籤上。

若要提升計劃，請使用「部署計劃」頁面上的**提升此計劃**動作。當您提升計劃時，會將名稱為「`plan_name` 提升」的新計劃插入「部署計劃」頁面中。提升的計劃包含原始計劃中定義的所有作業。如果 UrbanCode Deploy 作業在計劃中，則也會在提升的計劃中選取原始計劃中所選取的應用程式及版本。複製的計劃與提升的計劃之間的差異，在於提升的計劃中未設定應用程式版本。

## 管理計劃範本
{: #plan_templates}

您可以轉換部署計劃來建立部署計劃範本。

若要建立範本，請使用「部署計劃」頁面上的**建立此計劃的範本**動作。當您建立範本時，會將名稱為「plan_name 副本」的新計劃插入「部署計劃」頁面中。範本的狀態為 `template`，即使原始計劃的狀態為 `done` 或 `in progress`。範本包含原始計劃中定義的所有作業。如果 UrbanCode Deploy 作業在計劃中，則也會在範本中選取原始計劃中所選取的應用程式。

您無法使用範本來執行部署。若要使用部署的範本，請先複製或提升它，然後使用複製的計劃或提升的計劃。

## 保存部署計劃
{: #plan_arch}

當您將部署計劃放在保存檔中時，計劃的狀態為 `Archived`，而且不會顯示在「部署計劃」頁面中，除非您使用**保存檔**過濾器。

保存檔中的部署計劃可以還原為 `draft` 狀態。您無法永久刪除部署計劃。

## 回復及還原
{: #plan_history}

會維護每個部署計劃的變更及修訂歷程。您可以在「部署計劃詳細資料」頁面的**變更歷程**標籤上顯示修訂。

若要回復為先前的計劃版本，請針對您要還原的版本使用**還原**動作 <img class="inline" src="images/restore-icon.png"  alt="還原動作">。計劃即會還原為選取的版本。  

## 預估部署時間
{: #plan_durationEst}

開始部署之前，您可以預估其預期持續時間。若要預估持續時間，請使用「部署計劃詳細資料」頁面上的**預估作業時間**動作。顯示的時間代表您現在就啟動部署的部署結束時間。
