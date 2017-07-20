---

copyright:
  years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Gestion des événements et des étiquettes
{: #events_overview}

Un événement représente une activité associée à une édition et que vous gérez à l'aide du calendrier.

Une étiquette est un libellé que vous pouvez adjoindre à une édition ou à un événement. Vous pouvez utiliser des étiquettes pour filtrer la liste Activities sur la page Releases. Contrairement aux événements, les étiquettes n'apparaissent pas sur le calendrier.

{:shortdesc}

Les événements sont organisés en catégories globales qui incluent des éditions, des jours fériés et des créneaux de maintenance. [Les événements de calendrier et les étiquettes sont affectés à des éditions](UCCR_releases.html#releases_overview). Vous pouvez ajouter des événements à des éditions ou les utiliser indépendamment des éditions.  

Lorsqu'un événement est affecté, il est représenté sur le calendrier par une icône dénotant sa catégorie. Vous pouvez utiliser ces icônes pour filtrer la page Releases et sélectionner des éditions pour la date ou la plage de dates concernée.

Des étiquettes sont affectées aux éditions et peuvent être utilisées pour filtrer la page Releases. Les étiquettes affectées à des éditions figurent sur la page Releases, mais n'apparaissent pas sur le calendrier. Vous pouvez utiliser des étiquettes pour éviter d'encombrer inutilement le calendrier.

## Filtrage des événements d'édition et des plans de déploiement
{: #events_findFilter}

La page Releases affiche les éditions, les événements et les plans de déploiement créés par vous et votre équipe. Depuis la page Releases, vous pouvez réaliser la plupart dea activités associées aux éditions, comme la création d'éditions et de plans de déploiement.

Par défaut, la page Releases affiche les activités planifiées pour les sept prochaines journées. Vous pouvez filtrer l'affichage par date/heure, événement, étiquette et statut. Vous pourriez, par exemple, limiter l'affichage aux éditions planifiées pour le lendemain. La plage de dates actuellement sélectionnée est affichée sur la barre d'actions.

Pour filtrer la page Releases par événement ou balise, sélectionnez l'événement ou la balise dans la barre de recherche, puis appuyez sur la touche Entrée.

Pour filtrer les activités planifiées par date, effectuez l'une des opérations suivantes :
<ul>
<li>Sélectionnez une valeur dans la liste **Dates** sur la barre d'actions. Pour afficher, par exemple, les éléments planifiés pour la semaine à venir, sélectionnez **Next 7 days**.</li>
<li>Sur le calendrier, sélectionnez une date ou une plage de dates. Lorsque vous sélectionnez des dates sur le calendrier, la valeur **Dates** sur la barre d'actions est définie à **Custom**.</li>
</ul>

Les activités qui sont ou étaient planifiées pour les dates sélectionnées sont affichées.

Pour filtrer les éléments par statut, sélectionnez l'un des filtres suivants :
<ul>
<li>Sélectionnez **All** pour afficher toutes les activités. Cette option affiche toutes les éditions, événements et plans de déploiement, hormis ceux archivés. Utilisez cette option pour afficher les plans de déploiement sans planning.
</li>
<li>Sélectionnez **Draft** pour afficher les plans de déploiement dont le statut est autre que In Progress, Complete ou Failed.
</li>
<li>Sélectionnez **Scheduled** pour afficher les éditions, les événements et les plans planifiés pour la plage de dates sélectionnée.
</li>
<li>Sélectionnez **In Progress** pour afficher les déploiements en cours mais dont le statut n'indique pas encore Complete ou Failed.
</li>
<li>Sélectionnez **Failed** pour afficher les déploiements dont le statut indique Failed.</li>
<li>Sélectionnez **Complete** pour afficher les déploiements dont le statut indique Complete.
</li>
</li>
<li>Sélectionnez **Archive** pour afficher les éditions, les événements et les plans de déploiement qui ont été sauvegardés dans l'archive. Les éléments archivés peuvent être restaurés.
</li>
<li>Sélectionnez **Templates** pour afficher les plans de déploiement sauvegardés sous forme de modèles. Vous pouvez utiliser des modèles pour créer des plans. Vous pouvez rétablir des modèles à leur état plan de déploiement.  
</li>
</ul>

## Utilisation du calendrier
{: #events_calendarManage}

Vous pouvez filtrer la liste **Activities** en sélectionnant des icônes d'événement dans le calendrier. Le style des icônes d'événement évoque des catégories, ce qui facilite l'identification de la catégorie à laquelle ils appartiennent. La liste suivante recense les catégories d'événement :

<ul>
<li>Les événements d'édition sont représentés par des cercles pleins en couleur <img class="inline" src="images/event-icon-release.png"  alt="Icône Evénement d'édition">.</li>
<li>Les événements d'interruption totale et de maintenance sont représentés avec un contour en couleur <img class="inline" src="images/event-icon-window.png"  alt="Paramètres de calendrier">.</li></li>
<li>Les événements de type Jour férié sont représentés par un symbole en forme de parapluie en couleur au-dessus de la date concernée <img class="inline" src="images/event-icon-holiday.png"  alt="Paramètres de calendrier">.</li>
</ul>

Dans l'illustration ci-dessous, l'événement d'édition en vert est planifié pour une exécution du dimanche au mardi. L'événement d'édition en bleu est planifié pour mercredi. L'événement de maintenance est planifié du mercredi au samedi. L'événement Jour férié est planifié pour le second dimanche.

![](images/event-icon-styles2.png "Styles d'icônes d'événement par défaut")

Figure 1. Styles d'icônes d'événement par défaut

Pour filtrer la liste **Activities**, effectuez l'une des opérations suivantes :

<ul>
<li>Cliquez sur une date.</li>
<li>Sélectionnez une plage de dates. Vous pouvez sélectionner une plage de dates en cliquant sur une date, puis sur Maj+clic dans la seconde.</li>
</ul>

Les éditions, les événements et les déploiements planifiés pour les dates sélectionnées sont affichés. Si plusieurs événements de calendrier sont planifiés pour une date, celle-ci est soulignée <img class="inline" src="images/event-icon-twoIcons.png"  alt="Paramètres de calendrier">.

## Création de types d'événements
{: #events_eventTypeCreate}

Outre ceux par défaut, vous pouvez créer d'autres types d'événement pour toutes les catégories d'événement.

Lorsque vous créez un type d'événement, des styles graphiques sont automatiquement appliqués à l'icône associée. Vous pouvez changer le style de l'icône après avoir créé un événement.

Pour créer un événement, procédez comme suit :

1. Sur la page Releases, cliquez sur **Calendar settings** <img class="inline" src="images/cal-set.png"  alt="Calendar settings">.

1. Dans la page Configure calendar, cliquez sur **Add event type** <img class="inline" src="images/event-add.png"  alt="Ajout d'un type d'événement"> pour la catégorie d'événement que vous désirez créer.

3. Dans la zone de texte, entrez un nom pour l'événement.

3. Cliquez sur **Save**. Vous pouvez éditer et supprimer des étiquettes d'événement.

## Gestion des types d'événements
{: #events_eventEdit}

Par défaut, les icônes de style d'événement sont appliquées automatiquement et aléatoirement en fonction de la catégorie.

Dans l'illustration ci-dessous, les styles des deux premières lignes ont été appliqués aux événements de la catégorie Edition ; ceux de la troisième ligne aux événements de maintenance et d'interruption totale ; ceux de la quatrième, aux jours fériés.

![](images/event-styles.png "Plan de déploiement usuel")

Figure 2. Styles d'icônes d'événement

Pour modifier le style d'un type d'événement, procédez comme suit :

1. Dans la page Releases, cliquez sur **Calendar settings**.

2. Dans la page Configure calendar, cliquez sur l'icône **Edit** en regarde de l'icône d'événement que vous désirez modifier, puis sur **More**.

3. Sélectionnez un style. Vous pouvez sélectionner un style quelconque, quelque que soit la catégorie.

Pour modifier le nom d'un style d'événement, cliquez sur l'icône **Edit** en regard de son nom, puis modifiez ce nom.

Pour supprimer un type d'événement, cliquez sur l'icône **Delete** en regard de son nom.

## Importation d'éditions et d'événements
{: #events_importing}

Vous pouvez importer vos propres éditions et événements. Pour importer des éléments, définissez-les dans un fichier CSV. Le format de fichier CSV est un format standard qui peut être utilisé pour échanger des données entre des applications. Dans un fichier CSV, chaque zone d'un enregistrement est séparée des autres par des virgules et chaque enregistrement figure sur une ligne distincte. Utilisez le format suivant pour définir des éditions et des événements :  

`name*,description,start*,end,team*,tag`

Les zones suivantes sont obligatoires :

`name,start,team`

Par exemple, `Holiday,New Years Day,1/1/18,1/1/18,my_team,National Holiday` 

Pour importer des événements et des éditions, procédez comme suit :

1. Dans la page Releases, cliquez sur **Import** <img class="inline" src="images/import-events.png"  alt="Importation d'événements">.

2. Dans la boîte de dialogue Import from CSV , sélectionnez le fichier CSV contenant vos éditions et événements, puis cliquez sur **Import Events**. La boîte de dialogue comporte un lien vous permettant de télécharger un exemple de fichier d'événement au format CSV.

Si l'importation aboutit, les éditions et les événements sont affichés sur la page Releases. Si la valeur de la zone **tag** contient un type d'événement défini auparavant, cet événement est affiché sur le calendrier. Autrement, la valeur de la zone **tag** est traitée en tant qu'étiquette.

## Création de balises
{: #events_tagManage}

[Vous devez créer les étiquettes sur la page Create Release lorsque vous créez ou modifiez une édition.](UCCR_releases.html#releases_create) Les étiquettes sont affichées sur le page Releases, en même temps que l'édition propriétaire. Bien qu'elles n'apparaissent pas sur le calendrier, vous pouvez néanmoins les utiliser pour filtrer les éléments affichés sur la page Releases.
