---
title: "Mon premier blog Jamstack"
date: 2020-06-12T19:16:33+02:00
draft: false
featuredImg: ""
tags: 
  - hugo
  - Jamstack
---

Bienvenue !
Oui, bienvenue sur ce blog, je vais essayer de vous partager 
au mieux la création d'un blog, orienté technque grace à la Jamstack.
Cet article est construit au fur et à mesure que je découvre la solution.
En gros, toi lecteur, tu es en avance sur moi. Et donc si tu lis ceci, c'est que j'ai réussi !

# C'est quoi la Jamstack ?

Et bien, j'en ai lu un peu par ci par la, je lis un quelques blogs et je fais de la veille.
Donc ce mot m'est arrivé aux oreilles. J'ai donc ce que tout bon dev fait, j'ai cherché sur le net
(tu as vu pas de marque placée :joy:). Je suis donc tombé sur ce site [link] https://jamstatic.fr/2019/02/07/c-est-quoi-la-jamstack/,
en francais s'il vous plait !

Et en gros tu ecrit ton article en MD (coool :joy:), c'est compilé par une CI et diffusé !
Pas de soucis de sécu, de deploiement, de dev ... Le pied !

# Le commencent

- J'ai créé un compte sur [netlify](https://www.netlify.com/), pour eux ? Tout simplement car ca avait l'air facile (et gratuit) !
- Une connexion avec github, le choix du répo, merde, pas de repo
- Création du répô, création du branche develop !
- Séléction du répo
- [Installation de hugo](https://gohugo.io/getting-started/installing/), la doc est hyper bien faite !
- [Installation du theme](https://github.com/Track3/hermit), la doc est hyper bien faite !
- Je copie colle depuis l'exemple, je modifie la config
- Je crée ce fichier, je lance le serveur dev et **z'est parti !!!**

# Le deploiement

J'ai dit à netlify de construire le site que sur un push sur master, ca evite de build à chaque changement.
Et comme ca j'ai toujours une branche propre du site.

Je remarque qu'on peut faire du test A/B directement sur des branches cool !

Bon c'est partit pour un premier build. Donc un commit push et un merge sur master.
J'utilise git flow 

Ha merde, j'ai pas configuré netlify, on va aller lire la [doc](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/).
J'ajoute dans build command `hugo`, ca parait louche ... Et comme je suis un dingue, je push directe sur master !

Bon, ca a pas marché. J'ai ajouté un [fichier de config](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/) pour netlify, pour l'aider à compiler.

Et ca marche !!! Enfin presque, il manque le css ...


Bon y a pas le theme, alors qu'il est dispo avec le serveur de dev ...
Y a des erreurs de cross-origin et comme la plupart des gens j'ai un (tres) vague idée de ce que ca veut dire.
J'edite la base url, en definissant un nom "https://brunotech.netlify.app/", faut pas me juger, c'est un essai !

Et je rebuild !