# Accidents
2A ENSAE 2021/2022

Projet de Python pour le data scientist (2021-2022) :  ***Prédire le nombre et la mortalité des accidents corporels de la route***

### DUJARDIN Thomas, RONDEY Hélène, ROSUNEE Avichaï

___________________________________________________________________________________________________________________________________________________________________________________

### Données utilisées et exploitées: 

Utilisation des bases de données annuelles des accidents corporels de la circulation routière - Années de 2005 à 2020 disponibles à l'adresse : https://www.data.gouv.fr/fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2020/#resources

Une description détaillée des variables des quatre bases, réalisée par l'ONISR (Observatoire national interministériel de la sécurité routière) est disponible [ici](https://github.com/helene-78/Accidents/blob/main/description-des-bases-de-donnees-onisr-annees-2005-a-2020.pdf)

Les données rassemblées sur ces accidents font partie du Fichier BAAC, administré par l'ONISR, qui décrit la saisie de ces données de la manière suivante :
*"Pour chaque accident corporel impliquant au moins un véhicule et ayant fait au moins une victime ayant nécessité des soins, des saisies d’information décrivant l’accident sont effectuées par l’unité des forces de l’ordre (police, gendarmerie, etc.) qui est intervenue sur le lieu de l’accident. "*

Nous exploitons les données de l'année 2019 (plus de 130 000 entrées).

### Liens vers le projet:

[***Projet_complet***](https://github.com/helene-78/Accidents/blob/main/Projet_complet.ipynb) est le notebook du projet avec l'entièreté du code commenté

 [***df_utiles***](https://github.com/helene-78/Accidents/blob/main/df_utiles.csv) contient la fusion des bases de données utilisées dans ce projet (*caracteristiques-2019.csv*, *usagers-2019.csv*, *lieux-2019.csv*, *vehicules-2019.csv*) disponibles dans le dossier [**Bases de données**](https://github.com/helene-78/Accidents/tree/main/Bases%20de%20donn%C3%A9es)

### Plan du projet

**Installation et chargement des modules**

**I) Fusion des bases, sélection et reformatage des variables**

**II) Analyse descriptive**
 - Description de quelques variables
 - Matrice des corrélations
 
**III) Première modélisation : prédire le nombre d'accidentés grâce aux séries temporelles**

Nous réalisons un fit avec un modèle Sarimax puis prédisons 31 valeurs du nombre d'accidents par jour, sur le mois de Janvier 2020. Nous comparons graphiquement dans le Dash notre prédiction et la réalité. Bien que le graphe d'autocorrélation généré suggère que le dernier paramètre de seasonal_order devrait être 7, nous prenons 32, car prendre 7 obligerait à utiliser un ordre de 6 (Xt+1 = Xt + Xt-1 + ... Xt-5 où Xt := nombre de victimes d'accidents au jour t), ce qui ne fournit pas de prédictions réalistes.

**IV) Visualisation sur une carte interactive**

Toujours dans l'optique de visualier le nombre d'accidents, la carte interactive permet de visualiser les emplacements des accidents en France et dans le temps. 

Cette partie nécessite, pour pouvoir visualiser la carte dans le Notebook, de:
 1) soit utiliser la cellule au-dessus pour permettre le "unverified context"
 2) soit réaliser l'opération suivante : "" Make this Notebook Trusted to load map: File -> Trust Notebook" (Message rencontré sur JupyterLab).

**La carte a également été sauvegardée en html.**

**V) Entraînement d'un réseau de neurones pour prédire la mortalité (variable "grav")**

Nous nous intéressons cette fois à la mortalité des accidents grâce à un modèle de réseau de neurones. 

**VI) Interface Dash**

L'interface reprend la carte interactive, la prédiction par séries temporelles en affichant la prédiction sur janvier 2020, et enfin permet de prédire la mortalité d'un accident, en choisissant soi-même les modalités, à partir du modèle de Réseau de neurones que nous avons entraîné.
**Le code doit être compilé entièrement pour avoir accès au Dash. Les parties qui chargent le plus longtemps sont la construction du modèle Sarimax  (III) et l'affichage des cartes (IV), qui pourront être sautés pour voir l'interface plus rapidement**.
