# OCR_P5_Tag_Predictions

Projet dont le but est de proposer des tags pour catégoriser une question posée sur le site de [Stak Overflow](https://stackoverflow.com).

Les données ont été extraites de [stackexchange explorer](https://data.stackexchange.com/stackoverflow/query/new) et prétraitées :
- supprimer les balises html (librairie utilisée : BeautifulSoup) ;
- tokenisation du texte (librairie utilisée : NLTK) ;
- ne garder que les noms communs (librairie utilisée : NLTK) ;
- normaliser les mots : lemmatisation ou stemmatisation (librairie utilisée : NLTK).

Les données ont ensuite été filtrées et la liste des mots avec une occurence supérieureà 1400 a été conservée.

Deux approches ont été envisagées :
- une non supervisée avec Latent Dirichlet Allocation (LDA)
- une supervisée comparant :
  - DummyClassifier
  - KNeighborsClassifier 
  - LinearSVC couplé à OneVsRestClassifier 
  - RandomForestClassifier 

Les métriques utilisées sont accuracy, precision, recall et score F1.

Une comparaison a été effectuée entre les deux approches.

2 notebooks ont été réalisés : un d'exploration et un de modélisation. Une présentation et un rapport accompagnent ce projet.

Par ailleurs, deux APIs ont été développées pour effectuer la prédiction de tags :
- une sur FastAPI dont le GitHub est disponible [ici]()
- une sur [Streamlit]() dont le GitHub est disponible [ici]()
