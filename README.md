# Jeu de yams avec site web pour revoir les parties finies

## Description

**Projet universitaire**

Jeu de yams jouable en console à deux joueurs (sur le même ordinateur) fait en C#.  
Les résultats des parties finies peuvent être consultés sur le site web grâce à un fichier JSON créé à chaque fin de partie.

Exemple du tour d'un joueur :
```
======PSEUDOS======
===================
Pseudo joueur 1 : a
Pseudo joueur 2 : b
===================
===================

 


=======RÉCAP=======
a
===================
Nombre de 1 : 
Nombre de 2 : 
Nombre de 3 : 
Nombre de 4 : 
Nombre de 5 : 
Nombre de 6 : 
Brelan : 
Carré : 
Full : 
Petite suite : 
Grande suite : 
Yams : 
Chance : 
===================
Total : 0
===================
===================


========DÉS========
===================
 3  2  1  1  4 
===================
===================
Quel(s) dé(s) changer ? (les mettre à la suite sans espace et mettre 0 si aucun dé à changer)
3

========DÉS========
===================
 3  2  1  1  4 
===================
===================
Quel(s) dé(s) changer ? (les mettre à la suite sans espace et mettre 0 si aucun dé à changer)
3


=====DÉS FINAUX====
===================
 3  2  4  1  4 
===================
===================

Choisir le challenge

 | 1: Nombre de 1
 | 2: Nombre de 2
 | 3: Nombre de 3
 | 4: Nombre de 4
 | 5: Nombre de 5
 | 6: Nombre de 6
 | 7: Brelan
 | 8: Carré
 | 9: Full
 | 10: Petite suite
 | 11: Grande suite
 | 12: Yams
 | 13: Chance


 Entrez le code du challenge choisi
10


=======RÉCAP=======
a
===================
Nombre de 1 : 
Nombre de 2 : 
Nombre de 3 : 
Nombre de 4 : 
Nombre de 5 : 
Nombre de 6 : 
Brelan : 
Carré : 
Full : 
Petite suite : 30
Grande suite : 
Yams : 
Chance : 
===================
Total : 30
===================
===================
```

## Technologies utilisées

**Langage de l'application :** C#

**Stockage des informations d'une partie :** fichier JSON

**Site web :** HTML, CSS, JavaScript

## Installation

Cloner le repo :
```bash
git clone https://github.com/FireFeather5/Jeu-de-Yams
```
Ou télécharger tous les fichiers à la main.

## Lancement du jeu

### Utilisation avec `mono` sous Linux

Si `mono` n'est pas installé :
```bash
sudo apt install mono-complete
```

Lancer le fichier :
```bash
mono Application-Yams.exe
```

## Lancement du site web

> [!NOTE]  
> Dans le dosier `site-web-ne-fonctionnant-pas`, le fichier JSON était récupéré depuis un serveur de l'IUT n'étant plus disponible aujourd'hui. J'ai donc fait une nouvelle version du site (`site-web`) pour en avoir une opérationnelle même sans le serveur de l'IUT, qui récupère le fichier JSON en local.

Ouvrir la page `pageHTML.html` du dossier `site-web` avec un navigateur web.

### Changer de fichier JSON

Changer l'extention du fichier `.json` en `.js` et mettre
```js
const data =
```

Au début du fichier.

Mettre le nouveau fichier `.js` dans le dossier `site-web` (à la racine).

Ouvrir la page `pageHTML.html` avec un éditeur de code et modifier la ligne
```js
<script src='partie1.js'></script>
```
par
```js
<script src='[nom_du_nouveau_fichier].js'></script>
```

## Fonctionnalités

### Application C#

L'application C# permet à deux joueurs de faire une partie de yams dans un terminal en mode console.  
À la fin de la partie, le joueur ayant le plus de points est déclaré gagnant.

### Fichiers JSON

À la fin d'une partie, un fichier JSON est généré. Il peut servir à revoir les résultats de la partie dans le site web.

### Site web

Le site web sert à afficher les scores et le gagnant d'une partie stockée dans un fichier JSON "chargé" dans le site.

#### Affichage tour par tour

L'affichage tour par tour permet de voir les différents scores de dés obtenus, le challenge choisi et le nombre de points gagnés par le joueur dans le tour actuellement affiché. En bas se trouvent les résultats finaux de la partie.

![Capture d'écran du site quand l'affichage tour par tour est séléctionné](https://github.com/FireFeather5/Jeu-de-Yams/blob/main/images/yams-tpt.png?raw=true)

#### Résumé rapide

Le résumé rapide n'affiche que les résultats finaux de la partie.

![Capture d'écran du site quand l'affichage du résumé rapide est séléctionné](https://github.com/FireFeather5/Jeu-de-Yams/blob/main/images/yams-gene.png?raw=true)
