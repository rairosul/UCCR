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


# Einführung in Continuous Release (Beta)

{: #gettingstartedtemplate}

Der {{site.data.keyword.uccr_full}}-Service unter IBM {{site.data.keyword.Bluemix_short}} ist eine umfassende Lösung für das Release-Management. Mit {{site.data.keyword.uccr_short}} können Sie Releases und Bereitstellungen für alle Softwareanwendungen in Ihrem Entwicklungszyklus ausführen.
{:shortdesc}

[Nach dem Erstellen einer Instanz](https://console.ng.bluemix.net/catalog/services/continuous-release/){:new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") von {{site.data.keyword.uccr_short}} können Sie auswählen, wie Sie beginnen möchten.

* Beginnen Sie mit **[Release erstellen und Bereitstellung durchführen](#gs_create_plan)**, wenn Sie sofort in das Erstellen von Bereitstellungsplänen einsteigen möchten.

* Beginnen Sie mit **[DevOps Connect installieren und konfigurieren](#gs_install_dc)**, wenn Sie {{site.data.keyword.uccr_short}} in Ihre lokale IBM UrbanCode&trade; Deploy-Instanz integrierten möchten. Nachdem Sie eine Integration konfiguriert haben, können Sie Continuous Release-Tasks verwenden, um UrbanCode Deploy-Anwendungen zu verwalten.


## Release erstellen und Bereitstellung durchführen
{: #gs_create_plan}

1. [Erstellen Sie ein Release](/docs/services/UCCR/UCCR_releases.html##releases_create) und ordnen Sie es einem Ihrer Teams zu. Jedes Teammitglied kann Bereitstellungspläne für das Release erstellen und Bereitstellungen durchführen.

1. Fügen Sie einen Bereitstellungsplan zu dem Release hinzu.

  * [Erstellen Sie den Plan](/docs/services/UCCR/UCCR_releases.html#releases_planAdd) und ordnen Sie ihn dem Release zu. 

  * [Fügen Sie Tasks zum Bereitstellungsplan hinzu](/docs/services/UCCR/UCCR_tasks.html#tasks_create). Jede Task wird im Bereitstellungsplan in einer separaten Zeile aufgelistet. Fügen Sie versuchsweise verschiedene Tasktypen wie 'Manuell', 'UrbanCode Deploy', 'Continuous Delivery Pipeline', 'Verzögert', 'E-Mail' und 'Slack' hinzu.

  * Die Liste der Tasks in dem Plan kann mit verschiedenen Methoden geändert werden. Sie können Tasks neu positionieren, kopieren und löschen. 

4. Wenn Ihr Bereitstellungsplan abgeschlossen ist, führen Sie unter Verwendung des Plans, den Sie im vorigen Schritt erstellt haben, eine Bereitstellung durch.

  * [Führen Sie eine Bereitstellung durch, indem Sie die Tasks in einem Bereitstellungsplan auflösen](/docs/services/UCCR/UCCR_deployRun.html). Um eine Task aufzulösen, starten Sie die Task und ändern Sie den Status der Task in `Abgeschlossen`, `Fehlgeschlagen` oder `Übersprungen`. Nachdem alle Tasks in einem Bereitstellungsplan aufgelöst wurden, wird die Bereitstellung in den Status 'Fertig' versetzt.

  * Tasks können gestartet werden, sobald sie zum Starten berechtigt sind. Ob diese Berechtigung vorliegt, wird durch das Ausführungsmuster des Plans bestimmt. Ein Plan wird standardmäßig sequenziell ausgeführt. Zunächst ist die erste oder oberste Task zum Starten berechtigt. Sie können das Ausführungsmuster ändern, indem Sie Tasks gruppieren. Bei einer Taskgruppe mit parallelem Ausführungsmuster können die Tasks der Gruppe in beliebiger Reihenfolge gestartet und gleichzeitig ausgeführt werden. Ein Bereitstellungsplan kann mehrere Gruppen und darin enthaltene verschachtelte Gruppen umfassen.

  * Automatische Tasks werden automatisch gestartet, sobald sie für die Ausführung infrage kommen. Tasks vom Typ 'UrbanCode Deploy' und 'Continuous Delivery Pipeline' werden ohne manuelle Eingriffe gestartet, sobald sie für die Ausführung infrage kommen. Der Status für automatische Tasks wird ebenfalls ohne manuelle Eingriffe aktualisiert.  

## DevOps Connect installieren und konfigurieren
{: #gs_install_dc}

IBM Bluemix DevOps koordiniert die Kommunikation zwischen Ihrer lokalen IBM UrbanCode Deploy-Installation und {{site.data.keyword.uccr_short}}. Nachdem Sie DevOps Connect installiert haben, können Sie Integrationen erstellen, die das Verwalten von UrbanCode Deploy-Anwendungen mit {{site.data.keyword.uccr_short}}-Tasks ermöglichen.

**Voraussetzungen**

* Zum Registrieren von DevOps Connect benötigen Sie eine IBMid.

* Auf dem Hostsystem muss [Java™ Runtime Environment Version 7 oder höher](https://java.com/en/download/){:new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") installiert und in der Systemvariablen PATH muss die zugehörige Installationsposition angegeben sein.

* Sie müssen über ein Administratorberechtigungstoken von UrbanCode Deploy verfügen.   


1. Installieren Sie DevOps Connect und verwenden Sie dieses Produkt zum Integrieren von {{site.data.keyword.uccr_short}} in UrbanCode Deploy.

  1.  Klicken Sie in {{site.data.keyword.uccr_short}} auf der Seite 'Einführung' auf **Konfiguration**.

  1.  Klicken Sie im Dialogfeld zum Konfigurieren der UrbanCode Deploy-Integration auf **Download**, um DevOps Connect herunterzuladen. Speichern Sie die JAR-Datei auf einem Computer, der über Zugriff auf UrbanCode Deploy verfügt.

  1.  Verwenden Sie das Dialogfeld, um das DevOps Connect-Installationsscript zu kopieren. Das Script enthält den Befehl zum Starten von DevOps Connect und die erforderlichen Berechtigungsnachweise zum Identifizieren Ihres {{site.data.keyword.uccr_short}} Bluemix-Service.

  1.  Öffnen Sie auf dem Computer, auf dem sich DevOps Connect befindet, eine Befehlsshell und fügen Sie das kopierte Script ein.

  1.  Führen Sie das Script aus. Startnachrichten für DevOps Connect werden angezeigt.

2. Registrieren Sie DevOps Connect.

  1.  Öffnen Sie das DevOps Connect-Dashboard in einem Web-Browser. Die Standard-URL lautet `https://localhost:8443`. Informationen zum Ändern der URL und zu weiteren Startoptionen finden Sie in der [DevOps Connect-Dokumentation](https://developer.ibm.com/urbancode/plugindoc/urbancode-sync/ibm-urbancode-sync-utility/1-2/){:new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

  1.  Geben Sie auf der Registrierungsseite einen Namen für die DevOps Connect-Installation an.

  1.  Klicken Sie auf **Registrierung**. Wenn Sie zum ersten Mal auf DevOps Connect zugreifen, werden Sie aufgefordert, das Produkt mit Ihrer IBMid zu registrieren.

  1.  Geben Sie auf der Seite für die **Anmeldung bei IBM** Ihre IBMid und Ihr Kennwort ein und klicken Sie anschließend auf **Anmelden**. Sie müssen sich bei jedem Starten von DevOps Connect anmelden.

3. Verwenden Sie in Verbindung mit DevOps Connect das Plug-in 'IBM UrbanCode Deploy for Cloud Reporting', um eine Integration zwischen {{site.data.keyword.uccr_short}} und UrbanCode Deploy zu erstellen.

    1.  Klicken Sie im DevOps Connect-Dashboard auf **Integrationen** und anschließend auf **Neu hinzufügen**.

    1.  Geben Sie in das Feld **Name** einen Namen für die Integration ein.

    1.  Wählen Sie in der Liste **Integrationstyp** den Eintrag **IBM UrbanCode Deploy for Cloud Reporting** aus. Das IBM UrbanCode Deploy for Cloud Reporting-Plug-in wird mit DevOps Connect bereitgestellt.

    1.  Geben Sie in das Feld **Server-URI** die öffentliche URL des UrbanCode Deploy-Servers ein. Beispiel: `https://my_UCD.example.com:8447`.

    1.  Tragen Sie in das Feld **Authentifizierungstoken** das von UrbanCode Deploy generierte Authentifizierungstoken ein oder fügen Sie es ein.

    1.  Geben Sie in das Feld **E-Mail von Benutzer mit Administratorberechtigung** Ihre E-Mail-Adresse ein.

    1.  Klicken Sie auf **Speichern**.

4.  Führen Sie die Integration aus, um zu überprüfen, dass Sie funktioniert.

    1.  Klicken Sie auf der Integrationsseite auf **Ausführen**. DevOps Connect stellt die Verbindung zur UrbanCode Deploy-Instanz her, die im Feld **Server-URI** angegeben ist. Als Berechtigung wird von DevOps Connect das Token verwendet, das im Feld **Authentifizierungstoken** angegeben ist.

    1.  Überprüfen Sie in {{site.data.keyword.uccr_short}}, dass die Integration erfolgreich ausgeführt wurde, indem Sie eine Task des Typs 'UrbanCode Deploy' erstellen. Wenn Sie eine UrbanCode Deploy-Anwendung auswählen können, wurde die Integration erfolgreich durchgeführt. Die {{site.data.keyword.uccr_short}}-Instanz verwendet die Anmelde- und Startparameter von DevOps Connect, um die UrbanCode Deploy-Anwendungen zu identifizieren.  
