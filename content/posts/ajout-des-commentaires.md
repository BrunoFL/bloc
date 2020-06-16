---
title: "Ajouter des commentaires à un blog Hugo grâce à Commento"
date: 2020-06-15T18:57:00+0200
lastmod: 2020-06-16
draft: false
tags: 
- Hugo
- Jamstack
- commentaire
- theme
- commento
keywords: 
- Hugo
- Jamstack
- test
- theme
- commentaire
- commento
- disqus
toc: true
---

Un blog sans commentaires c'est un peu tristounet. Ils apportent une vraie valeur ajoutée à un blog et de possibles discussions.
Ou des [guerres de religion](https://www.jesuisundev.com/la-religion-chez-les-developpeureuses-informatiques/), bref des larmes, du sang et de la joie ! :wink:

## Choix de la solution

Avec mon thème ([Hermit](https://github.com/Track3/hermit)), [Disqus](https://disqus.com/) est proposé par défaut, il suffit de mettre l'identifiant dans la config et ça marche !
Le souci c'est que disqus n'a pas très bonne réputation, notamment sur le sujet de la vie privée.
J'ai donc sorti ma plus belle recherche `disqus vs ` et je suis tombé sur plusieurs solutions :

- [Disqus](https://disqus.com/), la référence, je suppose
- [Discourse](https://www.discourse.org/), le challenger
- [Commento](https://commento.io/), celui qui monte

{{< figure src="https://media.giphy.com/media/THsgSe9BVrQh7ENthU/giphy.gif" alt="combat 3 personnes" caption="Disqus vs Discourse vs Commento" >}}

Mon choix se porte donc entre discourse et Commento. Sauf que je n'ai rien compris à la tarification de discourse.
Donc allons plutôt sur Commento :+1:. Le prix minimum est de 5$ par mois c'est cher pour l'utilisation que je vais en faire, mais tant pis !
Si besoin je l'hébergerais moi-même. Pour l'instant, restons simples.

En plus, c'est léger, facile à utiliser, respecte la vie privée et dispose d'un système anti spam ([Akismet](https://akismet.com/)).
Parfait ! :blush:

## Installation de Commento

Il n'y a rien à installer ! Enfin plus exactement, j'utilise la version cloud donc je n'ai rien à installer.

En revanche, il y quelques petites choses à faire :

- Création du compte
- Création du domaine avec une url et un nom
- On met la carte bleue, 5$ par mois
- On commence par la configuration générale, c'est réduit et c'est très bien comme ça.

{{< figure src="/images/config-commento.png" alt="configuration générale de Commento" caption="configuration générale" >}}

J'autorise les commentaires anonymes, devoir se logger pour écrire un "*merci bisou*", c'est non, trop contraignant !
Je pourrais toujours changer à l'avenir si besoin.

- Et enfin la configuration de la modération

{{< figure src="/images/config-commento2.png" alt="configuration de la modération de Commento" caption="configuration de la modération" >}}

Voilà, en 3 minutes c'est fait et ça me convient parfaitement. Et c'est tout pour Commento. :blush:

## Installation des commentaires

Il reste maintenant l'installation sur le blog. Commento fournit 2 balises à insérer dans une page pour afficher les commentaires, simplissime et classique.

```html
<script defer src="https://cdn.commento.io/js/commento.js"></script>
<div id="commento"></div>
```

Je copie-colle le fichier `layouts/partials/comments.html` du thème dans `/layouts/partials/comments.html`.
Et je remplace par les 2 balises, facile. :+1:

**Y a plus qu'à tester !**

{{< figure src="/images/commento-error.png" alt="erreur de Commento" caption="Ha !" >}}

On ne dirait pas, mais c'est bon signe. Il est allé chercher le script, mais comme je suis sur le serveur de dev l'adresse ne correspond pas.
Il faut tester en prod maintenant !

{{< figure src="/images/commento.png" alt="commentaires" caption="il semblerait que ça fonctionne" >}}

Super ! Comme on peut le voir, les commentaires sont disponibles tout en bas de la page juste après liens vers les autres articles.

Une [documentation](https://docs.commento.io/) est fournie pour paramétrer notamment la partie client avec le style, le chargement ...
Elle est très bien faite et assez courte.

On peut également afficher le [nombre de commentaires](https://docs.commento.io/configuration/frontend/count.html) d'un article depuis une autre page.
Ça peut être intéressant pour la page avec la liste des articles, mais plus tard.

## Conclusion

Et bien comme d'habitude c'est facile à faire ! C'est quand même assez génial à quel point c'est simple.

Commento à l'air vraiment bien, dans les menus on a le sentiment que c'est bien pensé, avec une bonne philosophie.

D'après l'audit de performance de Google, j'ai toujours 99/100 sur mobile et 100/100 sur ordinateur. Parfait ! :blush:

J'ai hâte d'avoir vos retours et vos conseils !
N'hésitez pas à commenter que ce soit sur le ton des articles, le style du blog, le contenu, des idées tout !
Je suis vraiment preneur.

Merci de m'avoir lu :heart:. 