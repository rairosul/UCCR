---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}


# A propos de {{site.data.keyword.uccr_short}}
{: #about_UCCR}


## Présentation de {{site.data.keyword.uccr_short}}
{: #what}

{{site.data.keyword.uccr_full}} est un outil de gestion des éditions à l'échelle de l'entreprise. {{site.data.keyword.uccr_short}} fonctionne de manière transparente avec d'autres services Bluemix et vos produits UrbanCode&reg; sur site.

{{site.data.keyword.uccr_short}} vous permet de :

<ul>
<li>orchestrer des déploiements multi-applications
</li>
<li>visualiser les dépendances de projet et d'application
</li>
<li>automatiser la promotion de code basée qualité
</li>
<li>rationaliser la planification d'événements d'édition majeurs
</li>
</ul>


## Termes clés
{: #keyterms}

Les termes suivants sont fréquemment utilisés avec {{site.data.keyword.uccr_short}} :

**Activités **: les activités se réfèrent aux éléments pouvant être affichés dans la liste **Activities** sur la page Releases. Les activités incluent les éditions, les événements et les plans de déploiement. Vous pouvez filtrer la liste **Activities** par statut, date/heure et étiquette.  

**Application** : se réfère aux applications IBM UrbanCode Deploy que gère {{site.data.keyword.uccr_short}}. Dans {{site.data.keyword.uccr_short}}, vous affectez des applications intégrées à des tâches de type UrbanCode Deploy. Vous devez sélectionner les processus, versions et environnements d'application. Lorsqu'une tâche UrbanCode Deploy s'exécute, elle exécute également l'application associée dans IBM UrbanCode Deploy.

**Tâche automatique **: lors des déploiements, ces tâches sont lancées automatiquement dès lors qu'elles sont éligibles pour leur exécution. Les tâches automatiques incluent les types de tâche suivants : UrbanCode Deploy, pipeline Continuous Delivery, courrier électronique, Slack, exécution d'un autre plan et tâches différées.

**Tâches dépendantes **: la possibilité de lancement d'une tâche peut être tributaire de l'achèvement d'autres tâches. Une tâche en attente de l'achèvement d'autres tâches est dénommée tâche dépendante. La tâche dont l'achèvement est attendu est dénommé tâche prérequise. Les tâches dépendantes ne peuvent pas commencer tant que ses tâches prérequises ne se sont pas terminées. Généralement, des dépendances sont utilisées pour garantir que les tâches s'exécutent dans l'ordre prévu.

**Durée **: temps nécessaire pour exécuter les tâches. Cette durée est mesurée depuis son lancement jusqu'à sa résolution. Lorsque vous créez certains types de tâche, vous pouvez estimer sa durée prévue. La durée est exprimée en minutes.

**Environnement** : représente des environnements d'application IBM UrbanCode Deploy. Dans UrbanCode Deploy, les environnements définissent les cibles du déploiement. Dans {{site.data.keyword.uccr_short}}, lorsque vous lancez des tâches UrbanCode Deploy, vous sélectionnez l'environnement concerné. Vous pouvez spécifier cet environnement lorsque vous créez la tâche ou en phase d'exécution.

**Schéma d'exécution **: se rapporte à l'ordre dans lequel les tâches d'un plan de déploiement deviennent éligibles pour leur exécution. Par défaut, le schéma d'exécution d'un plan est séquentiel. Les tâches séquentielles s'exécutent dans l'ordre, en commençant par la première tâche du plan de déploiement. Vous pouvez combiner des tâches dans des groupes et affecter un schéma d'exécution parallèle au groupe. Les tâches parallèles peuvent s'exécuter dans n'importe quel ordre ou simultanément.

Vous affectez le schéma parallèle aux groupes lorsque vous créez les groupes. Le schéma d'exécution prévu peut être affecté par des dépendances de tâche.

**Intégration** : se réfère à la communication régularisée entre {{site.data.keyword.uccr_short}} et d'autres produits et services. La communication entre {{site.data.keyword.uccr_short}} et les produits intégrés peut être bidirectionnelle. Par exemple, IBM UrbanCode Deploy peut envoyer des données d'application à {{site.data.keyword.uccr_short}} et {{site.data.keyword.uccr_short}} peut ensuite exécuter les applications. Les intégrations sont configurées via IBM Bluemix DevOps Connect.

**Processus **: se réfère aux processus d'application UrbanCode Deploy. Dans UrbanCode Deploy, les processus définissent des activités d'automatisation, telles que le déploiement de composants. Dans {{site.data.keyword.uccr_short}}, lorsque vous lancez des tâches UrbanCode Deploy, vous sélectionnez le processus. Vous pouvez sélectionner le processus lorsque vous créez la tâche ou en phase d'exécution.

**Etiquette **: libellé que vous pouvez appliquer à des tâches où à des éditions. Lorsque les étiquettes sont appliquées à des tâches, elles peuvent déterminer l'applicabilité de la tâche pour un déploiement donné. Lorsqu'elles sont appliquées à des éditions, les étiquettes peuvent être utilisées afin d'organiser et de filtrer les éditions.

**Groupe de tâches **: vous pouvez combiner deux tâches, ou plus, dans un groupe de tâches. Lorsque vous formez un groupe, vous devez définir le schéma d'exécution du groupe : séquentiel ou parallèle.

**Equipe **: collection d'utilisateurs et de groupes. Dans {{site.data.keyword.uccr_short}}, les équipes gèrent des éditions, des déploiements et des plans de déploiement. Vous pouvez importer des équipes depuis IBM UrbanCode Deploy.

**Version** : représente un instantané d'application IBM UrbanCode Deploy. Lorsque vous créez une tâche UrbanCode Deploy, les versions appartenant à l'application affectée à la tâche sont stockées dans le plan de déploiement. Vous pouvez utiliser l'onglet Version pour sélectionner les versions d'application et les environnements à utiliser lorsqu'une tâche est lancée.

## Concepts clés
{: #keyconcepts}

**Déploiement **: le terme déploiement se réfère aux activités visant à diffuser un projet logiciel sur une cible de déploiement. Généralement, vous exécutez des déploiements pour chaque phase du cycle de vie de votre édition, en finissant par la phase de production. Les activités réalisées lors d'un déploiement, et appelées tâches, sont définies dans des plans de déploiement. Le déploiement est déclenché en lançant l'une des tâches éligibles du plan. Le déploiement s'achève après résolution de toutes les tâches du plan de déploiement. 

**Plan de déploiement **: plan reproductible utilisé pour piloter les éditions de logiciel. Les plans de déploiement contiennent les tâches que vous utilisez pour réaliser un déploiement. Lorsque vous ajoutez une tâche à un plan de déploiement, vous définissez son type et sa durée.

Lorsque vous êtes prêt à déclencher un déploiement, vous lancez l'une des tâches éligibles du plan. L'éligibilité d'une tâche pour son lancement est déterminée par son schéma d'exécution. Les tâches automatiques démarrent automatiquement dès lors qu'elles sont éligibles pour leur exécution. Les tâches manuelles sont lancées manuellement.  

**Evénement **: activités associées à l'édition et qui lui sont appliquées et suivies dans le calendrier. Vous pouvez utiliser des événements pour organiser vos éditions et d'autres activités dépendant d'une chronologie, telles que les jours fériés et les interruptions totales.

**Tâche **: généralement, une tâche représente une activité métier marquante, dotée d'un point de départ, d'un point d'arrivée et d'une durée de réalisation mesurable. Ces durées sont utilisées pour estimation du temps requis pour le déploiement. Vous ajoutez des tâches aux plans de déploiement. Lorsque vous lancez un déploiement, vous réalisez les tâches qu'il contient.

Vous pouvez définir plusieurs types de tâches.
<ul>
<li>Les tâches UrbanCode Deploy exécutent des processus d'applications dans IBM UrbanCode Deploy. Continuous Release suit les versions (instantanés) et les environnements qui sont utilisés par les applications. Ces tâches démarrent automatiquement quand elles deviennent éligibles pour leur exécution.</li>
<li>Les tâches manuelles peuvent représenter n'importe quelle activité concernant un déploiement, comme le démarrage d'un serveur. Comme leur nom l'indique, ces tâches sont lancées manuellement. </li>
<li>Les tâches différées représentent des jalons importants. Vu qu'il s'agit d'une tâche automatique, une tâche différée démarre dès lors qu'elle est éligible et s'arrête à la date/heure spécifiée. Généralement, les tâches différées constituent des prérequis pour d'autres tâches.
</li>
<li>Les tâches d'en-tête fournissent des éléments organisationnels pour les plans de déploiement. Vous pouvez utiliser une tâche d'en-tête pour identifier un groupe de tâches, ou pour ajouter des remarques ou des instructions à un groupe. Les tâches d'en-tête sont des tâches automatiques qui s'achèvent immédiatement après leur lancement. Vous ne pouvez pas définir des durées pour ces tâches.
</li>
<li>Les tâches de transmission de courrier électronique envoient des messages à des comptes de messagerie électronique.
</li>
<li>Les tâches Slack envoient des messages à un canal Slack spécifié par l'utilisateur.
</li>
<li>Les tâches de pipeline Continuous Delivery automatisent vos flux de travaux DevOps. Vous pouvez gérer vos pipelines avec des tâches de pipeline.</li>
</ul>

**Edition **: conteneur hébergeant des plans de déploiement, des événements et des étiquettes. Généralement, une édition contient plusieurs plans de déploiement, bien que ceci ne soit pas impératif. Encore en général, chaque plan dans une édition représente une phase dans le cycle de vie de développement (Assurance qualité ou Production, par exemple). Les phases, ou plans de déploiement, sont dénommées collectivement Cycle de vie de l'édition.
