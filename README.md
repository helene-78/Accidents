# Accidents
2A ENSAE 2021/2022

Projet de Python pour le data scientist (2021-2022) :  ***Prédire le nombre et la mortalité des accidents corporels de la route***

#### DUJARDIN Thomas, RONDEY Hélène, ROSUNEE Avichaï

___________________________________________________________________________________________________________________________________________________________________________________



Utilisation des bases de données annuelles des accidents corporels de la circulation routière - Années de 2005 à 2020 disponibles à l'adresse : https://www.data.gouv.fr/fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2020/#resources

Une description détaillée des variables des quatre bases, réalisée par l'ONISR (Observatoire national interministériel de la sécurité routière) est disponible [ici](https://github.com/helene-78/Accidents/blob/main/description-des-bases-de-donnees-onisr-annees-2005-a-2020.pdf)

Les données rassemblées sur ces accidents font partie du Fichier BAAC, administré par l'ONISR, qui décrit la saisie de ces données de la manière suivante :
*"Pour chaque accident corporel impliquant au moins un véhicule et ayant fait au moins une victime ayant nécessité des soins, des saisies d’information décrivant l’accident sont effectuées par l’unité des forces de l’ordre (police, gendarmerie, etc.) qui est intervenue sur le lieu de l’accident. "*

Exploitation des données de l'année 2019 (plus de 130 000 entrées) 

[***Projet_complet***](https://github.com/helene-78/Accidents/blob/main/Projet_complet.ipynb) est le notebook du projet avec l'entièreté du code commenté

 [***df_utiles***](https://github.com/helene-78/Accidents/blob/main/df_utiles.csv) contient la fusion des bases de données utilisées dans ce projet (*caracteristiques-2019.csv*, *usagers-2019.csv*, *lieux-2019.csv*, *vehicules-2019.csv*) disponibles dans le dossier [**Bases de données**](https://github.com/helene-78/Accidents/tree/main/Bases%20de%20donn%C3%A9es)


Le code doit être compilé entièrement pour avoir accès au Dash. La partie qui charge le plus est la construction du modèle Sarimax, qui pourra être sautée pour voir  l'interface Dash.

De plus la partie Carte Interactive nécessite, pour pouvoir visualiser la carte dans le Notebook, de 1) soit utiliser la cellule au-dessus pour permettre le "unverified context" 2) soit réaliser l'opération suivante : "" Make this Notebook Trusted to load map: File -> Trust Notebook" (Message rencontré sur JupyterLab). La carte a également été sauvegardée en html.