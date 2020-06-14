---
title: "Mon premier blog Jamstack avec Hugo !"
date: 2020-06-12
lastmod: 2020-06-13
draft: false
tags: 
- Hugo
- Jamstack
- test
keywords: 
- Hugo
- Jamstack
- test
toc: true
description: "Mon aventure avec Hugo et la Jamstack"
---

Bienvenue !
Oui, bienvenue sur ce blog, je vais essayer de vous partager 
au mieux la création d'un blog, orienté technique grâce à la Jamstack.

**Cet article est construit au fur et à mesure que je découvre la solution.**
En gros, toi lecteur, tu es en avance sur moi. Et donc si tu lis ceci, c'est que j'ai réussi !

## C'est quoi la Jamstack ?

Et bien, j'en ai entendu un petit peu par-ci par-là, en lisant quelques blogs ou articles.
Donc ce mot m'est arrivé aux oreilles. J'ai donc fait ce que tout bon dev fait, j'ai cherché sur le net
(tu as vu, je n'ai pas cité de marque :wink:). Je suis donc tombé sur ce [site](https://jamstatic.fr/2019/02/07/c-est-quoi-la-jamstack/),
en français s'il vous plait ! Où ils expliquent tout plein de choses intéressantes !

**Y a plus qu'à tester !**

Et en gros, tu écris ton article en MD (coool :smile:), c'est compilé par une CI et diffusé !
Pas de soucis de sécu, de deploiement, de dev ... Le pied !

## Le commencent

- J'ai créé un compte sur [Netlify](https://www.netlify.com/), pourquoi eux ? Tout simplement, car ça avait l'air facile (et gratuit) !
- Une connexion avec github, le choix du dépôt, merde, pas de dépôt ...
- Création du dépôt, création de la branche develop !
- Sélection du dépôt
- [Installation de Hugo](https://gohugo.io/getting-started/installing/), la doc est hyper bien faite !
- Sélection et [Installation du thème](https://github.com/Track3/hermit), la doc est hyper bien faite ! Il y a plein d'exemples d'articles !
- Je copie-colle depuis l'exemple et je modifie la config
- Je crée ce fichier, je lance le serveur de dev et **z'est parti !!!**

{{< figure src="https://media.giphy.com/media/4Nldony0MG8Ss/giphy.gif" alt="montagne russe" caption="Youhouuuu !!!" >}}

## Le déploiement

J'ai dit à Netlify de construire le site que sur un push sur master, ça évite de build à chaque changement et économise des crédits.
En plus, le serveur de dev est très pratique !
Comme ça, j'ai toujours une branche propre du site.

Je remarque qu'on peut faire du test A/B directement sur des branches grâce à Netlify, cool !

Bon, c'est parti pour un premier build. Donc un commit push et un merge sur master.
J'utilise [git flow](https://danielkummer.github.io/git-flow-cheatsheet/index.fr_FR.html) intégré dans IDEA.

Ha merde, je n'ai pas configuré Netlify, on va aller lire la [doc](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/).
J'ajoute dans ***build command*** `Hugo`, ça parait louche ... Et comme je suis un dingue, je push directe sur master !

Évidement, ça ne suffit pas. J'ai ajouté un [fichier de config](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/) pour Netlify, pour l'aider à compiler.

Et ça marche !!!

{{< figure src="/images/1.png" alt="page sans css" caption="il manque un truc ..." >}}

Bon y a pas le thème, alors qu'il est disponible avec le serveur de dev ...
Y a des erreurs de cross-origin dans la console et comme la plupart des gens j'ai une (très) vague idée de ce que ça veut dire.
J'édite le ***base url*** dans la config, en définissant un nom "https://brunotech.netlify.app/", faut pas me juger, c'est temporaire (tu sais ce que veux dire temporaire :wink:) !

Et je commit-push !

{{< figure src="https://media.giphy.com/media/iJgoGwkqb1mmH1mES3/giphy.gif" alt="animal heureux" caption="il manque un truc ..." >}}

Yeah ! Je m'amuse à ajouter quelques images. Je commence par des liens directs, puis des images locales meme s'il y a moyen de faire [mieux](https://docs.netlify.com/large-media/overview/#large-media-docs) mais flemme pour l'instant.

Je commence à corriger des fautes, j'ai écrit comme un sagouin !

J'en profite pour mettre à jour le [à propos]({{< ref "/about.md" >}}) et découvrir un peu plus Hugo.

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

Pareil, il y a beaucoup de thèmes, j'en ai testé quelques-uns Hermit, Fuji, hello-friend, Dimension, Coder, il y a vraiment beaucoup de variété.

## Un peu de config chez Netlify !

Bien, j'ai fait le tour rapide des fonctionnalités ! Maintenant, je vais tester des choses du côté de l'hébergement !

Pour commencer, Netlify met 39 secondes pour faire une installation propre complète. Avec un temps de build dérisoire !

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

{{< figure src="/images/2.png" alt="Capture du résultat de rapidité" caption="Super résultat !" class="big" >}}

La version mobile est vraiment bien !

Netlify propose une option ***Asset optimization***, mais ça ne m'a pas l'air utile, le CSS et le JS étant minifié.
Je teste la compression des images. Sans résultat ... on va désactiver dans le doute.
Et de toute façon il faudra que les images soient traitées autrement.

Je vois qu'il y a plein de plugins ! C'est top ! Mais j'ai l'impression qu'Hugo, fait déjà beaucoup de choses.

On peut également préciser un domaine perso, on peut l'acheter ou utiliser un domaine gratuit, mais flemme.

## Points positifs et négatifs

Bien, après une bonne nuit de sommeil, quelques points que j'ai aimés :

- Ce n’est pas compliqué et la doc est bien faite ! Les petites vidéos dans la documentation c'est sympa.
- Une volonté de bien faire, les thèmes ont tous des exemples et des configs par défaut.
- Rapide et simple, en 15 minutes on a déjà un résultat !
- Beaucoup de puissance cachée, traitement d'image, liens, paramétrages ...
- GIT !

Mais il y a quand même quelques points négatifs

- Quand il y a une erreur de syntaxe, le serveur de dev se coupe parfois.
- Manque de documentation pour la gestion des dossiers, où mettre les images par exemple.
- La modification du thème compliquée à première vue.
- Des fonctionnalités qui disparaissent ??? Les tags ne fonctionnent plus, ni la redirection vers d'autres articles.

Il va falloir passer du temps sur le [thème]({{< ref "/posts/theme.md" >}}) !

## Résumé

Résumons cette expérience !

Hugo, c'est vraiment agréable, alors ce n'est pas pour tous les projets, mais c'est parfait pour un blog.
Je pense que c'est suffisamment accessible pour un néophyte, il peut s'occuper uniquement du contenu une fois mis en place.
Quand on a l'habitude d'utiliser git et un serveur de dev, on est réellement très efficace.
Il fait largement ce que je lui demande et ça reste globalement simple à utiliser et configurer.

Netlify c'est un bonheur à utiliser, il y a de la documentation partout, c'est rapide efficace et gratuit.

Au final, je pense que la Jamstack et particulièrement l'utilisation d'Hugo est un véritable atout !
Cette technologie permet de se concentrer sur le contenu et c'est à mon avis toute la valeur d'un site.

Voilà, je ne sais pas si ce blog va perdurer, mais merci de m'avoir lu :heart:.
