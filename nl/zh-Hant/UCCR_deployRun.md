---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# 執行部署
{: #deployment_run}

請使用 {{site.data.keyword.uccr_short}} 來執行軟體部署。您可以透過解決部署計劃中的作業，來完成部署。
{:shortdesc}

啟動計劃的其中一個合格作業時，部署即會啟動。如果排程部署的其中一個合格作業是自動作業（例如 UrbanCode Deploy 或延遲類型作業），則排程的部署會在排程的時間自動啟動。否則，請啟動計劃的其中一個合格作業來開始部署。如果計劃包含數個合格作業，您可以啟動其中任何一個。您隨時可以手動啟動部署。您可以在排程的時間之前手動啟動排程的部署。   

部署計劃的執行型樣決定何時可啟動作業。如果計劃具有循序執行型樣（即預設型樣），則作業會從第一個作業開始依其列在計劃中的順序變成合格。第一個作業解決之後，第二個作業就會變成合格。按一下合格手動作業的**啟動**按鈕，以啟動作業。自動作業（例如 UrbanCode Deploy 作業）會在變成合格時立即自動啟動。

具有平行執行型樣之群組中的作業會同時變成合格。平行群組中的作業可以依任何順序啟動。具有特定相依關係的巢狀群組及作業可能會影響執行型樣。

在您啟動部署之後，可以修改部署計劃。您可以新增、刪除及修改作業。

解決所有作業之後，部署即已完成。如果作業的狀態為 `Complete`、`Failed` 或 `Skipped`，即已解決作業。如果您在部署完成之後重新開啟作業或新增作業，則部署的狀態會變更為 `In Progress`。

## 手動啟動部署
{: #deployment_start}

您隨時可以手動啟動部署（包括排程在稍後啟動的部署）。

部署計劃中的作業可能不適用於部署。如果未指定作業的版本或環境，則 UrbanCode Deploy 作業不適用。當您建立 UrbanCode Deploy 作業時，可以使用**使用版本**選項來延遲選取環境及版本。在啟動部署之前，請確定所有 UrbanCode Deploy 作業都適用於未來的部署。    

您可以故意排除作業不進行部署。您可以將標籤作業設為不適用，方法是排除其標籤不進行部署。具有已排除標籤的作業不適用於部署。  

不適用作業的狀態為 `Not Applicable`。無法啟動狀態為 `Not Applicable` 的作業。如果不適用作業是作用中作業的必要條件，則會忽略相依關係。  

若要啟動部署，請完成下列步驟：

1. 在「部署計劃」頁面上，按一下您要用於部署的部署計劃。即會顯示部署詳細資料頁面。

2. 若要讓標籤作業不適用於現行部署，請按一下**版本**，然後清除**標籤**區域中的標籤。如果作業有多個標籤，請將它們全部清除。

2. 若要選取任何不適用 UrbanCode Deploy 作業的版本或環境，請按一下**版本**，然後選取環境及版本。您也可以變更針對已選取其環境及版本的作業所做的選擇。

1. 您可以選擇按一下**隱藏不適用作業**，以從顯示的作業清單中移除不適用作業。不會從部署計劃中移除隱藏的作業。

1. 針對計劃的其中一個合格作業，按一下**啟動**動作 <img class="inline" src="images/task-start.png"  alt="啟動作業動作">。如果有多個作業合格，您可以啟動其中任何一個。只有合格作業才會顯示啟動按鈕。已啟動的作業在解決之前的狀態都是 `In Progress`。

啟動部署之後，計劃的狀態會變更為 `In Progress`。在解決所有作業之前，狀態都仍是 `In Progress`。解決所有作業後，計劃的狀態會變更為 `Done`。

## 解決作業
{: #deployment_taskComplete}

您可以透過解決部署計劃中的作業，來完成部署。已啟動作業的狀態變更為 `Complete`、`Failed` 或 `Skipped` 時，即已解決已啟動的作業。

您可以使用適當的狀態動作，來解決手動作業。自動作業（例如 UrbanCode Deploy 作業）會在狀況變更時自動變更狀態。不過，您可以手動解決自動作業。例如，您可以手動讓需要太長時間才能完成的 UrbanCode Deploy 作業失敗。

若要解決已啟動的作業，請套用下列其中一種狀態：

<ul>
<li>按一下**完成** <img class="inline" src="images/task-complete.png"  alt="完成作業動作">，以完成作業。`Complete` 表示作業已完成，並且具有預期結果。
</li>
<li>按一下**跳過** <img class="inline" src="images/task-skip.png"  alt="跳過作業動作">，以跳過現行部署的作業。
</li>
<li>按一下**失敗** <img class="inline" src="images/task-fail.png"  alt="失敗作業動作">，以結束作業。`Fail` 表示作業未完成，或已完成但具有非預期的結果。
</li>
<li>按一下**作業重新開啟** <img class="inline" src="images/task-reopen.png"  alt="作業重新開啟作業動作">，以開啟已解決的作業。如果所有作業都已完成，則重新開啟作業即會重新開啟部署。
</li>
</ul>

## 執行排程的部署
{: #deployment_startSchedule}

如果可以啟動排程部署的任何自動作業，則排程的部署會在排程的時間自動啟動。如果部署計劃未包含任何合格自動作業，請手動啟動其中一個合格作業來啟動部署。

您隨時可以手動啟動排程的部署，即使計劃具有合格自動作業。
