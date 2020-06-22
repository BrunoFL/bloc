---
title: "Clean Code, coder proprement, le résumé"
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

Clean code de [Robert C. Martin](https://blog.cleancoder.com/), aussi appelé oncle Bob, est une référence pour un développement de qualité.
J'ai toujours avec moi la version papier, ça ne veut pas dire que je fais que la qualité :wink:.

Ce livre est une référence, il revient souvent et c'est personnellement un livre qui a eu beaucoup d'impact sur moi.
Je conseille donc évidement à tous ceux qui touchent à du code de le lire. Il s'applique à tous les langages et tous les développements.

Un développeur junior manque d'expérience, l'expérience s'acquiert lentement, mais ce livre peut apporter 40 ans d'expériences et de bonnes pratiques.
De quoi économiser du temps !

Dans cette série d'articles je vais essayer d'en tirer le meilleur pour en faire un résumé avec des exemples, des citations et en tentant d'actualiser en y apporter mon avis.
Je fais ce travail pour vous mais aussi surtout pour moi, je vous en fais donc partager :wink:.

Il y a un article pour chaque chapitre du livre :

1. [Nommage]({{< ref "/posts/clean-code/nommage.md" >}})
2. Fonctions
3. Commentaires
4. Mise en forme
5. Objets et structures de données
6. Gestion des erreurs
7. Limites
8. Tests
9. Les classes
10. Emergences

Les articles apparaitrons au fur et à mesure :wink:

## Il y aura toujours du code !

On voit régulièrement de nouvelles technologies apparaitre, assurant de ne plus avoir besoin d'écrire du code :

- [Low-code](https://www.journaldunet.com/solutions/cloud-computing/1190722-comparatif-6-plateformes-cloud-de-developpement-low-code/) / No-code
- Programmation par bloc, comme [scratch](https://scratch.mit.edu/) 
- Intelligence artificielle qui [développe](https://www.lemagit.fr/actualites/252484744/Les-IA-sinvitent-sur-lecran-du-developpeur)

Toutes ses technologies sont super cool !
Elles permettent de développer mieux, plus rapidement, plus facilement, pour plus de personnes et plus tôt !

Mais elles ne vont pas remplacer le code. Déjà, il faut des gens pour développer ses outils. Ça peut paraitre bête à dire.
Mais ses outils ne sont faits ni facilement, ni sans code.

{{< notice >}}
Nous ne pourrons jamais nous débarrasser du code, car il représente les détails des exigences.
À un certain niveau, ces détails ne peuvent pas être ignorés ou absents ; ils doivent être précisés.
Préciser des exigences à un niveau de détail qui permet à une machine de les exécuter s’appelle programmer.
Cette spécification est le code.
{{< /notice >}}

Autrement dit, pour que quelque chose soit compréhensible et exécuté par un ordinateur (au sens large) il doit être décrit précisément, c'est donc du code.

Cela veut dire que même la programmation par bloc, ou autres, reste du code si elle fait exactement ce qu'on veut qu'elle fasse.
Oui, ton petit neveu de 8 ans qui fait du scratch est un développeur !

{{< figure src="https://media.giphy.com/media/ukMiDlCmdv2og/giphy.gif" alt="développeur" caption="ton neveu qui galère avec son robot" >}}

## Le mauvais code et le bon code

On est tous capables de remarquer du mauvais code.
On trouve ça moche, y a souvent des bugs, on ne comprend rien, ce n’est pas maintenable ...
On en a tous écrit.

{{< notice >}}
Nous avons tous examiné le désordre que nous venions de créer et choisi de le laisser ainsi encore un peu.
Nous avons tous été soulagés de voir notre programme peu soigné fonctionner et décider que c’était toujours mieux que rien. 
Nous avons tous pensé y revenir plus tard pour le nettoyer.
Bien entendu, à ce moment-là nous ne connaissions pas la loi de LeBlanc : **Plus tard signifie jamais**.
{{< /notice >}}

Par contre, écrire du beau code est plus difficile.

{{< notice >}}
Malheureusement, écrire du code ressemble à peindre un tableau.
La majorité d’entre nous sait reconnaitre un tableau bien ou mal peint.
Cependant, être capable de faire cette différence ne signifie pas être capable de peindre.
De même, être capable de différencier le code propre du code sale ne signifie pas savoir écrire du code propre !
{{< /notice >}}

## La règle du boy-scout
Du code doit rester propre, il se dégrade naturellement avec le temps. 

{{< notice >}}
Les boy-scouts ont une règle simple que nous pouvons appliquer à notre métier :

**Laissez le campement plus propre que vous ne l’avez trouvé en arrivant.**
{{< /notice >}}

Cela peut se faire en rennomant une variable que l'on trouve peu clair, découper une fonction, supprimer une redondance, supprimer du code inutile, des commentaires, ...

## Apprendre à faire du code propre

Donc en gros, il y aura toujours du code, peu importe sa forme. Globalement tous les principes qui vont être énoncés s'appliqueront toujours.

Et écrire du code propre demande un apprentissage, de l'expérience, un travail constant et aussi des échecs. **Ce n'est pas facile !**

{{< notice >}}
Ce livre ne promet pas de faire de vous un bon programmeur ou de vous donner cette "sensibilité au code".
Il ne peut que vous montrer les méthodes des bons programmeurs, ainsi que les astuces, les techniques et les outils qu’ils utilisent.
{{< /notice >}}

J'espère que cette série d'articles vous aidera n'hésitez pas à donner votre avis :wink:

Bisou :heart:.