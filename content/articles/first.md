---
title: "Mon premier blog Jamstack avec Hugo !"
date: 2020-06-12T19:16:33+02:00
lastmod: 2020-06-12T22:37:30+02:00
draft: false
tags: ["Hugo", "Jamstack", "test"]
categories: ["Hugo"]
toc: true
description: "Mon aventure avec Hugo et la Jamstack"
---

Bienvenue !
Oui, bienvenue sur ce blog, je vais essayer de vous partager 
au mieux la création d'un blog, orienté technique grace à la Jamstack.

**Cet article est construit au fur et à mesure que je découvre la solution.**
En gros, toi lecteur, tu es en avance sur moi. Et donc si tu lis ceci, c'est que j'ai réussi !

## C'est quoi la Jamstack ?

Et bien, j'en ai entendu un petit peu par ci par là, en lisant quelques blogs ou articles.
Donc ce mot m'est arrivé aux oreilles. J'ai donc fait ce que tout bon dev fait, j'ai cherché sur le net
(tu as vu, je n'ai pas cité de marque :joy:). Je suis donc tombé sur ce [site](https://jamstatic.fr/2019/02/07/c-est-quoi-la-jamstack/),
en français s'il vous plait ! Où ils expliquent tout plein de choses intéressentes !

**Y a plus qu'a tester !**

Et en gros tu ecrit ton article en MD (coool :joy:), c'est compilé par une CI et diffusé !
Pas de soucis de sécu, de deploiement, de dev ... Le pied !

## Le commencent

- J'ai créé un compte sur [netlify](https://www.netlify.com/), pour eux ? Tout simplement car ca avait l'air facile (et gratuit) !
- Une connexion avec github, le choix du dépot, merde, pas de dépot ...
- Création du dépot, création de la branche develop !
- Sélection du dépot
- [Installation de hugo](https://gohugo.io/getting-started/installing/), la doc est hyper bien faite !
- [Installation du theme](https://github.com/Track3/hermit), la doc est hyper bien faite ! Y a plein d'exemples d'articles !
- Je copie colle depuis l'exemple et je modifie la config
- Je crée ce fichier, je lance le serveur dev et **z'est parti !!!**

{{< figure src="https://media.giphy.com/media/4Nldony0MG8Ss/giphy.gif" alt="montagne russe" caption="Youhouuuu !!!" >}}

## Le déploiement

J'ai dit à netlify de construire le site que sur un push sur master, ça évite de build à chaque changement et economise des crédits.
En plus, le serveur de dev est très pratique !
Comme ça j'ai toujours une branche propre du site.

Je remarque qu'on peut faire du test A/B directement sur des branches cool !

Bon c'est partit pour un premier build. Donc un commit push et un merge sur master.
J'utilise [git flow](https://danielkummer.github.io/git-flow-cheatsheet/index.fr_FR.html) intégré dans IDEA.

Ha merde, je n'ai pas configuré netlify, on va aller lire la [doc](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/).
J'ajoute dans ***build command*** `hugo`, ça parait louche ... Et comme je suis un dingue, je push directe sur master !

Évidement, ça ne suffit pas. J'ai ajouté un [fichier de config](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/) pour netlify, pour l'aider à compiler.

Et ça marche !!!

{{< figure src="/images/1.png" alt="page sans css" caption="il manque un truc ..." >}}

Bon y a pas le thème, alors qu'il est disponible avec le serveur de dev ...
Y a des erreurs de cross-origin dans la console et comme la plupart des gens j'ai un (très) vague idée de ce que ça veut dire.
J'édite le ***base url*** dans la config, en définissant un nom "https://brunotech.netlify.app/", faut pas me juger, c'est un essai !

Et je commit !

{{< figure src="https://media.giphy.com/media/iJgoGwkqb1mmH1mES3/giphy.gif" alt="animal heureux" caption="il manque un truc ..." >}}

Yeah ! Je m'amuse à ajouter quelques images. Je mets des liens directs, mais il y a moyen de faire [mieux](https://docs.netlify.com/large-media/overview/#large-media-docs) mais flemme pour l'instant.

Je commence à corriger des fautes, j'ai écrit comme un sagouin !

J'en profite pour mettre à jour le [à propos]({{< ref "/me.md" >}}) et découvrir un peu plus Hugo.

- Les liens internes
- Les figures
- Le front matter
- Les sections
- Les tags et catégories
- Les commentaires
- Le support multilingue
- La recherche

Bon, je ne comprends pas tout, mais je ne cherche pas vraiment non plus à maitriser.
Mais je sens que c'est hyper puissant !

## Un peu de config chez Netlify !

Bien, j'ai fait le tour rapide des fonctionnalités ! Maintenant je vais tester des choses du côté de l'hebergement !

Pour commencer, Netlify mets 39 secondes pour faire une installation propre complete. Avec un temps de build dérisoire !

```
11:57:50 PM: Total in 123 ms
11:57:50 PM: ​
11:57:50 PM: (build.command completed in 210ms)
11:57:50 PM: ​
11:57:50 PM: ┌─────────────────────────────┐
11:57:50 PM: │   Netlify Build Complete    │
11:57:50 PM: └─────────────────────────────┘
11:57:50 PM: ​
11:57:50 PM: (Netlify Build completed in 316ms)
11:57:50 PM: Caching artifacts
...
11:57:55 PM: Build script success
11:57:55 PM: Starting to deploy site from 'public'
11:57:55 PM: Creating deploy tree 
11:57:55 PM: Creating deploy upload records
11:57:55 PM: 20 new files to upload
11:57:55 PM: 0 new functions to upload
11:57:55 PM: Starting post processing
11:57:57 PM: Post processing done
11:57:57 PM: Site is live
11:58:15 PM: Finished processing build request in 38.998450283s
```

Ensuite, Google donne une super note !

{{< figure src="/images/2.png" alt="capture du resultat de rapidité" caption="Super résultat !" >}}

Netlify propose une option ***Asset optimization***, mais ça ne m'a pas l'air utile, le CSS et le JS étant minifié.
Je teste la compression des images.

## Points positifs et négatifs

-

## Résumé

Résumons cette experience !