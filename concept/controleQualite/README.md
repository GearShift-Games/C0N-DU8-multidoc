# Paragraphe de présentation


CON D83 (conduite) est un jeu de course interactif intense plein de rebondissements et légèrement humoristique dans lequel l'utilisateur contrôle son véhicule à l'aide d'un vélo stationnaire.

# MVP (Minimal Viable Product)

## Visuel

- Un modèle de véhicule simple
- Un circuit de course simple
- Un UI simple

## Audio

- Musique d'ambiance
- bruits de véhicule

## Interactivité

- Mouvements détectés par senseurs
- Frein fonctionel
- Fin de la course

## Matériel

- 1 Projecteur
- 1 Vélo Stationnaire
- 2 Hauts Parleurs
- 1 capteur opencv blob tracking centroid
- 1 Écran Tactile
- 2 Bouton
 


# [Lien GitHub](https://github.com/GearShift-Games/CON-D83/tree/main)

# Date de livraison des test :

### 28 Février 2025

# Risques:

- R1: Détection des mouvements de l'utilisateur marche pas(tourner)
- R2: Détection des pédales marche pas
- R3: Détection des intreractions inconsistante
- R4: Problèmes de projection
- R5: On arrive pas à utiliser Unreal Engine
- R6: Une personne se blesse durant l'utilisation du projet
- R7: Le vélo stationnaire tombe
- R8: Projection pas clair (trop de lumière)
- R9: un des membre de l'équipe ne peux pas participer pour certaines raisons
- R10: Un bris / usure de matériel
- R11: controle du ventilateur selon la vitesse

![img/risques.drawio.png](img/risques.drawio.png)

Initialement on vas tester Unreal Engine et si on arrive pas à de manière efficace rapidement, on commence à travailler dans unity. (R5)

Nous allons continuer par nous assurer dans les premières semaines que le capteur de mouvement détecte la position de l'utilisateur et retourne une valeur gauche / droite selon la distance par rapport au millieu. (R1) 

Ensuite, nous nous assurerons que la détection de pédales fonctionnent selon la vitesse que l'utilisateur pédale (R2) et que la vitesse de transmission des données ne soit pas inconsistante. (R3) Nous allons aussi trouver un moyens de changer la vitesse du ventilateur selon la vitesse des pédales. (R11)

Selon le lieu, nous allons vérifier l'éclairage (R8) et l'espace nécessaire pour la projection durant la présentation. (R4)

Pour réduire les chances de blessure de l'utilisateur, nous allons tester par nous même des scénario et des possibilité de blessure et nous allons nous informé des information nécessaire avec les gardes. Selon le lieu, nous aurons des garde de sécurité pour nous aider et / ou une personne de notre équipe capable de premier soin mineure. (R6) Durant ces test, nous allons voir a quel point une personne peux se pencher avant que le vélo deviennent instable et si le point d'équilibre est trop proche ou restrictif, nous allons trouver une façons de le rendre plus stable. (R7)

Si il y a un bris de matériel ou une partie du projet trop usé et que l'on doit la remplacer, nous aurons des pièces de rechange. (R10)

# Tests à réaliser
## Scénarios
 
| Scénario 1 | L'utilisateur n'a pas encore été détecté par le capteur. Il voit un avant-goût de l'oeuvre par une vidéo en boucle projeter à l'écran.  |
|------------|---|
 
| Identification    | 1.1  Projection déclanché par défault|
|-------------------|---|
| Priorité          | Faible  |
| Date Limite       |  25 Février 2025 |
| Description       | S'assurer que dès le lancement de l'oeuvre, une vidéo joue en boucle |
| Contraintes       | Pouvoir détecter quand aucun utilisateur n'est présent pour entrer en veille. |
| Dépendances       | S'assurer que le l'ordinateur et la projection communiquent en harmonie.  |
| Procédure de test |  Données d’entrée : Vidéo de départ Résultats attendus : Projection de la vidéo. Critères de validation : On voit la vidéo. |
| Résultat          |   |
 
| Scénario 2 |  L'utilisateur est détecté par le capteur.|
|------------|---|
 
| Identification    | 2.1  Vidéo arrêter par la détection de l'interracteur|
|-------------------|---|
| Priorité          | Faible |
| Date Limite       | 28 Février 2025  |
| Description       | S'assurer que dès le lancement de l'oeuvre, une vidéo joue en boucle jusqu'à ce qu'un utilisateur soit détecté.|
| Contraintes       | Configurer le capteur afin de s'assurer que seulement la présence d'un utilisateur soit détecter.  |
| Dépendances       | S'assurer que le capteur et la projection communiquent en harmonie.  |
| Procédure de test | Données d’entrée : Vidéo de départ, entrée de l'utilisateur Résultats attendus : Projection de la vidéo interrompu par la présence de l'utilisateur. Critères de validation : Vidéo interrompu, le menu apparâit. |
| Résultat          |   |
 
| Identification    | 2.2  L'utilisateur n'est plus détecté par le capteur. La vidéo du départ reviens
|-------------------|---|
| Priorité          | Faible  |
| Date Limite       | 28 Février 2025  |
| Description       | S'assurer que si le capteur arrête de capté un utilisateur pour plus de 10 secondes, la vidéo continue ou elle c'était arrêtée.  |
| Contraintes       | Configurer le capteur afin qu'il détecte qu'il n'y a plus d'utilisateur  |
| Dépendances       | S'assurer que le capteur, l'ordinateur et la projection communiquent en harmonie.  |
| Procédure de test | Données d’entrée : Menu principal, départ de l'utilisateur Résultats attendus : Compte à rebourd lancé . Critères de validation : La vidéo par défault reprend ou elle c'était arrêtée 10 secondes apres le départ de l'utilisateur |
| Résultat          |   |
 
| Scénario 3 | L'utilisateur interragit avec le menu.  |
|------------|---|
 
| Identification    | 3.1  Choix du véhicule|
|-------------------|---|
| Priorité          | Faible  |
| Date Limite       | 15 Février 2025  |
| Description       | S'assurer que l'utilisateur est capable de naviguer à travers le menu et de modifier son véhicule par défaut. |
| Contraintes       | Configurer les boutons pour produire des intéractions différentes dépendamment de si l'utilisateur est dans un menu ou une course. |
| Dépendances       | S'assurer que les boutons additionnels puissent communiquer parfaitement avec l'ordinateur.  |
| Procédure de test | Données d’entrée : Interaction utilisateur. Résultats attendus : Modifications visuels du véhicules. Critères de validation : On voit les modifications à l'écran. |
| Résultat          |   |
 
| Identification    | 3.2  Départ de la course|
|-------------------|---|
| Priorité          | Extrême  |
| Date Limite       | 13 Février 2025  |
| Description       | S'assurer que l'utilisateur est capable de lancer une course |
| Contraintes       | Faire que le changement de scène entre le menu et la course sélectionnée soit fonctionnel et fluide. |
| Dépendances       | S'assurer que le menu soit fonctionnel et puisse envoyer d'une façon dynamique la course sélectionnée aux scripts.  |
| Procédure de test | Données d’entrée : Interraction utilisateur Résultats attendus : Changement de scène Critères de validation : Lancement de la course à l'écran |
| Résultat          |   |
 
| Scénario 4 | L'utilisateur interragit avec le vélo stationnaire  |
|------------|---|
 
| Identification    | 4.1  L'utilisateur pédale|
|-------------------|---|
| Priorité          | Extrême  |
| Date Limite       | 7 Février 2025  |
| Description       | S'assurer que les mouvements des pédales font avancer le véhicule |
| Contraintes       | Détecter la vitesse au quel l'utilisateur pédale puit pouvoir l'utiliser dans notre jeu pour attribuer en variable au véhicule. |
| Dépendances       | Avoir le vélo staionnaire, ce n'est pas quelque chose qui peut être testé avec précision par une simulation.  |
| Procédure de test | Données d’entrée : Donnés Arduino de mouvement des pédales Résultats attendus : Donnés transformé en vélocité affectant le véhicule. Critères de validation : On voit le véhicule avancé relativement à la vitesse du vélo. |
| Résultat          |   |
 
| Identification    | 4.2  L'utilisateur Freine|
|-------------------|---|
| Priorité          | Faible  |
| Date Limite       | 14 Février 2025  |
| Description       | S'assurer que lorsque l'utilisateur utilise le frein, le véhicule rallenti jusqu'a s'immobiliser |
| Contraintes       | Détecter la vitesse des pédales pour attibuer la réduction de vitesse appropriée. |
| Dépendances       | Avoir une connection entre l'ordinateur et le vélo pour processer l'information nécessaire du vélo stationnaire.  |
| Procédure de test | Données d’entrée : Donnés Arduino de l'actionnement du frein Résultats attendus : Donnés transformé en vélocité affectant le véhicule. Critères de validation : On voit le véhicule ralentir relativement au maintient du frein sur le vélo. |
| Résultat          |   |
 
| Identification    | 4.2  L'utilisateur utilise le turbo|
|-------------------|---|
| Priorité          | Faible  |
| Date Limite       | 17 Février 2025  |
| Description       | S'assurer que lorsque l'utilisateur appuie sur le bouton du turbo, le véhicule va 2 fois plus vite que sa vitesse maximal pendant une période de 3 secondes |
| Contraintes       | Faire que l'utilisateur ne ressent pas que l'immersion est cassée. |
| Dépendances       | Avoir la détection du bouton vers l'ordinateur d'un façon très rapide pour ne pas faire que l'utilisateur attend un peu pour un boost qui est supposé amené une certaine satisfaction. |
| Procédure de test | Données d’entrée : Donnés Arduino de l'actionnement bouton Résultats attendus : Donnés transformé en vélocité affectant le véhicule et neutralisant pendant le temps du turbo la relation entre les pédales et la vélocité. Critères de validation : On voit le véhicule accélérer rapidement pendant 3 secondes. |
| Résultat          |   |
 
| Identification    | 4.3  L'utilisateur se penche afin de tourner|
|-------------------|---|
| Priorité          | Extrême  |
| Date Limite       | 10 Février 2025  |
| Description       | S'assurer que lorsque l'utilisateur se penche dans une certaine direction, le capteur tourne le véhicule en fonction de cette direction. |
| Contraintes       | Détecter correctement le penchement d'un utilisateur et s'assurer que la présence de quelqu'un qui passe n'interfère pas avec la détection de la direction de l'utilisateur. De plus, l'intégration de faire que plus qu'on se tourne d'un côté, plus le véhicule tourne de ce côté. |
| Dépendances       | Avoir l'appareil installé sur le vélo stationnaire pour pouvoir comprendre comment détecter où l'utilisateur serait s'il n'est pas penché, mais également où il serait quand il est penché. |
| Procédure de test |  Données d’entrée : Donnés Arduino du capteur Résultats attendus : Donnés transformé en direction gauche/droite affectant la direction du véhicule Critères de validation : Quand l'utilisateur se penche vers la droite/gauche le véhicule tourne dans cette direction. |
| Résultat          |   |
