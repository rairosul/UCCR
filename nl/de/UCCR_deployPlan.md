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

# Bereitstellungspläne verwalten
{: #plan_overview}

Ein Bereitstellungsplan ist ein Container für Tasks. Tasks definieren die Aktivitäten, die von Ihrem Team ausgeführt werden, um eine Softwarebereitstellung abzuschließen.

{:shortdesc}

Um einen Bereitstellungsplan zu erstellen, ordnen Sie ein Team zum Verwalten des Plans zu und fügen anschließend Tasks zu dem Plan hinzu. Mitglieder des Teams fügen Tasks zu dem Plan hinzu und führen die Bereitstellungstasks aus. Das Verwaltungsteam legt außerdem fest, welche IBM UrbanCode Deploy-Anwendungen zur Verfügung stehen. Nach dem Konfigurieren einer Integration in DevOps Connect sind alle Anwendungen, die von dem Team in IBM UrbanCode Deploy verwaltetet werden, in {{site.data.keyword.uccr_short}} verfügbar.  

Die Tasks definieren, welche Aktivitäten von dem Team ausgeführt werden, um eine Bereitstellung abzuschließen. Sie können neue Tasks erstellen, Tasks aus anderen Bereitstellungsplänen kopieren oder Tasks aus CSV-Dateien importieren. Wenn der Plan Ihren Vorstellungen entspricht, können Sie eine Bereitstellung planen. Außerdem können Sie jederzeit eine Bereitstellung durchführen, indem Sie eine der zugehörigen Tasks des Plans starten.

Die zugehörigen Tasks in Bereitstellungsplänen werden in separaten Zeilen angezeigt. Jede Zeile enthält Informationen zum Identifizieren der Task und gibt den Status der Task an. Außerdem enthält jede Zeile Aktionssymbole, die in Bereitstellungen verwendet werden, z. B. zum **Starten** oder **Überspringen** einer Task.

Tasks werden standardmäßig in sequenzieller Reihenfolge ausgeführt, beginnend mit der ersten (obersten) Task des Bereitstellungsplans. Nach Beendigung der ersten Task kommt die zweite Task für die Ausführung infrage usw. Die Reihenfolge, in der die Tasks ausgeführt werden, wird als Ausführungsreihenfolge bezeichnet.

Die Ausführungsreihenfolge kann geändert werden, indem Tasks zu Gruppen zusammengefasst werden. Wenn Sie eine [Gruppe erstellen](/docs/services/UCCR/UCCR_tasks.html#tasks_groups), legen Sie fest, ob die Gruppe sequenziell oder parallel ausgeführt wird (Ausführungsmuster). Die Tasks einer Gruppe mit sequenziellem Ausführungsmuster werden nacheinander ausgeführt, beginnend mit der ersten Task. Ein Bereitstellungsplan wird standardmäßig sequenziell ausgeführt. Die zugehörigen Tasks einer Gruppe mit parallelem Ausführungsmuster können in beliebiger Reihenfolge gestartet und gleichzeitig ausgeführt werden. Wenn ein Plan ausschließlich parallele Tasks enthält, können Sie jede beliebige Task (unabhängig von der Position in der Taskliste) starten.

Ob eine Task für die Ausführung infrage kommt, kann auch durch Taskabhängigkeiten beeinflusst werden. [Wenn eine Task über Voraussetzungen verfügt](/docs/services/UCCR/UCCR_tasks.html#tasks_dependencies), kann sie erst gestartet werden, sobald alle vorausgesetzten Tasks abgeschlossen (aufgelöst) sind, selbst wenn sie ansonsten für die Ausführung infrage kommt.

Manche Tasks werden automatisch gestartet, sobald sie für die Ausführung infrage kommen, andere Tasks werden manuell gestartet. Ob eine Task automatisch gestartet wird oder nicht, hängt vom Tasktyp ab. Tasks des Typs 'Manuell' werden (wie der Name schon sagt) manuell gestartet. Tasks der Typen 'UrbanCode Deploy' und 'Verzögert' werden automatisch gestartet, sobald sie für die Ausführung infrage kommen.

Für Tasks, die für die Ausführung infrage kommen, wird eine Schaltfläche **Task starten** angezeigt. Um eine Bereitstellung zu starten, starten Sie eine der für die Ausführung infrage kommenden Tasks in einem Plan. Geplante Bereitstellungen werden am geplanten Zeitpunkt automatisch gestartet, sofern die für die Ausführung infrage kommende Task einen Typ aufweist, der automatisch gestartet werden kann (z. B. UrbanCopy Deploy).

## Bereitstellungspläne erstellen
{: #plan_create}
Sie können mit einem leeren Plan ohne definierte Tasks beginnen oder einen bereits vorhandenen Plan kopieren. Alternativ können Sie mit einer Planvorlage beginnen. Ein kopierter Plan bzw. eine Vorlage enthält bereits definierte Tasks.

Führen Sie die folgenden Schritte aus, um einen Bereitstellungsplan zu erstellen:

1. Klicken Sie auf der Seite 'Releases' oder auf der Seite 'Releasedetails' auf **Bereitstellungsplan erstellen**.

2. Geben Sie auf der Seite 'Bereitstellungsplan erstellen' in der Liste **Vorlage** die Vorlage an, die als Grundlage für den Plan verwendet werden soll. Die Standardeinstellung ist **Ohne**.

2. Geben Sie in das Feld **Planname** den Namen für den Plan ein. 

3. Wählen Sie in der Liste **Team** ein Team aus, das den Plan verwalten soll. In der Liste sind alle Teams verfügbar, denen Sie als Mitglied angehören. Die Teammitglieder können den Plan ändern und Tasks verwalten. Die von dem betreffenden Team mit UrbanCode Deploy verwalteten UrbanCode Deploy-Anwendungen können den Tasks des Typs 'UrbanCode Deploy' zugewiesen werden.

4. Um eine Bereitstellung für den Plan zu konfigurieren, klicken Sie auf **Startzeit** und wählen Sie einen Zeitpunkt (Datum und Uhrzeit) für die Bereitstellung aus. Geplante Bereitstellungen werden am geplanten Zeitpunkt automatisch gestartet, wenn der Plan für die Ausführung infrage kommende automatische Tasks enthält. Sie können eine Bereitstellung zu einem beliebigen zukünftigen Zeitpunkt planen.

5. Wählen Sie in der Liste **Releases** das Release aus, zu dem der Plan hinzugefügt werden soll. Alle Releases, die einem Team zugeordnet sind, dem Sie angehören, sind verfügbar. Wenn Sie ein Release auswählen, wird der Bereitstellungsplan auf der zugehörigen Seite 'Releasedetails' angezeigt.

6. Klicken Sie auf **Speichern**. Wenn Sie den Plan auf einer Seite 'Releasedetails' erstellt haben, ist der Plan Teil des ausgewählten Release.

Nachdem Sie den Plan gespeichert haben, können Sie auf **Bearbeiten** klicken, um die Plandetails zu ändern.

## Tasks in Bereitstellungspläne importieren
{: #plan_importTasks}

Sie können Tasks, die in Dateien mit durch Kommas getrennten Werten (Comma-Separated Values, CSV) definiert sind, in einen Bereitstellungsplan importieren. Sie können CSV-Dateien verwenden, die aus IBM UrbanCode Release oder aus einer anderen Anwendung mit der Funktionalität zum Erstellen von CSV-Dateien exportiert wurden.

**Wichtig:** Beim Importieren von Tasks werden die bereits im Bereitstellungsplan definierten Tasks überschrieben und durch die Tasks aus der CSV-Datei ersetzt.

Führen Sie die folgenden Schritte aus, um Tasks in einen Bereitstellungsplan zu importieren.

1. Klicken Sie auf der Seite 'Bereitstellungsplandetails' auf **Tasks importieren**.

3. Klicken Sie im Dialogfeld 'Tasks importieren' auf **Datei auswählen** und wählen Sie anschließend die CSV-Datei aus. Sie können auch eine Datei in das Feld **Datei auswählen** ziehen.

6. Klicken Sie auf **Importieren**. Die Tasks werden zum Bereitstellungsplan hinzugefügt. Falls der Importprozess fehlschlägt, klicken Sie auf **Bericht anzeigen**, um das Fehlerprotokoll anzuzeigen.

Wenn Sie einen Bereitstellungsplan aus IBM UrbanCode Release importieren, werden Segmente in Gruppen mit demselben Ausführungsmuster wie die ursprünglichen Segmente umgewandelt. Segmenttasks werden in Segmentstart- und Segmentendetasks des Typs 'note' eingeschlossen. Taskabhängigkeiten bleiben beim Importieren erhalten. Segmentabhängigkeiten werden als Abhängigkeiten von Segmentendetasks dargestellt. 

Die folgende Tabelle enthält die Felder, die eine Task in einem IBM UrbanCode Release-Bereitstellungsplan definieren. Die erste Zeile in der CSV-Datei enthält die Spaltenüberschriften, die der Tabellenspalte **Feld** entsprechen. Die weiteren Spalten enthalten jeweils eine Zeile mit den Daten für eine bestimmte Task. Die Reihenfolge der Spalten ist nicht von Bedeutung.

Um weitere Informationen zu Bereitstellungsplänen, die aus IBM UrbanCode Release exportiert wurden, zu erhalten, laden Sie die im Dialogfeld 'Tasks importieren' angegebene Datei `SamplePlan.csv` herunter.

Beim Erstellen von Tasks in einer CSV-Datei müssen Sie die erforderlichen Felder einbeziehen, die in der folgenden Tabelle durch einen Stern (*) markiert sind.

| Feld   | Beschreibung |
| ------------------ |------------------|
|segmentName*                 |Der Name des Segments. Erforderliches Feld.|                                                    
|name*                        |Der Name der Bereitstellungstask. Erforderliches Feld.|                                                                
|type*                        |Der Tasktyp. Gültige Werte sind `note`, `waitfortimetask`, `ucdtask` oder `manual`. Beim Importieren wird der Task der Typ 'manual' zugewiesen, wenn das Feld einen nicht erkannten Wert enthält.|
|description                 |Eine Beschreibung des Bereitstellungsplans.|                                                                                                    
|property:processId           |Die Prozess-ID in IBM UrbanCode Deploy, die der Task entspricht.|
|property:task-environments   |Anwendungsumgebungen, die für die Task verfügbar sind.|
|property:mailRecipients|E-Mail-Adressen der Benutzer, die E-Mails erhalten, wenn Benachrichtigungen gesendet werden.|
|taskTagNames                 |Die Namen der zugeordneten Tags für die Task.|
|taskPrequisiteIds         |Durch Kommas getrennte Liste der IDs für Tasks, die abgeschlossen sein müssen, bevor diese Task gestartet werden kann.|
|segmentPrerequisitelds       |Durch Kommas getrennte Liste der IDs für Segmente, von denen das aktuelle Segment abhängig ist.|
|taskPrequisiteNames         |Durch Kommas getrennte Liste mit den Namen der Tasks, die abgeschlossen sein müssen, bevor diese Task gestartet werden kann.|
|segmentPrerequisiteNames       |Durch Kommas getrennte Liste der Namen für Segmente, von denen das aktuelle Segment abhängig ist.|
|assignedUserEmail                |Die E-Mail-Adresse des Benutzers, dem die aktuelle Task zugeordnet ist.|
|executorGroup                |Die Benutzergruppe, der die aktuelle Task zugeordnet ist.|
|segmentPattern                |Das Ausführungsmuster für das ausgewählte Segment.|

{: caption="Tabelle 1. Bereitstellungsplanfelder in IBM UrbanCode Release" caption-side="top"}

## Bereitstellungspläne kopieren und umstufen
{: #plan_copyPromote}

Sie können Bereitstellungspläne kopieren und umstufen, um Duplikate zu erstellen. Einem kopierten oder umgestuften Plan wird der Status `Entwurf` zugewiesen, selbst wenn der ursprüngliche Plan den Status `Fertig` oder `In Bearbeitung` aufweist.

Verwenden Sie zum Kopieren eines Plans die Aktion **Plan kopieren** auf der Seite 'Bereitstellungsplan'. Beim Kopieren eines Plans wird ein neuer Plan mit dem Namen 'Kopie von `planname`' auf der Seite 'Bereitstellungsplan' eingefügt. Der kopierte Plan enthält alle Tasks, die im ursprünglichen Plan definiert sind. Wenn der Plan Tasks des Typs 'UrbanCode Deploy' enthält, werden die im ursprünglichen Plan ausgewählten Anwendungen, Versionen und Umgebungen auch im kopierten Plan ausgewählt. Die Anwendungen, Versionen und Umgebungen werden in der Registerkarte **Versionen** auf der Seite 'Bereitstellungsplandetails' angezeigt.

Verwenden Sie zum Umstufen eines Plans die Aktion **Plan umstufen** auf der Seite 'Bereitstellungsplan'. Beim Umstufen eines Plans wird ein neuer Plan mit dem Namen 'Umstufung von `planname`' auf der Seite 'Bereitstellungsplan' eingefügt. Der umgestufte Plan enthält alle Tasks, die im ursprünglichen Plan definiert sind. Wenn der Plan Tasks des Typs 'UrbanCode Deploy' enthält, werden die im ursprünglichen Plan ausgewählten Anwendungen und Versionen auch im umgestuften Plan ausgewählt. Kopierte und umgestufte Pläne unterscheiden sich darin, dass in umgestuften Plänen keine Anwendungsversionen festgelegt sind.

## Planvorlagen verwalten
{: #plan_templates}

Sie können Bereitstellungspläne umwandeln, um Vorlagen für Bereitstellungspläne zu erstellen.

Verwenden Sie zum Erstellen einer Vorlage die Aktion **Vorlage aus Plan erstellen** auf der Seite 'Bereitstellungsplan'. Beim Erstellen einer Vorlage wird ein neuer Plan mit dem Namen 'Kopie von `planname` auf der Seite 'Bereitstellungsplan' eingefügt. Einer Vorlage wird der Status `Vorlage` zugewiesen, selbst wenn der ursprüngliche Plan den Status `Fertig` oder `In Bearbeitung` aufweist. Die Vorlage enthält alle Tasks, die im ursprünglichen Plan definiert sind. Wenn der Plan Tasks des Typs 'UrbanCode Deploy' enthält, werden die im ursprünglichen Plan ausgewählten Anwendungen auch in der Vorlage ausgewählt.

Bereitstellungspläne können nicht mit Vorlagen ausgeführt werden. Um eine Vorlage für eine Bereitstellungsplan zu verwenden, müssen Sie zunächst den Bereitstellungsplan kopieren oder umstufen und anschließend den kopierten oder umgestuften Plan verwenden.

## Bereitstellungspläne archivieren
{: #plan_arch}

Wenn Sie einen Bereitstellungsplan im Archiv speichern, wird dem Plan der Status `Archiviert` zugewiesen und er wird auf der Seite 'Bereitstellungsplan' nur angezeigt, wenn Sie den Filter **Archiv** verwenden.

Archivierte Bereitstellungspläne können in den Status `Entwurf` zurückgesetzt werden. Ein Bereitstellungsplan kann nicht dauerhaft gelöscht werden.

## Zurücksetzen und wiederherstellen
{: #plan_history}

Für jeden Bereitstellungsplan wird ein Verlaufsprotokoll der Änderungen und Überarbeitungen aufgezeichnet. Überarbeitungen können in der Registerkarte **Änderungsprotokoll** auf der Seite 'Bereitstellungsplandetails' angezeigt werden.

Verwenden Sie zum Zurücksetzen eines Plans auf eine vorherige Planversion die Aktion **Wiederherstellen** <img class="inline" src="images/restore-icon.png"  alt="Aktion 'Wiederherstellen'"> für die gewünschte Version. Die ausgewählte Version des Plans wird wiederhergestellt.  

## Bereitstellungszeiten schätzen
{: #plan_durationEst}

Vor dem Starten einer Bereitstellung können Sie die voraussichtliche Dauer schätzen. Verwenden Sie zum Schätzen der voraussichtlichen Dauer die Aktion **Geschätzte Taskzeiten** auf der Seite 'Bereitstellungsplandetails'. Die angezeigte Zeit gibt den Zeitpunkt an, an dem die Bereitstellung endet, wenn sie jetzt gestartet wird.
