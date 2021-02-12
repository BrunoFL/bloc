---
title: "La domotique avec Home Assistant, le commencement"
date: 2021-02-08T18:10:00+0200
lastmod: 2021-02-08
draft: false
tags:
- domotique
- home assistant

keywords:
- domotique
- home assistant
---

Salut ! Une nouvelle série d'articles sur la domotique !
J'ai récemment emménagé dans un nouvel appartement et je me suis dit que c'était le moment de commencer !

Je n'ai jamais testé aucun logiciel, centrale, objet ou même ampoule ! Je suis donc totalement incompétent sur le sujet ! (spoil : ça va bien se passer)

Mon objectif c'est de m'amuser :smile:, apprendre et découvrir des choses et gagner en confort.
Pour les économies, je pense actuellement que c'est anecdotique, mais on verra dans plusieurs mois (années).

Certains liens vers les produits que j'ai utilisés sont affiliés, vous ne payez pas plus et je touche une commission, c'est une façon de me soutenir gratuitement :smile:. Merci !

## Au programme

Différents sujets m'intéressent !

- Le chauffage, je suis dans un immeuble avec un chauffage collectif et un recalcule individuel. Je voudrais donc piloter les radiateurs.
- L'électricité, piloter des prises, mesurer la consommation ...
- Éclairage, que serait de la domotique sans une ampoule connectée !
- Et tout ce que je vais découvrir !

{{< figure src="https://media.giphy.com/media/5xtDarqCp0eomZaFJW8/giphy.gif" alt="maison" caption="C'est partit !!!" >}}

## Les objectifs

Mon objectif premier, c'est voir qu'est-ce qu'il est possible de faire.
J'ai certaines connaissances en informatique, en réseau, en électronique, mais je veux voir si tout le monde peut le faire ou non.
*Je veux que ça reste simple !*

Combien ça coute ! L'achat de la centrale, des objets, du fonctionnement. Mais aussi le temps d'installation de maintenance ...

Est-ce qu'il y a vraiment des économies à faire ?

Je veux également au maximum un fonctionnement *cloud less* c'est-à-dire avec serveur chez moi, les objets communiquant sans passer par des services tiers ...
Pour différentes raisons, l'indépendance, la résistance à la panne et garder mes données au chaud :smile:.

## Home Assistant

Plusieurs solutions existent sur le marché (je ne vais pas toutes les citer), des open sources, des payantes, avec une station, de grand constructeur, de startup ...

Un ami m'a conseillé [Home Assistant](https://www.home-assistant.io/), j'ai parcouru un petit peu la documentation, vu les exemples, les captures d'écrans.
Ça avait l'air cool donc je me suis lancé ! Voilà sans plus de raison.

{{< figure src="https://media.giphy.com/media/3ornjSL2sBcPflIDiU/giphy.gif" alt="haussement d'épaules" caption="il faut plus de raisons ?" >}}

Je ne pourrais évidement pas dire s'il manque des fonctionnalités, ou si cette solution est meilleure que les autres.
Juste si ça marche et si ça me convient. Je précise que la version actuelle est la 2021.

Des [démos](https://demo.home-assistant.io/#/lovelace/0) sont disponibles pour voir à quoi ça ressemble. Ça donne une bonne idée !

### L'installation

Pour commencer, j'ai acheté un Raspberry Pi 4 (4GB), la documentation indique que la version avec 2GB est suffisante, mais je voulais avoir plus de souplesse et potentiellement utiliser le pi pour autre chose un jour.
J'ai pris un pack avec un boitier une alimentation, une carte SD et le pi. Pour un peu plus de 100€ (il a baissé depuis :grimacing:)
[![LABISTS Raspberry Pi 4 Modèle B (4 B) 4Go Kit avec 64 Go](//ws-eu.amazon-adsystem.com/widgets/q?_encoding=UTF8&MarketPlace=FR&ASIN=B07YYXNMG7&ServiceVersion=20070822&ID=AsinImage&WS=1&Format=_SL250_&tag=brunoacademie-21)](https://www.amazon.fr/gp/product/B07YYXNMG7/ref=as_li_tl?ie=UTF8&camp=1642&creative=6746&creativeASIN=B07YYXNMG7&linkCode=as2&tag=brunoacademie-21&linkId=6a1fcb4d208ea52389f2dc126a464fd3)


J'ai ensuite suivi la [procédure d'installation](https://www.home-assistant.io/getting-started/), c'est assez facile et en 30 minutes c'est prêt !
Elle est vraiment pas-à-pas et facile à faire, en gros ça donne ça :
- Telecharger balenaEtcher
- Flasher l'image sur la carte SD
- Installer la carte dans le pi, le brancher en ethernet, l'alimenter et attendre (20 minutes)
- Se connecter [http://homeassistant.local:8123](http://homeassistant.local:8123)

{{< figure src="https://media.giphy.com/media/QMoXJjGPsmJ6Pdc596/giphy.gif" alt="joie" caption="joie intense !" >}}

Et on prêt à commencer !

## Conclusion

C'est ainsi que se finit ce premier article ! Dans le prochain, un tour des fonctionnalités, les éléments de base et la configuration.

Et les premières intégrations !

Merci :heart:, bisou.
