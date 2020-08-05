---
title: "Design Mode, modifier facilement le contenu d'un site web"
date: 2020-08-05T21:10:00+0200
lastmod: 2020-08-05
draft: false
tags: 
- js
- hack
- dev
keywords: 
- hack
- web
- js
toc: true
---

Salut ! Un petit article pour vous présenter un petit quelque chose hyper sympa !
Comment en une commande pouvoir modifier tous les textes d'un site web !

*Y a juste à lancer l'inspecteur, trouver le bon noeud est modifier le contenu*

Oui c'est vrai que ça fonctionne, mais ça peut être long et donc chiant ! **J'ai mieux !**

## Design mode

L'astuce c'est d'utiliser le [Design Mode](https://developer.mozilla.org/fr/docs/Web/API/Document/designMode).
Pour cela c'est hyper simple :

- Ouvrir l'inspecteur avec `F12`
- Dans la console écrire : `document.designMode = 'on'`

Voilà c'est tout ! Maintenant vous pouvez éditer tous les champs textes !

{{< figure src="/images/flow/designMode.gif" alt="design mode modification" caption="jamais de paix" >}}


Attention, pour les textes qui sont des liens (un tweet, *par exemple*), ça ne fonctionne pas ouf, on est redirigé.
(Mais ça fonctionne bien sur la page du tweet).

Je viens de découvrir ça, mais c'est hyper [vieux](https://caniuse.com/#search=designmode) et compatible sur *tous* les navigateurs, oui même Internet Explorer ! :open_mouth:

## Disclaimer

Si cet outil est super pratique pour les développeurs, notamment dans les phases de tests, d'ajustements...

Il est aussi hyper sympa pour faire de la merde et répandre de la merde !
Une modification, une capture et voilà, on fait dire ce qu'on veut à qui on veut ! :fearful:
Alors quand c'est une petite blague ça va, mais quand c'est des fausses infos relayées en masse ça craint.

Raison de plus pour se méfier ! :wink:

## Conclusion

Une petite astuce pratique, mais qui peut poser beaucoup de tord !

J'espère que cet article pourra vous aider si vous en avez le besoin.
Et sinon vous ouvrir les yeux, si ce n'était pas déjà fait, sur le niveau de compétence et de complexité qu'il faut pour créer et diffuser de la merde.

Merci :heart:, bisou.