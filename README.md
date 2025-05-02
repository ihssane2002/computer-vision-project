
# YOLOv8 Computer Vision Model - Detection de Personnes & Évaluation 5S

Ce projet a été réalisé dans le cadre d’un projet enjeu en collaboration avec **Tecpap** et **Coca-Cola**, visant à améliorer la sécurité industrielle et l'organisation des espaces de travail selon la méthode 5S.

Le modèle développé est basé sur **YOLOv8** pour :
-  Détecter la présence humaine dans une zone dangereuse.
-  Calculer automatiquement le **score 5S** à partir d’images du poste de travail.

##  Contenu du dépôt

- `YOLOv8_Computer_Vision_Model.ipynb` : Notebook principal pour l’entraînement et l’inférence.
- `README.md` : Ce fichier.
  
##  Jeu de données

Nous avons utilisé une base d’images annotées couvrant **11 classes** :
['May_Bom_Nuoc_A', 'May_Bom_Nuoc_B', 'May_Do_NhietDo_MT', 'May_Do_Nuoc',
'Person', 'as_no_helmet', 'as_with_helmet', 'no_suit', 'obstacle',
'person', 'robot']

- Télécharger ici : [Lien Google Drive](https://drive.google.com/file/d/1O7R7WCfmPGqnIzgOo1KCilnQcINOkifN/view?usp=sharing)
- Base de données trouvée sur la plateforme Roboflow, puis réorganisée pour l'entraînement YOLOv8 (train/, val/, test/, data.yaml).

Les annotations sont prêtes pour l'entraînement YOLO.

##  Modèle entraîné

Nous avons utilisé **YOLOv8** pour entraîner un modèle de détection. Voici les principales métriques obtenues :

| Métrique                 | Valeur         |
|--------------------------|----------------|
| Precision (B)            | 0.9227         |
| Recall (B)               | 0.8826         |
| mAP@0.5 (B)              | 0.9343         |
| mAP@0.5:0.95 (B)         | 0.6754         |
| Fitness                  | 0.7012         |


## Fonctionnalités

### 1. **Détection de présence dans une zone dangereuse**
Le modèle détecte si une **personne** est présente dans une zone marquée comme dangereuse .

- Si une personne est détectée dans la zone : `return 1`
-  Sinon : `return 0`

🔽 Exemple visuel (à insérer dans `assets/`):
![Zone Dangereuse](images/danger.jpg)

---

### 2. **Calcul du score 5S**
À partir d’une image du poste de travail, le modèle détecte les éléments non conformes (désordre, obstacles, équipements de sécurité manquants) pour estimer un **score 5S** automatiquement.

🔽 Exemple visuel :
![Score 5S](images/5s.jpg)

---

##  Utilisation du Notebook

1. Ouvrir le notebook [`YOLOv8_Computer_Vision_Model.ipynb`](YOLOv8_Computer_Vision_Model.ipynb) sur Google Colab.
2. Suivre les cellules pour :
   - Charger les données
   - Entraîner le modèle (ou charger un modèle pré-entraîné)
   - Lancer les détections sur images ou vidéos
  
 ##  Perspectives
Dans le cadre de la continuité du projet, nous envisageons d’utiliser ce modèle YOLOv8 pour analyser des images réelles capturées dans les locaux des entreprises partenaires :

### - Tecpap 

### - Coca-Cola 

L’objectif est de tester la robustesse du modèle sur des données du terrain et d’adapter les détections à des scénarios spécifiques (PPE, obstacles, non-conformités…).





