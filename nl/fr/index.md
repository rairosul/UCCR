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


# Initiation à Continuous Release (bêta)

{: #gettingstartedtemplate}

Le service {{site.data.keyword.uccr_full}} sur on IBM {{site.data.keyword.Bluemix_short}} constitue une solution de gestion d'édition complète. Via {{site.data.keyword.uccr_short}}, vous pouvez réaliser des éditions et des déploiements pour toutes les applications logicielles dans votre cycle de vie de développement.
{:shortdesc}

[Après avoir créé une instance](https://console.ng.bluemix.net/catalog/services/continuous-release/){:new_window} ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe") de {{site.data.keyword.uccr_short}}, décidez comment commencer.

* **[En créant une édition et en exécutant un déploiement](#gs_create_plan)** si vous décidez de vous jeter à l'eau et de commencer à créer des plans de déploiement.

* **[En installant et en configurant DevOps Connect](#gs_install_dc)** si vous désirez intégrer {{site.data.keyword.uccr_short}} avec votre instance IBM UrbanCode&trade; Deploy sur site. Après avoir configuré une intégration, vous pouvez utiliser des tâches Continuous Release pour gérer des applications UrbanCode Deploy.


## Création d'une édition et exécution d'un déploiement
{: #gs_create_plan}

1. [Créez une édition](/docs/services/UCCR/UCCR_releases.html##releases_create) et affectez-la à l'une de vos équipes. N'importe quel membre de l'équipe peut créer des plans de déploiement pour l'édition et exécuter des déploiements.

1. Ajoutez un plan de déploiement à l'édition.

  * [Créez le plan](/docs/services/UCCR/UCCR_releases.html#releases_planAdd) et affectez-le à l'édition. 

  * [Ajoutez des tâches au plan de déploiement](/docs/services/UCCR/UCCR_tasks.html#tasks_create). Chaque tâche est répertoriée sur une ligne distincte dans le plan de déploiement. Essayez d'ajouter différents types de tâches : manuelle, UrbanCode Deploy, pipeline Continuous Delivery pipeline, différée, courrier électronique et Slack.

  * Vous pouvez modifier la liste des tâches dans le plan de différentes manières. Vous pouvez repositionner des tâches, les copier et les supprimer. 

4. Lorsque votre plan de déploiement est prêt, exécutez un déploiement à l'aide du plan de déploiement que vous avez créé à l'étape précédente.

  * [Vous exécutez un plan de déploiement en résolvant les tâches qu'il contient](/docs/services/UCCR/UCCR_deployRun.html). La résolution des tâches se réfère à leur lancement, puis à la modification de leur statut en `Complete` (complète), `Fail` (échec) ou `Skipped` (ignorée). Après la résolution de toutes les tâches d'un plan de déploiement, son statut indique Done (terminée).

  * Les tâches peuvent être lancées quand elles sont éligibles pour leur exécution. L'éligibilité est déterminée par le schéma d'exécution du plan. Par défaut, le schéma d'exécution d'un plan est séquentiel. Initialement, la première tâche, ou celle en tête de liste, est éligible pour son lancement. Vous pouvez modifier le schéma d'exécution en regroupant des tâches. Un groupe de tâches peut avoir un schéma d'exécution parallèle, ce qui signifie que le groupe de tâches peut être démarré dans n'importe quel ordre et que celles-ci peuvent s'exécuter simultanément. Un plan de déploiement peut comprendre plusieurs groupes, ainsi que des groupes imbriqués dans d'autres.

  * Certaines tâches, dénommées tâches automatiques, démarrent dès lors qu'elles sont éligibles pour leur exécution. Les tâches de type UrbanCode Deploy et pipeline Continuous Delivery démarrent dès qu'elles sont éligibles, sans intervention manuelle. Leur statut est également mis à jour sans intervention manuelle.  

## Installation et configuration de DevOps Connect
{: #gs_install_dc}

IBM Bluemix DevOps Connect coordonne la communication entre votre installation IBM UrbanCode Deploy sur site et {{site.data.keyword.uccr_short}}. Après avoir installé DevOps Connect, vous pouvez créer des intégrations pour vous permettre de gérer les applications UrbanCode Deploy via des tâches {{site.data.keyword.uccr_short}}.

**Prérequis**

* Pour enregistrer DevOps Connect, vous devez disposer d'un IBMid.

* Vous devez disposer de [Java™ Runtime Environment version 7 ou ultérieure](https://java.com/en/download/){:new_window} ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe") sur le système hôte et configurer la variable système PATH en spécifiant son emplacement.

* Vous aurez besoin d'un jeton d'autorisation de niveau admin d'UrbanCode Deploy.   


1. Installez DevOps Connect et utilisez-le pour intégrer {{site.data.keyword.uccr_short}} avec UrbanCode Deploy.

  1.  Sur la page Getting Started de {{site.data.keyword.uccr_short}}, cliquez sur **Setup**.

  1.  Dans la boîte de dialogue UrbanCode Deploy Integration Setup, cliquez sur **Download** pour télécharger DevOps Connect. Placez le fichier JAR sur un ordinateur ayant accès à UrbanCode Deploy.

  1.  A l'aide de la boîte de dialogue, copiez le script d'installation de DevOps Connect. Le script contient la commande de lancement de DevOps Connect et les données d'identification requises pour identifier votre service {{site.data.keyword.uccr_short}} Bluemix.

  1.  Sur l'ordinateur où vous avez placé DevOps Connect, ouvrez un interpréteur de commandes et collez dans celui-ci le script que vous avez copié.

  1.  Exécutez le script.  DevOps Connect affiche des messages de démarrage.

2. Enregistrez DevOps Connect.

  1.  Utilisez un navigateur Web pour ouvrir le tableau de bord DevOps Connect. L'URL par défaut est la suivante : `https://localhost:8443`. Pour changer l'URL et vous familiariser avec les autres options de démarrage, reportez-vous à la [documentation DevOps Connect](https://developer.ibm.com/urbancode/plugindoc/urbancode-sync/ibm-urbancode-sync-utility/1-2/){:new_window} ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")

  1.  Sur la page d'inscription, indiquez un nom pour l'installation DevOps Connect.

  1.  Cliquez sur **Register**. La première fois que vous accédez à DevOps Connect, vous êtes invité à vous inscrire avec votre IBMid.

  1.  Sur la page **Sign-in to IBM**, entrez votre IBMid et votre mot de passe, puis cliquez sur **Sign In**. Vous devez vous connecter chaque fois que vous lancez DevOps Connect.

3. Avec DevOps Connect, utilisez le plug-in IBM UrbanCode Deploy for Cloud Reporting pour créer une intégration entre {{site.data.keyword.uccr_short}} et UrbanCode Deploy.

    1.  Dans le tableau de bord DevOps Connect, cliquez sur **Integrations**, puis sur **Add New**.

    1.  Dans la zone **Name**, entrez un nom pour l'intégration. 

    1.  Dans la liste **Integration Type**, sélectionnez **IBM UrbanCode Deploy for Cloud Reporting**. Le plug-in IBM UrbanCode Deploy for Cloud Reporting est inclus avec DevOps Connect.

    1.  Dans la zone **Server URI**, entrez l'URL publique du serveur UrbanCode Deploy. Par exemple, `https://my_UCD.example.com:8447`.

    1.  Dans la zone **Authentication Token**, entrez ou collez le jeton d'authentification généré par UrbanCode Deploy.

    1.  Dans la zone **Admin User Email**, entrez votre adresse de courrier électronique.

    1.  Cliquez sur **Save**. 

4.  Lancez l'intégration pour vérifier qu'elle fonctionne.

    1.  Sur la page d'intégration, cliquez sur **Run**. DevOps Connect se connecte à l'instance UrbanCode Deploy spécifiée dans la zone **Server URI**. DevOps Connect est autorisé par le jeton collé dans la zone **Authentication Token**.

    1.  Dans {{site.data.keyword.uccr_short}}, confirmez que l'intégration a abouti en créant un type de tâche UrbanCode Deploy. Si vous pouvez sélectionner une application UrbanCode Deploy, ceci indique que l'intégration a abouti. L'instance {{site.data.keyword.uccr_short}} utilise les données de connexion et les paramètres de démarrage DevOps Connect pour identifier les applications UrbanCode Deploy.  
