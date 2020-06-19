---
title: "Bootstrap abandonne jQuery, c'est important !"
date: 2020-06-18T22:10:00+0200
lastmod: 2020-06-19
draft: false
tags: 
- actualité
- bootstrap
- js
- jquery
keywords: 
- Hugo
- Jamstack
- test
- theme
- blog
- bootstrap
- web
toc: true
---

[Bootstrap](https://getbootstrap.com/), le framework CSS le plus connu et utilisé à fait une grande annonce !
Dans sa [dernière](https://blog.getbootstrap.com/2020/06/16/bootstrap-5-alpha/) news, Bootstrap a annoncé :

1. La fin du support d'Internet Explorer 10 et 11
2. Le passage de la documentation sous Hugo :blush:
3. La fin de l'utilisation de jQuery ! :scream:

Et je vais vous expliquer pourquoi c'est important !

## La fin du support d'Internet Explorer 10 et 11

Déjà, tous ceux qui font du développement et encore plus du développement web ont un petit rictus dès que le nom **Internet Explorer** est prononcé.
Un mélange entre crainte, rire jaune, peur, détresse, demande de pitié, vous voyez l'idée. :wink:

{{< figure src="https://media.giphy.com/media/14ut8PhnIwzros/giphy.gif" alt="peur" caption="quand le client demande le support d'IE" >}}

Et malheureusement, il est toujours utilisé malgré l'[abandon](https://www.lefigaro.fr/secteur/high-tech/2019/02/13/32001-20190213ARTFIG00173-microsoft-exhorte-a-ne-plus-utiliser-son-navigateur-internet-explorer.php) de Microsoft.
Bon à [1.41%](https://gs.statcounter.com/browser-market-share), c'est peu, mais **pourquoi** ?

Et bien pour plusieurs raisons :

- Malheureusement, les gens ne font pas les mises à jour, les particuliers, les institutions, les entreprises :scream:. 
- Installé et utilisé par défaut sur de vieux parcs.

Donc les développeurs ont créé plein d'outils pour prendre en charge ces navigateurs.
Ils assurent le maintien de ce que je vais appeler des rustines, je pense, à [Babel](https://babeljs.io/) et aux hacks CSS.
Et ils en créent de nouvelles à chaque nouveauté.

Toutes ces rustines alourdissent les sites web de tout le monde.
Ce code utile pour 1.41% des visites est analysé et exécuté par tout le monde.

J'espère donc que ces développeurs vont pouvoir se concentrer sur d'autres choses :smile:.
En tout cas, c'est ce qu'a annoncé Bootstrap ! 

## Le passage de la documentation sous Hugo

Court paragraphe, mais qui me fait très plaisir :smile:.

La documentation, généré par [jekyll](https://jekyllrb.com/) est maintenant effectué par [Hugo](https://gohugo.io/) !
Le même générateur que ce blog ! :blush:

Et d'après leurs retours la totalité de la documentation est compilée en **1.6 seconde** ! On parle de centaines de pages !

{{< figure src="https://media.giphy.com/media/gQ8vH7xIzYCR2/giphy.gif" alt="rapidté sonic" caption="Hugo qui compile la doc" >}}

Le serveur de dev met quelques millisecondes pour se mettre à jour contre 8-12 secondes pour Jekyll.
C'est juste dingue ! Ce qui me conforte dans le choix d'Hugo ! :blush:

À noter que le dev principal d'Hugo a aidé à la transition et ça, c'est gentil !

## La fin de l'utilisation de jQuery
L'information que je trouve la plus importante c'est l'abandon de [jQuery](https://jquery.com/) !

Pour ceux qui ne connaissent pas, c'est une librairie JavaScript créé **2006** (**!!!**) permettant d'écrire du code plus facilement.
Elle facilite la manipulation du DOM, des évènements, les requêtes ! À une époque où il n'y avait aucun standard !
Un petit [lien](https://www.mathieurobin.com/2014/09/il-est-temps-davoir-deja-quitte-jquery/) pour un résumé et un ressenti de l'époque dorée de jQuery.

Bref, quasiment tous les dev web ont utilisé jQuery. Et tout le monde à exécuter du code jQuery.
Certaines offres d'emploi mentionnent directement jQuery et non pas JavaScript :joy:. On parlait même de langage jQuery !

Il faut lui reconnaitre qu'il a développé, démocratisé et facilité le développement JavaScript.
Et l’on ne peut que remercier l'équipe derrière. Je vous invite à lire la partie dans la news de base qui explique mieux que moi l'impact de jQuery.

**Alors, pourquoi le supprimer ?**

Pour commencer, jQuery est très complet ! Trop complet ! C'est vite devenu une usine à gaz à tout faire.
Autrement dit, si vous vouliez une fonctionnalité précise toute la librairie est téléchargée et analysée par le navigateur ...

*Ouais mais y a une version slim*. Certes, ça réduit l'impact, mais le résultat et le problème est le même.

Le principal problème, c'est que **jQuery est devenu inutile !**. Surement grâce à sa démocratisation.
L'API JS s'est simplifié, des nouveautés sont apparues, des standards ont été créés ... 

Ce [site](http://youmightnotneedjquery.com/) expose des fonctions de jQuery transcrit en JavaScript de base.
Et ce n'est pas plus compliqué. :wink:

De plus, les frameworks JS sont apparus et ce sont démocratisés, rendant complètement inutile jQuery.
La manipulation du DOM étant effectué par ceux-ci. Les requêtes par des objets natifs plus récents comme [fetch](https://developer.mozilla.org/fr/docs/Web/API/Fetch_API/Using_Fetch).
Ou des librairies plus efficaces ([axios](https://github.com/axios/axios)).

Bref, merci jQuery pour tout ce que tu as fait et apporté !

{{< figure src="https://media.giphy.com/media/yoJC2El7xJkYCadlWE/giphy.gif" alt="merci" caption="à jamais dans notre coeur" >}}

Mais il est maintenant temps de laisser ta place. :kissing:

## Conclusion

Je ne sais pas quelle décision a impliqué l'autre, la fin du support d'IE 10 et 11 et l'abandon de jQuery.
Mais il est évident que les deux sont liés, pour à mon avis le meilleur.

J'espère que ces choix vont inciter les gens et les entreprises à abandonner l'utilisation et le support d'Internet Explorer 10 et 11.
Pour la bonne santé du web, la sécurité des utilisateurs et la rapidité du web. (*Mais aussi la santé des développeurs !* :blush:)

Si en plus cela permet à ces brillants développeurs de se concentrer sur des problématiques actuelles et bien j'ai hâte de voir !

Je vous invite à aller voir la [news](https://blog.getbootstrap.com/2020/06/16/bootstrap-5-alpha/) pour toutes les informations :wink:.

Si vous voulez donner votre avis ou raconter vos expériences les commentaires sont ouverts, j'ai hâte de vous lire !

Merci :heart:, bisou.
