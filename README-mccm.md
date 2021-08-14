

# Project - Analyse de la performance d'un cabinet d'expertise comptable
Amandine Gauberville

*[27-07-2021]*

![image](https://drive.google.com/file/d/1py4N9DlSN3Ul8JxaPwWBxmN7Tbr9-jZp/view?usp=sharing)

## Content
- [Project Description](#project-description)
- [Dataset](#dataset)
- [Workflow](#workflow)
- [Links](#links)

<a name="project-description"></a>

## Project Description

A partir des données de gestion interne d'un cabinet d'expertise comptable dispensant une offre de services diversifiée, nous allons effectuer un diagnostic de la performance de ce cabinet en nous basant sur le comparatif des données de prix de revient avec les données du chiffre d'affaires.

Lorsque la différence entre le chiffres d'affaires et le prix de revient est positive, nous appellerons cela un "boni". A l'inverse, lorsque la différence sera négative, nous appellerons cela un "mali".

Avec des modèles de machine learning d'apprentissage supervisé de régression, nous allons prédire le prix de revient d'une mission. 

Les objectifs de cette prédiction sont les suivants :
- Eviter les malis en donnant le bon coût, ainsi nous pouvons anticiper le montant total hors taxe à facturer au client
- Améliorer la rentabilité des missions 

Avant d'arriver à prédire ce prix de revient, il est important d'analyser les features qui pourront avoir une influence sur ce dernier. L'ensemble de l'analyse se trouve dans le fichier suivant : [Data EDA](https://github.com/AmandineGauberville/mccm_project/blob/master/Data%20EDA.ipynb) 

L'étude porte sur les années 2017, 2018, 2019 et 2020.

<a name="hypotheses-/-questions"></a>


## Dataset

Le dataset est issu des données exportées du logiciel CEGID Expert utilisé dans le cadre de la gestion interne de ce cabinet.

Les données récoltées par année sont :

- Temps passé par un collaborateur sur une activité d’une mission 
- Manager dédié par mission
- Factures de l’ensemble de la clientèle
- Données clients

Ces données sont ensuite compilées pour obtenir le dataset final avant analyse.

Le dataset est composé de 35 583 lignes pour 197 colonnes.

Codebook : [Codebook](https://github.com/AmandineGauberville/mccm_project/blob/master/Codebook.xlsx) 


<a name="workflow"></a>


## Workflow
Les étapes de cette analyse de données ont été :

1. La constitution du "dataset ML" sur Python
    - Export et concaténation des données de CEGID Expert en fichiers csv. issus de différents modules soit 11 fichiers exportés.
    [Dataset-2017]
    [Dataset-2018]
    [Dataset-2019]
    [Dataset-2020]
    
2. Datacleaning sur Python
    - Suppression des valeurs nulles
    - Suppression des outliers
    - Création de bag of words (types de mission, activités et formes juridiques)
    
    
3. Analyse exploratoire des données sur Python
    - Dans un premier temps, l'analyse est effectuée de manière univariée
    - Dans un second temps, nous avons tenté de croiser les données par analyse bi-variée puis multivariée. [Data EDA](https://github.com/AmandineGauberville/mccm_project) 

4. Datavisualisation sur Tableau public
    - Traduction des éléments d'analyse sur des graphiques plus complets
    - Storytelling
    - Création d'un dashborad pour évaluer la performance par manager
    
    
5. Machine learning
    - Test de 8 modèles ML de régression en cross-validation
    - Le modèle lightGBMRegressor, le plus performant est retenu
    - Mean Absolute Error de 189€ sur le test
    [Data ML](https://github.com/AmandineGauberville/mccm_project/blob/master/Data%20ML.ipynb)


## Links

[Repository](https://github.com/AmandineGauberville/mccm_project)  
[Slides](https://docs.google.com/presentation/d/19-X6aq5-QMRwRKBfQN-2gLHbQ45Q1O5W/edit?usp=sharing&ouid=114312886424634733159&rtpof=true&sd=true)
[Storytelling](https://public.tableau.com/app/profile/gauberville.amandine/viz/mccm/Storytelling)
[Dashboard](https://public.tableau.com/app/profile/gauberville.amandine/viz/Performance-mgr-2020/TBDmgr)
