# Optimiser-les-flux-de-retours-produits-d-une-usine
## Présentation du projet
L'entreprise Retail&Log livre des articles du quotidien aux particuliers. Certains articles sont fréquemment expédiés et retournés : leur remise en stock mobilise les opérateurs alors qu’ils peuvent être réexpédiés rapidement.
Ma mission consiste à analyser les flux de sorties et de retours pour éclairer leur organisation et l’utilisation envisagée d’une trieuse comme stock intermédiaire.

## Problématique
Quels articles prioriser pour réduire les manipulations de remise en stock et faciliter leur réexpédition ?

## Objectifs principaux
1. Analyser les volumes d’expédition et de retour par article.
2. Identifier les références prioritaires à partir de classifications ABC.
3. Croiser les classes de sorties et de retours pour repérer les articles à forte rotation.
4. Restituer les flux et les priorités dans un tableau de bord Power BI.
5. Permettre une exploration par jour, semaine, classe ABC et score de rotation.
6. Éclairer la réflexion sur la trieuse, avec une capacité de 10 000 emplacements et un séjour maximal de 3 jours par article.

## Jeu de données
Le tableau de bord présente les flux sur mars 2017. Le dictionnaire fourni décrit deux ensembles de données : les sorties et les retours.
| Champ | Description |
| :--- | :--- |
| DATE | Date au format année-mois-jour, stockée comme entier dans la source |
| ARTICLE | Référence de l’article |
| QTE | Nombre d’articles sortis ou retournés |
| SECTEUR | Référence liée à l’entrepôt |
| UNIVERS | Référence de la catégorie de l’article |
| CONTENANT | Référence pour les commerciaux |
| ADRESSE | Référence de traçabilité |

Le modèle Power BI contient les tables de sorties et de retours, une table Calendrier, un Tableau final et des tables TOP20 Sorties et TOP20 Retours. Les fichiers de flux décrits dans le cahier des charges sont des CSV séparés par des points-virgules.

## Outils et technologies
- Power BI Desktop : réalisation du tableau de bord, modèle de données et visualisations interactives.
- DAX : mesures utilisées dans le rapport, notamment le taux de retours global et l’identification des articles communs aux Top 20.
- Analyse ABC et classement des volumes : priorisation des références.
- Classification ABC
Le principe consiste à classer les articles par volume décroissant et à analyser leur contribution cumulée pour distinguer les classes A, B et C. Les sorties et les retours sont étudiés séparément, puis croisés.
- Score de rotation croisé
La méthode proposée dans le cahier des charges attribue un facteur à chaque classe : A = 3, B = 2, C = 1. Le facteur des sorties est multiplié par celui des retours.

## Analyse des flux et des Top 20
Les visualisations comparent les quantités de sorties et de retours dans le temps. Deux classements Top 20 et une vue des articles communs permettent de rapprocher les références les plus expédiées de celles les plus retournées.

## Démarche d’analyse
1. Comprendre le processus métier : retours, remise en stock, préparation, empaquetage et expédition.
2. Analyser les sorties et les retours : classement des références et approche ABC.
3. Croiser les priorités : classes de sorties, classes de retours et score de rotation.
4. Organiser le modèle du rapport : tables de flux, calendrier, tableau croisé des articles et Top 20.
5. Construire les visualisations : indicateurs globaux, évolutions temporelles et répartition des articles par score.
6. Faciliter l’exploration : navigation entre pages, filtres temporels et sélection par classe ou score.

## Résultats finaux
Le livrable est un tableau de bord Power BI structuré en quatre pages.
| Page | Contenu |
| ---: | :--- |
| Accueil | Sorties totales, retours totaux, nombre d’articles analysés, taux de retours global et évolution quotidienne des flux |
| Interactivité et filtres | Explications du fonctionnement des filtres et des interactions |
| Vue globale des flux | Comparaison journalière des sorties et retours, évolutions séparées et filtres par jour et semaine |
| Analyse rotation des articles | Répartition des articles par score, filtres de score et de classe ABC, Top 20 sorties, Top 20 retours et comparaison des articles communs |

Le fichier contient:
- une navigation entre les pages depuis l’accueil ;
- des filtres par jour et semaine sur la vue globale ;
- des filtres par score de rotation et classe ABC sur l’analyse des articles ;
- une information de classe ABC dans les infobulles des visuels de répartition ;
- une comparaison des références présentes dans les Top 20 des deux flux.
  
## Limites de l’étude
- Le rapport couvre mars 2017 : cette période ne permet pas à elle seule de caractériser une saisonnalité annuelle.
- Les retours du mois ne correspondent pas nécessairement aux expéditions du même mois : le ratio global des flux ne représente pas automatiquement un taux de retour par cohorte de commandes.
- Le score croisé est un outil de priorisation ; il ne mesure ni le temps de séjour réel ni la capacité effectivement nécessaire dans la trieuse.
- Les coûts, les gains de temps et le retour sur investissement de la trieuse ne sont pas démontrés par les documents fournis.
  
[Consulter le fichier Power BI](ZOOTYAM_Michelle_1_Tableau_de_bord_122025.pbix)
