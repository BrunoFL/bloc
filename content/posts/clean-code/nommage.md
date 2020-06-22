---
title: "Clean Code, coder proprement, le nommage"
date: 2020-06-20T17:18:00+0200
lastmod: 2020-06-120
draft: true
tags: 
- clean code
- dev
- resume
- JAVA
- JavaScript
keywords: 
- clean code
- dev
- coder
- proprement
- resume
- code
toc: true
---
Cet article fait partie d'une suite sur clean code, un petite [intro]({{< ref "/posts/clean-code/resume.md" >}}) est disponible :smile:.

Ce n'est pas pour rien que c'est le premier chapitre. Le nommage est un des points les plus importants !
C'est ce qu'on lit le plus, les variables, les fonctions, les classes, ...
Avoir un nommage mauvais rend completement impossible la compréhension d'un code.

{{< notice >}}
Choisir de bons noms prend du temps, mais permet d’en gagner plus encore.
Vous devez donc faire attention à vos noms et les changer dès que vous en trouvez de meilleurs
Quiconque lit votre code, y compris vous, vous en sera reconnaissant.
{{< /notice >}}

## Regles générales

Le nom de quelque choser sert à 3 choses :

1. La raison de son existance
2. Le role
3. L'utilisation

Ces regles doivent etre appliquée partout, tout le temps.

1. Prononçables 
2. Descriptif sans besoin d’ajouter un commentaire
3. Pas de jeux de mots
4. Pas de blague, ne pas faire le malin
5. Pas de préfixe d
6. Propice à une recherche
7. Distinction significative
8. Un mot par concept (add, insert, append)
9. Cohérent et respectant la norme

## Les classes

- Un nom ou un groupe nominal
- Un nom de méthode doit être un verbe ou des groupes verbaux
- Les accesseurs, les mutateurs et les prédicats doivent être préfixés par `get`, `set` et `is`

## Les fonctions

- Utiliser la forme verbe + nom
