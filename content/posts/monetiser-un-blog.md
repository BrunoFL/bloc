---
title: "Monetiser un blog"
date: 2020-06-17T21:01:00+0200
lastmod: 2020-06-18
draft: false
tags: 
- Hugo
- Jamstack
- theme
- blog
keywords: 
- Hugo
- Jamstack
- test
- theme
- bmc
- argent
- euros
toc: true
---

S'occuper d'un blog, cela prend du temps. 
Pour certains articles, les recherches, les tests, les développements ou le support, le nombre d'heures peut vite exploser.
Pour avoir un ordre d'idée, le premier jet de cet article m'a pris 4-5h.

En ajoutant les autres couts, comme les commentaires, l'hébergement, la rédaction tenir un blog coute de l'argent.
Alors évidemment je ne suis pas concerné par les couts d'hébergement, de rédaction ou de salaires.

Je voulais donc un moyen, non pas de gagner de l'argent, mais au moins rembourser les frais.
Pour mon cas et au moment où j'écris cet article, le module des [commentaires]({{< ref "/posts/ajout-des-commentaires.md" >}}) est mon unique dépense de 5$ par mois.

Mais le principal argument pour moi, c'est que je veux tester, voir comment ça fonctionne. 

Et donc **comment on fait ???**, la première idée qui vient chez tout le monde c'est la publicité !

## Pourquoi pas de publicités ?

Déjà, la publicité nécessite un fort volume de visite ou/et un grand nombre de pubs.
Je ne cherche pas un grand nombre de visites, sinon je n'aurais pas fait un blog sur le développement. :grin:

Et globalement, je suis mal à l'aise à l'idée de mettre de la publicité (déjà que je ne suis pas très à l'aise).
Je ne saurais pas où la mettre, combien, quelle taille... 

{{< figure src="https://media.giphy.com/media/xT1XGRNZKFIzKqWnsc/giphy.gif" alt="gif trop de pubs" caption="trop de pubs tuent la pub" >}}

Bref, la publicité c'est très bien dans bon nombre de cas, mais pas pour moi.

## Mes attentes

Pour résumé, je voudrais un système de don et non pas d'achats. Limitant au maximum la collecte des données personnelles et :

1. Integrable et léger, il ne faut pas qu'un module qui va être utilisé rarement ralentisse le blog
2. Facile à utiliser et à mettre en place
3. Non intrusif à l'usage

Si en plus, je peux le customiser, c'est du bonus ! :blush:

## Choix de la solution

C'est parti pour une petite recherche de solutions.
J'ai déjà entendu parler et vu sur différents sites [buy me a coffee](https://www.buymeacoffee.com/).
Mais il existe aussi [ko-fi](https://ko-fi.com/) son concurrent direct, on sent bien la copie.
 
Mais il existe aussi :

- [Donorbox](https://donorbox.org/fr), mise trop sur la collecte de fonds.
- [Patreon](https://www.patreon.com/) et [utip](https://www.utip.io/), pas trop l'esprit, mais pourquoi pas dans le futur ?
- [Paypal](https://www.paypal.com/)

Il me reste donc Paypal ou Buy Me a Coffee. J'ai choisi le deuxième pour plusieurs raisons :

- Plus fun dans l'esprit
- On peut modifier le style

Ce sont 2 arguments assez faibles, mais il fallait faire un choix :blush:.
Mais ce n'est évidemment pas gratuit la plateforme prend une commission de 5%.

## Configuration de Buy Me a Coffee

Comme d'habitue ce n'est pas compliqué :

- Création du compte
- Lien avec le compte Paypal

L'outil permet de débloquer des contreparties, mais ce n'est pas ce que je cherche.
Et je ne vois pas ce que je pourrais offrir. :confused:

- Ensuite il faut remplir sa page personnelle, la bio, le lien, une description et quelques messages

{{< figure src="/images/bmc-emoji.png" alt="capture buy me a coffee emoji" caption="on peut choisir ce qui est offert" >}}

On peut également choisir le montant du don, entre 1 et 5 euros.
J'ai choisi 3€, car je trouve que 4€ et 5€ c'est trop et qu'ils recommandent 3€ minimum pour limiter l'effet des frais.

## Installation sur le blog

Ensuite, il faut installer le module sur le blog.
Il y a 2 possibilités un widget ou un bouton.

Le widget est assez sympa, il se place dans le coin inférieur gauche ou droit de la page et affiche un message lorsque le visiteur arrive en bas.

{{< figure src="/images/bmc1.png" alt="widget buy me a coffee" caption="super cool non ?" >}}

Mais 2 problèmes apparaissent :

1. Le bouton s'adapte assez mal en mode mobile, il gêne le menu du bas et la navigation.
2. Trop intrusif, le message s'affiche un peu trop aléatoirement à mon gout.

Sinon un simple bouton est disponible, l'outil fournit un générateur pour créer un bouton de son choix.
Puis il génère un bout de code à insérer où on le souhaite.

```html
<style>.bmc-button img{height: 34px !important;width: 35px !important;margin-bottom: 1px !important;box-shadow: none !important;border: none !important;vertical-align: middle !important;}.bmc-button{padding: 7px 15px 7px 10px !important;line-height: 35px !important;height:51px !important;text-decoration: none !important;display:inline-flex !important;color:#ffffff !important;background-color:#5F7FFF !important;border-radius: 5px !important;border: 1px solid transparent !important;padding: 7px 15px 7px 10px !important;font-size: 22px !important;letter-spacing: 0.6px !important;box-shadow: 0px 1px 2px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;margin: 0 auto !important;font-family:'Cookie', cursive !important;-webkit-box-sizing: border-box !important;box-sizing: border-box !important;}.bmc-button:hover, .bmc-button:active, .bmc-button:focus {-webkit-box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;text-decoration: none !important;box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;opacity: 0.85 !important;color:#ffffff !important;}</style>
<link href="https://fonts.googleapis.com/css?family=Cookie" rel="stylesheet">
    <a class="bmc-button" target="_blank" href="https://www.buymeacoffee.com/brunofl">
    <img src="https://cdn.buymeacoffee.com/buttons/bmc-new-btn-logo.svg" alt="Buy me a beer">
    <span style="margin-left:5px;font-size:28px !important;">Buy me a beer</span>
</a>
```

En l'état plusieurs choses me gênent.
Mettre du css directement dans une balise, je trouve que ce n'est pas une bonne pratique.
Importer une police pour uniquement 3 mots c'est un peu cher payé.

- Je commence donc par créer un fichier `/static/css/bmc.css` et je copie-colle le css.
- Ensuite, je supprime tous les `!important`, j'en profite pour déplacer le style dans le `span` dans ce fichier.
- Également je supprime la font qui n'a pas un grand intérêt.
- Je modifie le texte et les couleurs pour respecter le [thème]({{< ref "/posts/modification-du-theme.md" >}})
- Enfin j'ajoute dans la config la prise en charge de fichier de style. `customCSS = ["css/bmc.css"]`

Je pourrais ressortir différentes choses dans des paramètres, mais flemme. :blush:

Ensuite je crée un fichier `/layouts/partials/bmc.html` pour mettre le reste du bouton, j'ajoute async et lazy dans le doute.

```html
<a class="bmc-button" target="_blank" href="https://www.buymeacoffee.com/brunofl">
    <img decoding="async" loading="lazy" src="https://cdn.buymeacoffee.com/buttons/bmc-new-btn-logo.svg" alt="Offre moi une bière">
    <span>Offre moi une bière</span>
</a>
```
 
Et pour finir, j'importe le layout dans le fichier `/layouts/posts/single.html`, celui qui gère l'affichage d'un article.
Je le place entre la barre verticale et le footer avec les métadonnées.

```html
{{ partial "bmc.html" . }}
 ```

Et voilà le résultat final !

{{< figure src="/images/bmc2.png" alt="button buy me a coffee" caption="ça rend bien non ?" >}}

Facile :+1:.

## Conclusion

Au final, je suis assez satisfait du résultat, je ne force personne, je ne pénalise personne et surtout ça rentre discrètement dans le thème.

Ce n'est pas facile de parler d'argent, mais je pense que le résultat est honnête.
J'ai assez peu d'espoir d'avoir un don, mais avec le temps et la multiplication des articles on ne sait jamais :wink:.

Et de toute façon, c'est suffisamment intéressant à faire pour ne pas regretter de l'avoir fait :blush:.

J'ai l'impression de répéter toujours la même chose, mais c'est hyper facile à faire !
Un service à configurer, quelques fichiers à créer ou modifier et c'est réglé !

Si cet article vous a aidé ou intéressé vous pouvez laisser votre avis ou faire plus maintenant :wink:.

Merci de m'avoir lu :heart:. 

