# 🎮 Mini-Jeu "Guess The Number" – Système de Revive Web

## 📘 Présentation du Projet

Ce projet est une application web interactive développée en **HTML**, **CSS** et **JavaScript**. Le but est de créer un **mini-jeu de devinette** dans lequel l'utilisateur doit deviner un nombre aléatoire généré par l'ordinateur.

Ce jeu sert de **mécanisme de "revive"** dans des jeux plus complexes comme "Combat Revival" et "Shoot Balls".

---

## 📌 Objectifs du Jeu

- Générer un nombre aléatoire.
- Choisir un **niveau de difficulté** (facile, moyen, difficile).
- Donner un **feedback en temps réel** ("Trop grand", "Trop petit", "Correct").
- Afficher un **résultat final** après les tentatives.
- Interface responsive et intuitive.

---

## 🧩 Fonctionnalités Principales

- 🎚️ **Choix de la difficulté :**
  - Facile : 1-10 (5 tentatives)
  - Moyen : 1-50 (7 tentatives)
  - Difficile : 1-100 (10 tentatives)

- 🎮 **Système de jeu :**
  - Saisie et validation des nombres.
  - Feedback après chaque essai.
  - Réaffichage du menu principal après 2 secondes à la fin de la partie.

- 🔁 **Réutilisation dans d'autres jeux :**
  - Intégré dans des jeux comme "Combat Revival" et "Shoot Balls" comme système de revive.

---

## 📂 Structure du Code

Le jeu est contenu dans **un seul fichier HTML** :

```html
<body>
  <style>/* CSS ici */</style>
  <script>
    // JS ici
    function generateRandomNumber(min, max) {
      return Math.floor(Math.random() * (max - min + 1)) + min;
    }

    function checkGuess(guess, target) {
      if (guess === target) return "Correct";
      return guess > target ? "Trop grand" : "Trop petit";
    }

    document.getElementById("guess-button").addEventListener("click", () => {
      const guess = parseInt(document.getElementById("guess-input").value);
      const feedback = checkGuess(guess, targetNumber);
      updateFeedback(feedback);
    });
  </script>
</body>
