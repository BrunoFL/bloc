---
title: "Moment.js s'est fini !"
date: 2020-09-19T13:10:00+0200
lastmod: 2020-09-19
draft: false
tags: 
- actualité
- moment
- js
keywords: 
- date
- moment
- js
- web
toc: true
---

La librairie utilisée dans des millions de projets, téléchargée 12 millions de fois par semaine est finie ! :clap:

Oui ! Et ce n'est pas moi qui le dis, mais bien les développeurs de la librairie dans un [billet](https://momentjs.com/docs/#/-project-status/) apparu en septembre 2020.

Mettons les choses au clair tout de suite. Non, la librairie n'est pas morte. Oui, elle est toujours maintenue.
Par contre, il n'y aura plus de nouveauté. Le développement est fini.

Alors un petit retour s'impose sur cet outil, pourquoi c'est la fin et les solutions.

## Retour aux sources

Moment.js c'est un ensemble de fonctions pour analyser, valider, manipuler des dates et durées en JS.
Elle peut gérer des calculs, la gestion des fuseaux horaires, du formatage, de la localisation ...

Tous ceux qui l'ont utilisé savent que c'est facile et sympa.
Surtout ceux qui ont tenté d'utiliser l'objet Date natif de JS...
Toi-même tu sais si tu as lu cet [article]({{< ref "/posts/pourquoi-detester-javascript.md" >}}).

Bref, c'est un super outil qui facilite la vie ! Par exemple, mozzila dans sa [documentation](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Date/Date#Timestamp_string) déconseille fortement l'utilisation du parse de Date...
Car les résultats sont différents selon les navigateurs et inconsistants ...

{{< figure src="https://media.giphy.com/media/6jFz3h6iFOjwQ/giphy.gif" alt="non, mais allo" caption="je me sens sale" >}}

{{< notice >}}
Bon alors c'est quoi le problème ? Utilisons Moment.js !
{{< /notice >}}

## Les problèmes

En fait, il y en a plusieurs...

### L'âge

Premièrement la librairie date de 2011. Pour du web, c'est vieux !
Son but initial est de fournir un palliatif aux manques du JS de 2011 ! Problèmes qui sont aujourd'hui pour certains résolus.
Oui, comme pour jQuery :wink:.

Par exemple [Intl](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Intl), l'API d'Internationalisation n'existait pas.
Et ensuite, elle n'était pas suffisamment complète.

Aujourd'hui, il y a moins de problèmes, Moment.js n'est donc plus indispensable.

### La taille
 
Le problème le plus relevé c'est sa taille ! Entre 65 et 232 KB selon la version choisie ! C'est énorme !
Pour se donner une idée Vue c'est 20 KB, React 30.

{{< figure src="https://raw.githubusercontent.com/you-dont-need/You-Dont-Need-Momentjs/master/screenshot.png" alt="taille des librairies" caption="Moment vs les concurrents" >}}

Google alerte et commence à conseiller des alternatives {{< tweet 1304676118822174721 >}}

De plus, Moment.js n'est pas compatible, par construction, avec le ["tree-shaking"](https://webpack.js.org/guides/tree-shaking/), la technique d'optimisation des bundlers qui consiste à supprimer les fichiers inutiles.
Ce qui veut dire que tout est téléchargé puis analysé par le navigateur. Contrairement à [date-fns](https://date-fns.org/) par exemple. :thumbsup:


### Les performances
 
En plus, c'est relativement lent, en tout cas comparé à certains de ces concurrents. Ceci dit, cet argument est dépendant du contexte.
Il n'y a pas énormément de cas où il faut analyser et transformer des milliers de dates d'un coup.
Mais si le cas se présente, il faut y penser.

### La mutabilité

La norme aujourd'hui est de faire des composants immutables, pour différentes raisons.
L'idée est simple, l'objet manipulé ne peut pas changer de valeur ! Si on effectue un calcul, ce calcul retourne une nouvelle valeur sans modifier les autres.
Ce fonctionnement permet entre autres d'éviter les bugs.

```javascript
const debut = moment()
const fin   = debut.add(1, 'year')

console.log(debut) // 2020-09-19T13:00:00+02:00
console.log(fin)   // 2020-09-19T13:00:00+02:00
```

La variable `debut` a pris la valeur du résultat du calcul. Cela veut dire que si on voulait conserver la valeur de base, il faut la cloner avant.

En plus, le calcul retourne également la valeur. Si aucune valeur n'était retournée, au moins pas de doute c'est mutable.
Ici on ne sait pas trop. C'est assez particulier comme fonctionnement. :hushed:

Ce problème est à l'appréciation du développeur, certains aiment d'autres non. 

## On continue de l'utiliser ?

Et bien oui, dans certains il vaut mieux. Les développeurs ne conseillent pas aux nouveaux projets.
Mais apportent quelques exceptions :

1. Support du navigateur, si tu as besoin du support d'Internet Explorer 8 (:innocent:).
2. Dépendances, si ton composant de sélection de dates en a besoin.
3. Par habitude, si tu es un expert continue avec.

Sinon, utilise une autre librairie, certaines utilisent Intl ou/et sont compatibles avec le tree-shaking :
- [Luxon](https://moment.github.io/luxon/), le successeur spirituel
- [Day.js](https://day.js.org/), celui qui fait le minimum, mais le fait bien
- [date-fns](https://date-fns.org/), le jeune chalengeur plein de fougue
- [js-joda](https://js-joda.github.io/js-joda/), le cousin venu d'un autre pays
- [Spacetime](https://github.com/spencermountain/spacetime), le cousin expat

Et toutes les autres.

Sinon, il y a toujours l'option de faire soi-même avec [Intl.DateTimeFormat](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Intl/DateTimeFormat) et l'objet [Date](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Date) de JS.
Dans les cas simples, c'est suffisant.

Et peut-être qu'un jour prochain, [Temporal](https://github.com/tc39/proposal-temporal) sera disponible avec toutes ces [nouveautés](https://tc39.es/proposal-temporal/docs/index.html).

## Merci
Moment.js c'est terminé, mais on peut toujours l'utiliser. Même si c'est déconseillé pour de nouveaux projets.
Le web évolue, les besoins changent et les solutions avec.

Merci Moment.js d'avoir amélioré le web. Et aussi de savoir quand t'arrêter tout en aidant à faire la transition.
Et merci à tous ceux qui ont participé à ce super projet !

{{< figure src="https://media.giphy.com/media/uLda64US3sb16/giphy.gif" alt="au revoir blanche neige" caption="au revoir" >}}

Tu l'as déjà utilisé ? Tu utilises une autre libraire, j'aimerais savoir pourquoi. :blush:

Si tu as des remarques sur cet article, n’hésite pas !

Merci :heart:.
