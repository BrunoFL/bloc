---
title: "Clean Code, coder prorement, le resumé"
date: 2020-06-20T17:18:00+0200
lastmod: 2020-06-120
draft: false
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
toc: true
---

Clean code de [Robert C. Martin](https://blog.cleancoder.com/), aussi appellé oncle Bob, est une reference pour un developpement de qualité.
J'ai toujours avec moi la version papier, ca veut pas dire que je fais que la qualité :wink:

Ce livre est une référence, il revient souvent et c'est personnellement un livre qui a eu beaucoup d'impact sur moi.
Je conseille donc evidement à tous ceux qui touchent à du code de le lire. Il s'applique à tous les langages et tous les developpements.

Un developpeur junior manque d'experience, l'experience s'acquiere lentemement, mais ce livre peut apporter 40 ans d'experiences et de bonnes pratiques.

Dans cette série d'articles je vais essayer d'en tirer le meilleur pour en faire un resumé avec des exemples, des citations et en tentant d'actualiser en y apporter mon avis.

Il y a un article pour chaque chapitre du livre :

1. Nommage
2. Nommage
3. Fonctions
4. Commentaires
5. Mise en forme
6. Objets et structures de données
7. Gestion des erreurs
8. Limites
9. Tests
10. Les classes
11. Emergences

Les articles apparaitrons au fur et à mesure :wink:

## Il y aura toujours du code !

On voit regulierement de nouvelles technoliges apparaitrent, assurant de ne plus avoir besoin d'ecrire du code :

- [Low-code](https://www.journaldunet.com/solutions/cloud-computing/1190722-comparatif-6-plateformes-cloud-de-developpement-low-code/) / No-code
- Programmation par bloc, comme [scratch](https://scratch.mit.edu/) 
- Intelligence artifiecelle qui [developpe](https://www.lemagit.fr/actualites/252484744/Les-IA-sinvitent-sur-lecran-du-developpeur)

Toutes ses technologies sont super cool !
Elles permettent de developper mieux, plus rapidement, plus facilement, pour plus de personnes et plus tot !

Mais elles ne vont pas remplacer le code. Déjà, il faut des gens pour developper ses outils. Ca peut paraitre bete à dire.
Mais ses outils ne sont faits ni facilement, ni sans code.

Ensuite et je vais directement citer le livre :

{{< notice >}}
Nous ne pourrons jamais nous débarrasser du code car il représente les détails des exigences.
À un certain niveau, ces détails ne peuvent pas être ignorés ou absents ; ils doivent être précisés.
Préciser des exigences à un niveau de détail qui permet à une machine de les exécuter s’appelle programmer.
Cette spécification est le code.
{{< /notice >}}

Autrement dit, pour que quelque chose soit compréhensible et executé par un ordinateur (au sens large) il doit etre décrit précisemnt, c'est donc du code.

Cela veut dire que meme la programmation par bloc, ou en glissé déposé, reste du code si elle fait exactement ce qu'on veut qu'elle fasse.
Oui, ton petit neveu de 8 ans qui fait du scratch est un développeur !

{{< figure src="https://media.giphy.com/media/ukMiDlCmdv2og/giphy.gif" alt="developpeur" caption="ton neveu qui galere avec son robot" >}}

## Le mauvais code et le bon code

On est tous capable de remarquer du mauvais code.
On trouve ça moche, y a souvent des bugs, on comprend rien, c'est pas maintenable, ...
On en a tous écrit. Par contre écrire du beau code est plus difficile. :

{{< notice >}}
Nous avons tous examiné le désordre que nous venions de créer et choisi de le laisser ainsi encore un peu.
Nous avons tous été soulagés de voir notre programme peu soigné fonctionner et décidé que c’était toujours mieux que rien. 
Nous avons tous pensé y revenir plus tard pour le nettoyer.
Bien entendu, à ce moment-là nous ne connaissions pas la loi de LeBlanc : **Plus tard signifie jamais**.
{{< /notice >}}

{{< notice >}}
Malheureusement, écrire du code ressemble à peindre un tableau.
La majorité d’entre nous sait reconnaître un tableau bien ou mal peint.
Cependant, être capable de faire cette différence ne signifie pas être capable de peindre.
De même, être capable de différencier le code propre du code sale ne signifie pas savoir écrire du code propre !
{{< /notice >}}