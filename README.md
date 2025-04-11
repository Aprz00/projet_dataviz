# projet_dataviz

## Sources des données et traitement
Données immobilières (valeurs foncières)
Les données utilisées proviennent du jeu de données public intitulé :
« Indicateurs Immobiliers par commune et par année (prix et volumes sur la période 2014-2023) », disponible sur data.gouv.fr.
Ces données, issues de la base DVF (Demandes de Valeurs Foncières), sont produites par la DGFiP et recensent les transactions immobilières enregistrées en France au cours des cinq dernières années. Elles incluent des informations sur le prix, la surface et la typologie des biens.

Les données d’origine étant communales, un traitement a été effectué afin de calculer des moyennes par département, notamment pour les représentations en carte. Ce traitement repose sur des agrégations simples, en l’absence d’informations plus fines (comme des identifiants de transaction ou des métadonnées cadastrales précises). Ce choix a pu engendrer certaines imprécisions dans les résultats, en particulier dans les cas de transactions complexes (ex. ventes multilignes ou regroupement de biens hétérogènes).

Nous avons fait le choix de ne pas utiliser DVF+, une version enrichie proposée par le Cerema, en raison de sa découverte trop tardive dans le processus de conception du site.

Données géographiques
Contours des départements : issus du jeu de données « Carte des départements » disponible sur data.gouv.fr.

Contours des communes : issus de « Contours des communes de France simplifié, avec régions et départements d’outre-mer rapprochés » (également sur data.gouv.fr).

En raison de leur poids important, les données GeoJSON des communes n’ont pas pu être chargées intégralement dans l’environnement web. Les départements et régions d’outre-mer (DOM-ROM), bien qu’inclus dans les données sources, sont masqués dans le code HTML car aucune donnée n’est disponible pour ces territoires concernant le prix au m².

Contours des pays du monde (pour le fond de carte général) : issus du dépôt GitHub Natural Earth Vector.

Structure et fonctionnalités du site
Onglet 2 – Carte 2D interactive
Cet onglet propose une carte interactive en 2D de la France, affichant la valeur foncière moyenne par département. L’utilisateur peut également rechercher une commune spécifique et en consulter la moyenne locale.
Lorsqu’un département est sélectionné, un menu déroulant liste les communes associées, avec la possibilité de trier ces dernières. Des informations complémentaires, telles que le lien vers la page Wikipédia de la commune sélectionnée, sont également accessibles.

Onglet 3 – Carte 3D
Une version tridimensionnelle de la carte précédente est proposée ici. Les communes sont représentées par des polygones extrudés : leur hauteur (axe Z) varie selon la moyenne des valeurs foncières observées. Un filtrage par département est possible via un menu latéral, et des informations contextuelles s’affichent lors de la sélection d’une commune.

Onglet 4 – Histogramme des départements
Cet histogramme permet de visualiser les départements les plus chers et les moins chers en matière de prix au m². Il reprend les mêmes couleurs que les cartes précédentes pour une meilleure lisibilité. Un tri dynamique est possible afin de comparer les territoires plus efficacement.

Onglet 5 – Évolution temporelle
Cette carte permet de suivre l’évolution des prix au m² par département de 2014 à 2023, grâce à un curseur temporel. En cliquant sur un département, un pop-up présente les données correspondantes ; ce pop-up reste visible même lorsque l’année change, facilitant ainsi la comparaison des prix dans le temps.
En complément, un graphique situé en bas de page présente l’évolution moyenne nationale, mettant en évidence une tendance générale à la hausse des prix fonciers sur la période.

Onglet 6 – Infographie régionale
L’infographie présente une analyse ciblée sur cinq départements du littoral sud-est : Gard, Hérault, Bouches-du-Rhône, Var, Alpes-Maritimes.
L’objectif est de mettre en évidence les contrastes régionaux en matière de prix au m², avec une fracture marquée entre les départements les plus accessibles (Gard et Hérault) et ceux aux prix nettement plus élevés (notamment les Alpes-Maritimes).

Cette infographie, réalisée avec l’outil Flourish, repose sur les mêmes données DVF que le reste du site. Elle reste relativement simple en raison du temps limité accordé à sa conception, l’essentiel des efforts ayant été concentré sur la réalisation du site web lui-même.

Limites et remarques
Ce site, bien qu’opérationnel, présente encore certaines lacunes et dysfonctionnements, liés notamment :

à la complexité des données initiales (brutes, parfois incomplètes ou mal interprétées),

au poids de certains fichiers empêchant leur chargement complet,

et à un temps de développement restreint, qui n’a pas permis de finaliser toutes les fonctionnalités souhaitées ni d’approfondir l’analyse graphique ou cartographique.

L’ensemble de ce projet a donc été réalisé dans une logique de prototypage fonctionnel, avec l’objectif de démontrer la faisabilité et la pertinence d’un outil de visualisation interactif basé sur des données publiques.
