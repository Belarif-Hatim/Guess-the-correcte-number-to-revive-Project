open html files with a navigator to run the games
1.	Introduction
1.1	Présentation du Projet
Le projet consiste à développer une application web interactive en JavaScript, HTML et CSS. L’objectif est de créer un jeu où l’utilisateur doit deviner un nombre aléatoire généré par l’ordinateur. Le jeu propose différents niveaux de difficulté (facile, moyen, difficile) qui influencent l’intervalle du nombre à deviner et le nombre de tentatives autorisées.
1.2	Objectif du Site Web
Ce mini-jeu sert de mécanisme de « revive » (retour en jeu) dans un système de jeu principal, avec les fonctionnalités suivantes :

•	Implémenter un système de génération aléatoire de nombres.
•	Permettre à l’utilisateur de choisir un niveau de difficulté.
•	Afficher des retours après chaque tentative ("Trop grand", "Trop petit", "Correct").
•	Calculer et afficher un résultat final.
•	Intégrer le jeu dans une interface utilisateur intuitive et responsive.
1.3	Contexte de Réalisation
Ce projet s’inscrit dans le cadre de projet du deuxième semestre, visant à mettre en pratique les concepts de JavaScript, HTML et CSS. Il permet également d’explorer des mécanismes de jeu interactifs, comme ceux observés dans les fichiers HTML joints (système de "revive" via un mini-jeu de devinette).

2.	Cahier des Charges
2.1	Besoins et Objectifs
Le site web doit répondre aux besoins suivants :
•	Génération aléatoire d’un nombre en fonction de la difficulté choisie.
•	Saisie utilisateur et validation des tentatives.
•	Feedback visuel ("Trop grand", "Trop petit", "Correct").
•	Gestion des vies/tentatives et calcul du score.
•	Interface utilisateur claire et responsive.
 
2.2	Public Cible
Le site web est destiné à plusieurs types d'utilisateurs :

•	Étudiants et enseignants (pour démonstration pédagogique).
•	Joueurs occasionnels.

2.3	Contraintes Techniques

•	Langages : HTML, CSS, JavaScript.
•	Compatibilité : Navigateurs modernes (Chrome, Firefox, Edge).
•	Responsive design (adapté aux mobiles et tablettes).

2.4	Technologies Utilisées
Le site web a été développé en utilisant :

•	HTML5 : Structure de la page.
•	CSS3 : Style et mise en page.
•	JavaScript : Logique du jeu et interactivité.
•	Google Fonts : Typographie moderne.

3.	Conception du Site
3.1	Fonctionnalités Principales
•	1. Menu Principal : 
o	Choix de la difficulté (facile : 1-10, moyen : 1-50, difficile : 1-100).
o	Nombre de tentatives ajusté (ex : 5 pour facile, 7 pour moyen, 10 pour difficile).
 
•	2. Jeu Principal :
o	Saisie du nombre et validation.
o	Nombre de tentatives ajusté (ex : 5 pour facile, 7 pour moyen, 10 pour difficile). 
 


•	3. Fin de Partie :
o	Après le jeu principale on affichent le résultat pendant 2 secondes et afficher le menue principale pour rejouer.
   

4.	Développement
4.1	Structure du Code

•	1 seule Fichier html contient :
<body>
<style></style>//pour le css
<script></script>//pour le javascript
</body>
•	Fonctions JavaScript Clés :
function generateRandomNumber(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

function checkGuess(guess, target) {
  if (guess === target) return "Correct";
  return guess > target ? "Trop grand" : "Trop petit";
}
•	Gestion des Événements :
document.getElementById("guess-button").addEventListener("click", () => {
  const guess = parseInt(document.getElementById("guess-input").value);
  const feedback = checkGuess(guess, targetNumber);
  updateFeedback(feedback);
});
 
4.2	Problèmes Rencontrés et Solutions

Problème :				
•	Validation des entrées utilisateur	
•	Gestion des niveaux de difficulté	
•	L'implémentation d'un mini-jeu comme système de revive dans un jeu vidéo
Solution
•	Utilisation de isNaN() et messages d’erreur.
•	Création d’un objet difficultySettings.
•	l’experimentation

4.3 Démonstration par l'Exemple : Implémentation de Deux Jeux
Pour valider l'efficacité du système de revive basé sur un mini-jeu de devinette, deux prototypes ont été développés :
1. "Combat Revival"
Jeu de combat où le joueur peut revenir après défaite en réussissant un défi de devinette.
Caractéristiques :
•	Système de revive avec 3 niveaux de difficulté
•	Animation de transition fluide
•	Mémorisation du score entre les parties

#le jouer en bleu a attaquer le jouer en rouge 
                   

#après le  jouer a “health“<=0 il existe un boutton pour revive

                  

#Si le jourer qui a été deffi click sur boutton revive il vas jouer le mini jeux guess the number
 









2. " Shoot Balls"
•	Concept : Détruire des balles colorées approchant le joueur.
•	Améliorations apportées :
o	Trois niveaux de difficulté (facile : 1-10, moyen : 1-50, difficile : 1-100).
o	Feedback visuel (couleurs pour "trop haut"/"trop bas").
o	Bonus de vitesse en cas de réussite en mode difficile.
Objectif : Ces implémentations démontrent comment un mini-jeu simple peut :
•	Prolonger l'engagement des joueurs.
•	Ajouter une couche stratégique (choix du risque).
•	Maintenir la tension même après un échec.










#le jouer reste au centre et si une ballon touche lui il mort
                   

#le jour a la possibilité de tirer les ballon
 



#Si un ballon touche le jouer cette scene s’affiche avec un boutton pour revive	

                  

#Si le jourer qui a été deffi click sur boutton revive il vas jouer le mini jeux guess the number
         

“shoot balls” et “Combat Revival” ont été realiser seulement avec javascripte utilisent la tag canvas.

 
 
5.Tests et Validation
1.1	Affichage sur Différents Navigateurs
Le site a été testé et validé sur :

•	Google Chrome
•	Mozilla Firefox
•	Microsoft Edge

1.2	Tests de Responsivité
Le site s'affiche correctement sur :

•	Ordinateurs de bureau
•	Tablettes

6.Conclusion et Perspectives d'Amélioration
6.1 Bilan du Projet

Le projet a permis de créer un jeu fonctionnel, éducatif et interactif. Les mécaniques de base (génération aléatoire, feedback) sont opérationnelles.
6.2 Améliorations Possibles

•	Ajouter un système de highscore avec localStorage.
•	Intégrer des animations CSS pour un meilleur feedback visuel.
•	Étendre le système de "revive" inspiré des fichiers joints.
6.3 Technologies Futures

•	Ajout d’un backend (Node.js) pour sauvegarder les scores. 

