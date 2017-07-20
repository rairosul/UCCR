---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Ereignisse und Tags verwalten
{: #events_overview}

Ein Ereignis stellt eine auf ein Release bezogene Aktivität dar, die mit dem Kalender verwaltet wird.

Ein Tag ist eine Bezeichnung, die Sie zu einem Release oder einem Ereignis hinzufügen können.Mithilfe von Tags können Sie die Liste der Aktivitäten auf der Seite 'Releases' filtern. Im Unterschied zu Ereignissen werden Tags nicht im Kalender angezeigt.

{:shortdesc}

Ereignisse werden zu allgemeinen Kategorien zusammengefasst (z. B. Releases, arbeitsfreie Zeiten und Wartungszeiten). [Kalenderereignisse und Tags sind Releases zugeordnet.](UCCR_releases.html#releases_overview). Ereignisse können zu Releases hinzugefügt oder unabhängig von Releases verwendet werden.  

Wenn ein Ereignis zugeordnet ist, wird es im Kalender durch ein entsprechendes Symbol für die Ereigniskategorie dargestellt. Mithilfe dieser Symbole können Sie die Seite 'Releases' nach den zugehörigen Datumsangaben oder nach Datumsbereichen filtern.

Tags sind Releases zugeordnet und können verwendet werden, um die Seite 'Releases' zu filtern. Zugeordnete Tags werden auf der Seite 'Releases' angezeigt und nicht im Kalender. Sie können Tags verwenden, um den Kalender nicht mit zu vielen Details zu überfrachten.

## Releaseereignisse und Bereitstellungspläne filtern
{: #events_findFilter}

Auf der Seite 'Releases' werden die Releases, Ereignisse und Bereitstellungspläne angezeigt, die von Ihnen und von Ihrem Team erstellt wurden. Diese Seite kann für die meisten auf Releases bezogenen Aktivitäten verwendet werden (z. B. zum Erstellen von Releases und Bereitstellungsplänen).

Auf der Seite 'Releases' werden standardmäßig Aktivitäten angezeigt, die für die nächsten sieben Tage geplant sind. Sie können die Anzeige nach Zeit, Ereignis, Tag und Status filtern. Beispielsweise können Sie die Anzeige auf Releases beschränken, die für morgen geplant sind. Der aktuell ausgewählte Datumsbereich wird in der Aktionsleiste angezeigt.

Um die Seite 'Releases' nach Ereignis oder Tag zu filtern, wählen Sie das Ereignis bzw. den Tag in der Suchleiste aus und drücken Sie die Eingabetaste.

Führen Sie eine der folgenden Tasks aus, um geplante Aktivitäten nach Datum zu filtern:
<ul>
<li>Wählen Sie in der Liste **Daten** in der Aktionsleiste einen Wert aus. Wenn Sie beispielsweise Elemente anzeigen möchten, die für die kommende Woche geplant sind, wählen Sie **Nächste 7 Tage** aus.</li>
<li>Wählen Sie im Kalender ein Datum oder einen Datumsbereich aus. Wenn Sie Datumsangaben im Kalender auswählen, wird für Datumsangaben (**Daten**) in der Aktionsleiste der Wert **Angepasst** angegeben.</li>
</ul>

Die für die ausgewählten Datumsangaben geplanten Aktivitäten werden angezeigt.

Wählen Sie einen der folgenden Filter aus, um Elemente nach dem Status zu filtern:
<ul>
<li>Wählen Sie **Alle** aus, um alle Aktivitäten anzuzeigen. Alle Releases, Ereignisse und Bereitstellungspläne, die nicht archiviert sind, werden angezeigt. Verwenden Sie diese Option, um nicht geplante Bereitstellungspläne anzuzeigen.
</li>
<li>Wählen Sie **Entwurf** aus, um Bereitstellungspläne anzuzeigen, die nicht den Status 'In Bearbeitung', 'Abgeschlossen' oder 'Fehlgeschlagen' aufweisen.
</li>
<li>Wählen Sie **Geplant** aus, um Releases, Ereignisse und Pläne anzuzeigen, die für den ausgewählten Datumsbereich geplant sind.
</li>
<li>Wählen Sie **In Bearbeitung** aus, um aktive Bereitstellungen anzuzeigen, die nicht den Status 'Abgeschlossen' oder 'Fehlgeschlagen' aufweisen.
</li>
<li>Wählen Sie **Fehlgeschlagen** aus, um Bereitstellungen anzuzeigen, die den Status 'Fehlgeschlagen' aufweisen.</li>
<li>Wählen Sie **Abgeschlossen** aus, um Bereitstellungen anzuzeigen, die den Status 'Abgeschlossen' aufweisen.
</li>
</li>
<li>Wählen Sie **Archiv** aus, um Releases, Ereignisse und Bereitstellungspläne anzuzeigen, die im Archiv gespeichert sind. Archivierte Elemente können wiederhergestellt werden.
</li>
<li>Wählen Sie **Vorlagen** aus, um Bereitstellungspläne anzuzeigen, die als Vorlagen gespeichert wurden. Mithilfe von Vorlagen können Sie Pläne erstellen. Sie können Vorlagen zurück in Bereitstellungspläne umwandeln.  
</li>
</ul>

## Kalender verwenden
{: #events_calendarManage}

Sie können die Liste **Aktivitäten** filtern, indem Sie Ereignissymbole im Kalender auswählen. Ereignissymbole stellen die Kategorien dar und erleichtern die Übersicht über die dargestellten Ereigniskategorien. Die Ereigniskategorien werden in der folgenden Liste beschrieben:

<ul>
<li>Ereignisse des Typs 'Release' werden als ausgefüllte farbige Kreise dargestellt (z. B. <img class="inline" src="images/event-icon-release.png"  alt="Symbol für Releaseereignis">).</li>
<li>Ereignisse des Typs 'Ausfall- oder Wartungszeit' werden durch Kreise mit farbiger Umrandung dargestellt (z. B. <img class="inline" src="images/event-icon-window.png"  alt="Kalendereinstellungen">)</li></li>
<li>Ereignisse des Typs 'Arbeitsfreie Zeit' werden durch farbige, schirmähnliche Symbole über dem Datum dargestellt (z. B. <img class="inline" src="images/event-icon-holiday.png"  alt="Kalendereinstellungen">).</li>
</ul>

Das grün dargestellte Releaseereignis in der folgenden Abbildung ist von Sonntag bis Dienstag geplant. Das blau dargestellte Releaseereignis ist für den Mittwoch geplant. Das Wartungsereignis ist von Donnerstag bis Sonntag geplant. Das Ereignis 'Arbeitsfreie Zeit' ist für den zweiten Sonntag geplant.

![](images/event-icon-styles2.png "Standarddarstellungen der Ereignissymbole")

Abbildung 1. Standarddarstellungen der Ereignissymbole

Führen Sie eine der folgenden Aktionen aus, um die Liste **Aktivitäten** zu filtern:

<ul>
<li>Klicken Sie auf ein Datum.</li>
<li>Wählen Sie einen Datumsbereich aus. Klicken Sie zum Auswählen eines Datumsbereichs auf ein Datum und anschließend bei gedrückter Umschalttaste auf ein weiteres Datum.</li>
</ul>

Daraufhin werden Releases, Ereignisse und Bereitstellungen angezeigt, die in dem ausgewählten Datumsbereich geplant sind. Falls für ein Datum mehrere Kalenderereignisse geplant sind, wird das Datum unterstrichen dargestellt (z. B. <img class="inline" src="images/event-icon-twoIcons.png"  alt="Kalendereinstellungen">).

## Ereignistypen erstellen
{: #events_eventTypeCreate}

Zusätzlich zu den Standardereignistypen können Sie weitere Ereignistypen für beliebige Ereigniskategorien erstellen.

Wenn Sie einen Ereignistyp erstellen, werden automatisch grafische Darstellungen auf das zugehörige Symbol angewendet. Nachdem Sie ein Ereignis erstellt habe, können Sie die Symboldarstellung ändern.

Führen Sie die folgenden Schritte aus, um ein Ereignis zu erstellen:

1. Klicken Sie auf der Seite 'Releases' auf **Kalendereinstellungen** <img class="inline" src="images/cal-set.png"  alt="Kalendereinstellungen">.

1. Klicken Sie auf der Seite zum Konfigurieren des Kalenders auf **Ereignistyp hinzufügen** <img class="inline" src="images/event-add.png"  alt="Ereignistyp hinzufügen"> für die Ereigniskategorie, die Sie erstellen möchten.

3. Geben Sie in das Textfeld einen Namen für das Ereignis ein.

3. Klicken Sie auf **Speichern**. Ereignistags können bearbeitet und gelöscht werden.

## Ereignistypen verwalten
{: #events_eventEdit}

Die Darstellungsstile für Ereignissymbole werden standardmäßig nach dem Zufallsprinzip automatisch abhängig von der Kategorie angewendet.

In der folgenden Abbildung werden die Stile in den oberen beiden Zeilen auf Ereignisse in der Kategorie für Releaseereignisse angewendet, die Stile in der dritten Zeile auf Wartungs- und Ausfallereignisse und die Stile in der vierten Zeile auf arbeitsfreie Zeiten.

![](images/event-styles.png "Typischer Bereitstellungsplan")

Abbildung 2. Darstellungen für Ereignissymbole

Führen Sie die folgenden Schritte aus, um einen Ereignistypstil zu bearbeiten:

1. Klicken Sie auf der Seite 'Releases' auf **Kalendereinstellungen**.

2. Klicken Sie auf der Seite zum Konfigurieren des Kalenders auf das Symbol **Bearbeiten** neben dem Ereignissymbol, das Sie ändern möchten, und klicken Sie anschließend auf **Weiter**.

3. Wählen Sie einen Stil aus. Sie können einen beliebigen Stil auswählen (unabhängig von der Kategorie).

Um einen Ereignistypnamen zu bearbeiten, klicken Sie auf das Symbol **Bearbeiten** neben dem Namen des Ereignistyps und bearbeiten Sie den Namen.

Um einen Ereignistyp zu löschen, klicken Sie auf das Symbol **Löschen** neben dem Namen.

## Releases und Ereignisse importieren
{: #events_importing}

Sie können eigene Releases und Ereignisse importieren. Um Elemente zu importieren, definieren Sie die Elemente in einer CSV-Datei mit durch Kommas getrennten Werten (Comma-Separated Values, CSV). Das Format der CSV-Datei ist ein Standardformat für den Datenaustausch zwischen Anwendungen. In CSV-Dateien ist jedes Feld in einem Datensatz durch ein Komma getrennt und jeder Datensatz ist in einer separaten Zeile enthalten. Verwenden Sie das folgende Format zum Definieren von Ereignissen und Releases:  

`name*,description,start*,end,team*,tag`

Die folgenden Felder sind erforderlich:

`name,start,team`

Beispiel: `Arbeitsfreie Zeit,Neujahrstag,1/1/18,1/1/18,mein_team,Nationaler Feiertag` 

Führen Sie die folgenden Schritte aus, um Ereignisse und Releases zu importieren:

1. Klicken Sie auf der Seite 'Releases' auf **Importieren** <img class="inline" src="images/import-events.png"  alt="Ereignisse importieren">.

2. Wählen Sie im Dialogfeld 'Aus CSV importieren' die CSV-Datei aus, in der Ihre Releases und Ereignisse enthalten sind, und klicken Sie anschließend auf **Ereignisse importieren**. Im Dialogfeld wird ein Link zum Herunterladen einer CSV-Beispielereignisdatei bereitgestellt.

Wenn der Import erfolgreich ausgeführt wird, werden die Releases und Ereignisse auf der Seite 'Releases' angezeigt. Wenn der Wert im Feld **tag** einen zuvor definierten Ereignistyp enthält, wird das Ereignis im Kalender angezeigt. Andernfalls wird der Wert im Feld **tag** wie ein Tag behandelt.

## Tags erstellen
{: #events_tagManage}

[Tags können auf der Seite 'Release erstellen' erstellt werden, während Sie ein Release erstellen oder ändern.](UCCR_releases.html#releases_create) Tags werden auf der Seite 'Releases' zusammen mit dem übergeordneten Release angezeigt. Obwohl Tags nicht im Kalender angezeigt werden, können sie zum Filtern der auf der Seite 'Releases' angezeigten Elemente verwendet werden.
