**Problématique et Objectifs **

Le problème consiste à prédire si un client souscrira ou non à un dépôt à terme bancaire après une campagne de marketing direct. L'objectif est de construire un modèle de machine learning qui peut prédire cette probabilité avec une précision raisonnable, afin d'optimiser les futures campagnes de marketing.

Les données sont issues des campagnes de marketing direct de l'institution bancaire portugaise. Chaque entrée représente un client et les détails de ses contacts lors de la campagne. Les features sont les différentes variables disponibles dans les données qui peuvent être utilisées pour prédire la souscription à un dépôt à terme. La variable cible est la souscription à un dépôt à terme (oui/non).

Nous allons traiter ce probleme comme une classification, car la tâche est de prédire une variable binaire : la souscription ou non à un dépôt à terme. Les problèmes où la variable cible est une catégorie discrète sont généralement traités comme des problèmes de classification. Nous chercherons à attribuer chaque client à une classe spécifique, ce qui est la caractéristique d'un problème de classification.



** Les données que nous utiliserons sont organisées de la maniere suivante :**

    Nombre d'instances : 45211

    Nombre d'attributs : 16 + attribut de sortie.

Attributs : âge (numérique), emploi(catégorique), matrimonial (catégorique), éducation (catégorique), défaut (binaire), solde (numérique), logement (binaire), prêt (binaire), contact (catégorique), jour (numérique), mois (catégorique), durée (numérique), campagne (numérique), pdays (numérique), précédent (numérique), poutcome (catégorique).

Variable de sortie (cible souhaitée) : y - le client a-t-il souscrit à un dépôt à terme ? (binaire : "oui", "non")


** Apres avoir procédé au pré-traitement des données**

    -suppression des colonnes vides et colonnes avec valeurs manquantes

    -encodage

    -division en ensembles (entraînement, validation, test)

    -sur-échantillonage(équilibre de classe)

** Nous avons suivi ces étapes pour déterminer un modele optimale :**

    Évaluation des modèles : Nous avons évalué plusieurs modèles en utilisant la validation croisée pour comparer leurs performances. Cela nous a permis de voir comment chaque modèle se comporte sur notre jeu de données et de sélectionner les modèles qui donnent les meilleurs résultats en termes de métriques d'évaluation telles que l'exactitude, la précision et le rappel. En considérant ces facteurs, la forêt aléatoire semble être le meilleur modèle, car elle a la plus haute précision globale et des performances relativement bonnes en termes de précision et de rappel pour les deux classes. Cependant, il est important de considérer d'autres aspects, le choix dépendra des besoins spécifiques du problème et des compromis entre la précision et le rappel que nous sommes prêts à faire. La courbe ROC nous montre que la Forêt Aléatoire est le modele produisant le moins d'erreur.La courbe de Gain cumulatif nous montre que le modèle le plus performant, identifiant efficacement les exemples positifs, est la Forêt Aléatoire. La courbe d'apprentissage convergeant le mieux et le plus possible est celle de la Forêt Aléatoire, c'est ce modele qui est le mieux généralisé.

    Détermination des paramètres optimaux: Après avoir évalué les modèles, nous avons utilisé la recherche par grille (GridSearchCV) pour déterminer les meilleurs hyperparamètres pour chaque modèle. Cela nous permet d'optimiser les performances de chaque modèle en réglant les paramètres qui les contrôlent. Pour la Forêt Aléatoire, les paramètres optimaux sont une profondeur maximale de 3, un nombre minimal d'échantillons par feuille de 0.05 et 300 arbres de décision à construire.

    Scaling (Mise à l'échelle) : La mise à l'échelle des données est une étape de prétraitement supplémentaire qui peut être bénéfique pour certains modèles. La comparaison des performances des modèles montre que l'effet de la mise à l'échelle des données varie selon l'algorithme : tandis que KNN et la Forêt Aléatoire semblent moins performants avec la mise à l'échelle, le modèle Naive Bayes bénéficie d'une amélioration significative de sa performance.



    Décision finale : Au terme de nos analyses approfondies, la Forêt Aléatoire émerge comme le choix optimal, démontrant une précision globale supérieure, des bonnes performances en termes de précision et de rappel pour les deux classes, ainsi qu'une plus grande stabilité et généralisation confirmées par les courbes ROC, de gain cumulatif et d'apprentissage.
