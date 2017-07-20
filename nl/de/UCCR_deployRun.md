---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Bereitstellungen ausführen
{: #deployment_run}

Verwenden Sie {{site.data.keyword.uccr_short}}, um Softwarebereitstellungen auszuführen. Zum Abschließen von Bereitstellungen werden die Tasks in einem Bereitstellungsplan aufgelöst.
{:shortdesc}

Eine Bereitstellung beginnt, wenn eine der für die Ausführung infrage kommenden Tasks des zugehörigen Bereitstellungsplans gestartet wird. Eine geplante Bereitstellung wird am geplanten Zeitpunkt automatisch gestartet, wenn eine der zugehörigen und für die Ausführung infrage kommenden Tasks eine automatische Task (z. B. vom Typ 'UrbanCode Deploy' oder 'Delayed') ist. Andernfalls können Sie eine Bereitstellung starten, indem Sie eine der für die Ausführung infrage kommenden Tasks aus dem zugehörigen Plan starten. Wenn der Plan mehrere infrage kommende Tasks enthält, können Sie beliebige dieser Tasks starten. Sie können eine Bereitstellung jederzeit manuell starten. Eine geplante Bereitstellung kann vor dem geplanten Zeitpunkt manuell gestartet werden.   

Das Ausführungsmuster des Bereitstellungsplans bestimmt, wann Tasks für die Ausführung infrage kommen. Wenn für den Plan die sequenzielle Ausführung vorgesehen ist (dies ist die Standardeinstellung), kommen Tasks in der im Plan angegebenen Reihenfolge (beginnend mit der ersten Task) für die Ausführung infrage. Nachdem die erste Task abgeschlossen ist, kommt die zweite Task für die Ausführung infrage. Starten Sie eine für die Ausführung infrage kommende Task durch Klicken auf die zugehörige Schaltfläche **Starten**. Automatische Tasks (z. B. Tasks vom Typ 'UrbanCode Deploy') werden automatisch gestartet, sobald sie für die Ausführung infrage kommen.

Die Tasks in einer Gruppe, die für die parallele Ausführung vorgesehen ist, kommen gleichzeitig für die Ausführung infrage. Die Tasks in Gruppen mit paralleler Ausführung können in jeder beliebigen Reihenfolge gestartet werden. Verschachtelte Gruppen und Tasks mit Ad-hoc-Abhängigkeiten können das Ausführungsmuster verändern.

Ein Bereitstellungsplan kann nach dem Starten einer Bereitstellung geändert werden. Sie können Tasks hinzufügen, löschen und ändern.

Nachdem alle Tasks aufgelöst wurden, ist die Bereitstellung abgeschlossen. Eine Task ist aufgelöst, wenn sie den Status `Abgeschlossen`, `Fehlgeschlagen` oder `Übersprungen` aufweist. Wenn Sie eine Task erneut öffnen oder nach Beendigung der Bereitstellung eine Task hinzufügen, wird der Status der Bereitstellung in `In Bearbeitung` geändert.

## Bereitstellungen manuell starten
{: #deployment_start}

Sie können eine Bereitstellung jederzeit manuell starten. Dies gilt auch für Bereitstellungen, deren Ausführung für einen späteren Zeitpunkt geplant ist.

Ein Bereitstellungsplan kann Tasks enthalten, die für die Bereitstellung nicht anwendbar sind. Tasks vom Typ 'UrbanCode Deploy' sind nicht anwendbar, wenn für die Tasks keine Version oder Umgebung angegeben ist. Beim Erstellen von Tasks des Typs 'UrbanCode Deploy' können Sie das Auswählen der Umgebung und der Version mithilfe der Option **Version verwenden** verzögern. Stellen Sie vor Beginn der Bereitstellung sicher, dass alle Tasks des Typs  'UrbanCode Deploy' für die anstehende Bereitstellung anwendbar sind.    

Sie können Tasks gezielt aus einer Bereitstellung ausschließen. Sie können mit Tags versehene Tasks nicht anwendbar machen, indem sie die zugehörigen Tags aus der Bereitstellung ausschließen. Tasks, die über ausgeschlossene Tags verfügen, sind für die Bereitstellung nicht anwendbar.  

Nicht anwendbaren Tasks wird der Status `Nicht zutreffend` zugewiesen. Tasks mit dem Status `Nicht zutreffend` können nicht gestartet werden. Wenn eine nicht anwendbare Task die Voraussetzung für eine aktive Task ist, wird diese Abhängigkeit ignoriert.  

Führen Sie die folgenden Schritte aus, um eine Bereitstellung zu starten:

1. Klicken Sie auf der Seite 'Bereitstellungspläne' auf den Bereitstellungsplan, den Sie für die Bereitstellung verwenden möchten. Die Seite mit den Bereitstellungsdetails wird angezeigt.

2. Um mit Tags versehene Tasks für die aktuelle Bereitstellung nicht anwendbar zu machen, klicken Sie auf **Versionen** und löschen Sie anschließend die Tags im Bereich **Tags**. Wenn einer Task mehrere Tags zugeordnet sind, löschen Sie alle Tags.

2. Um die Version oder die Umgebung für beliebige, nicht anwendbare Tasks des Typs 'UrbanCode Deploy' auszuwählen, klicken Sie auf **Versionen** und wählen Sie anschließend die Umgebung und die Version aus. Außerdem können Sie die Auswahlen für Tasks ändern, für die bereits Umgebungen und Versionen ausgewählt sind.

1. Optional: Klicken Sie auf **Nicht anwendbare Tasks ausblenden**, um nicht anwendbare Tasks in der angezeigten Taskliste zu entfernen. Ausgeblendete Tasks werden nicht aus dem Bereitstellungsplan entfernt.

1. Klicken Sie auf die Aktion **Starten** <img class="inline" src="images/task-start.png"  alt="Aktion 'Task starten'"> für eine der für die Ausführung infrage kommenden Tasks in dem Plan. Wenn mehrere Tasks für die Ausführung infrage kommen, können Sie eine beliebige Anzahl dieser Tasks starten. Die Schaltfläche 'Starten' wird nur für infrage kommende Tasks angezeigt. Ein gestartete Task wird in den Status `In Bearbeitung` versetzt, bis sie aufgelöst ist.

Nach dem Starten der Bereitstellung wird der Status des Plans in `In Bearbeitung` geändert. Der Status `In Bearbeitung` bleibt aktiv, bis alle Tasks aufgelöst sind. Sobald alle Tasks aufgelöst sind, wird der Plan in den Status `Fertig` versetzt.

## Tasks auflösen
{: #deployment_taskComplete}

Zum Abschließen einer Bereitstellung müssen die Tasks im zugehörigen Bereitstellungsplan aufgelöst werden. Eine gestartete Task gilt als aufgelöst, wenn die Task den Status `Abgeschlossen`, `Fehlgeschlagen` oder `Übersprungen` aufweist.

Manuelle Tasks können mit der entsprechenden Statusaktion aufgelöst werden. Für automatische Tasks (z. B. Tasks vom Typ 'UrbanCode Deploy') wird der Status automatisch geändert, wenn sich die Bedingungen ändern. Sie können automatische Tasks jedoch auch manuell auflösen. Beispielsweise kann eine Task des Typs 'UrbanCode Deploy' manuell in den Status 'Fehlgeschlagen' versetzt werden, wenn das Abschließen der Task zu lange dauert.

Aktivieren Sie einen der folgenden Statuswerte, um eine gestartete Task aufzulösen:

<ul>
<li>Klicken Sie auf **Abschließen** <img class="inline" src="images/task-complete.png"  alt="Aktion 'Task abschließen'">, um eine Task zu beenden. `Abschließen` bedeutet, dass die Task mit den erwarteten Ergebnissen beendet wurde.
</li>
<li>Klicken Sie auf **Überspringen** <img class="inline" src="images/task-skip.png"  alt="Aktion 'Task überspringen'">, um eine Task in der aktuellen Bereitstellung zu überspringen.
</li>
<li>Klicken Sie auf **Fehlgeschlagen** <img class="inline" src="images/task-fail.png"  alt="Aktion 'Task fehlgeschlagen'">, um eine Task zu beenden. `Fehlgeschlagen` bedeutet, dass die Task nicht oder mit nicht erwarteten Ergebnissen beendet wurde.
</li>
<li>Klicken Sie auf **Task erneut öffnen** <img class="inline" src="images/task-reopen.png"  alt="Aktion 'Task erneut öffnen'">, um eine aufgelöste Task wieder zu öffnen. Wenn alle Tasks abgeschlossen sind, wird durch das erneute Öffnen einer Task die Bereitstellung erneut geöffnet.
</li>
</ul>

## Geplante Bereitstellungen ausführen
{: #deployment_startSchedule}

Eine geplante Bereitstellung wird automatisch an dem geplanten Zeitpunkt gestartet, sofern mindestens eine der zugehörigen automatischen Tasks für die Ausführung infrage kommt. Wenn ein Bereitstellungsplan keine für die Ausführung infrage kommenden, automatischen Tasks enthält, können Sie die Bereitstellung starten, indem Sie eine der infrage kommenden Tasks manuell starten.

Eine geplante Bereitstellung kann jederzeit manuell gestartet werden, selbst wenn der Plan infrage kommende automatische Tasks enthält.
