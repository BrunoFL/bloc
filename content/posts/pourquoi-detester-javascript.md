---
title: "Pourquoi JavaScript déclenche autant de haine ?"
date: 2020-06-28T00:19:00+0200
lastmod: 2020-06-28
draft: false
tags: 
- dev
- JavaScript
- Java
keywords: 
- Java
- JavaScript
- dev
- haine
- detester
toc: true
---

Dans un [dernier]({{< ref "/posts/news/bootstrap-abandonne-jqeury.md" >}}) article sur Bootstrap et jQuery, il y a eu un commentaire :

{{< figure src="/images/js/bullshit-js.png" alt="commentaire jquery" caption="un souci avec JavaScript ?" >}}

JavaScript est détesté, c'est un fait, c'est comme ça. Et pour plein de raisons, souvent légitimes.
Dans cet article, je vais essayer d'expliquer pourquoi il y a autant de désamour pour ce langage.
Avec des exemples qui me sont arrivés et quelques idées :wink:.

Je chercherai peut-être un jour dans un autre article pourquoi il est tant aimé ?

## Le nom déjà

Bon, ça commence mal, **JavaScript**, **Java + Script**

- La version script de Java ? **non**
- Du script codé en Java alors ? **non !**
- Un langage typé objet au moins ? **non**
- Il récupère juste le nom pour avoir un nom avec une bonne réputation ? **ouais en gros** (super article sur l'[histoire](https://delicious-insights.com/fr/articles/javascript-n-a-rien-a-voir-avec-java/) de JS :wink:)

Donc en gros, pour la plupart des développeurs Java, JS c'est l'enfant attardé qui a piqué l'héritage.
On commence mal.

## Utilisation, le nombre fait la force

Bon ensuite, si on regarde l'[utilisation](https://insights.stackoverflow.com/survey/2020#technology) d'après stackoverflow, JS est utilisé, en gros, par tout le monde.
Si on l'utile c'est qu'on l'aime ?

{{< figure src="https://media.giphy.com/media/J0WtGU7W9knOo/giphy.gif" alt="gif haha non" caption="Haha, non !" >}}

Donc forcément si plein de gens l'utilisent; plein de gens le détestent. Bah ouais.

En plus, c'est le seul langage disponible sur une page web. Donc on oblige des gens à l'utiliser.
En général, quand on oblige un truc ça passe mal. :wink:

{{< notice >}}
Ouais, mais avec Kotlin, tu peux faire du transcompilage vers JavaScript !
{{< /notice >}}

Alors, tu as tout à fait raison mise en forme me servant à effectuer un pseudo dialogue !
Mais je ne suis pas sûr que ce soit beaucoup utilisé. 
(Si tu l'utilises, j'ai hâte d'avoir ton avis !)

Et j'ai personnellement du mal avec le [transcompilage](https://fr.wikipedia.org/wiki/Compilateur_source_%C3%A0_source) et les surcouches.
Tu ajoutes un niveau supplémentaire d'apprentissage, de bugs, de dette technique ...

## Le typage et ces bizarreries

C'est ici qu'on rigole (ou pleure).
JS fait des trucs, les débutants ne comprennent pas pourquoi.
Et même après, ce n’est pas intuitif.

On commence doucement :

```JavaScript
'10' + 2 => '102' // Ok on concatène, logique
'10' - 2 => 8 // ?
'10' - '2' => 8 // ???
'10' + - '2' => '10-2' // Je me barre
```

Un petit détour par les types :

```javascript
typeof NaN => "number" // NaN signifie Not a Number
NaN == NaN => false
typeof null => "object"
'super texte' instanceof String => false
null == undefined => true
```

Ceci n'est que quelques exemples. La première chose à faire est de ne pas utiliser `==` mais bien `===` (triple égal).
Ça évitera bien des problèmes. Et oui, il y a des explications, ce n’est pas le problème.
Le problème c'est que ce n'est pas intuitif. On n'obtient pas ce qu'on s'attendait à avoir.

Mais ces bizarreries sont parfois problématiques et impliquent de tester les types.
Là on rentre dans l'avis personnel, mais un typage faible et dynamique n'est pas pratique et pose plus de problèmes qu'il en résout.

Ha et comme c'est un langage interprété et non compilé on voit les erreurs qu'à la compilation, sinon c'est pas drôle :blush:.

## La complexité grandissante du langage

JavaScript d'après son créateur a été créé pour être simple et pour les néophytes.
Mais il s'est complexifié, pour répondre à des problèmes du langage (coucou les [callback hell](http://callbackhell.com/) :smile:).
Certaines demandes de la communauté sont d'ailleurs refusées, car trop difficiles à maitriser pour un débutant.

Plein de concepts sont peu connus ou mal maitrisés, par moi y compris :wink:.
Pour un débutant, une fois qu'on a compris le fonctionnement des callbacks et de l'asynchrone, il reste plein de choses à voir :

- [Proxy](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Proxy),
- [Symbol](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Symbol)
- [Iterateur](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/iterateurs_et_generateurs)
- [Générateur](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Generator)
- [Promesse](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Promise)
- Surement d'autres que je ne connais pas ?

## Langage non objet

JavaScript n'est pas un langage objet comme Java ou C++.
Mais bien un langage objet à prototype. C'est un concept bien particulier et différent.
Même déroutant pour ceux qui ont appris avec des langages objets.

{{< notice >}}
Ouais mais maintenant on peut faire des classes !
{{< /notice >}}

Ouais, mais il a fallu ECMAScript 2015, et en plus c'est juste une autre façon d'écrire la même chose qu'en prototype !
Donc ça ne change rien.

Mais surtout ce qu'il manque à tous les développeurs Objets, ce sont les sacrosaintes **Interfaces** :heart::heart::heart:.

Je suis de la team composition dans la guerre Héritage vs Composition, donc je suis mal partit.

## Ils ne font pas comme tout le monde

Y a des fonctionnements qui sont standards, documentés et généralisés.
Et il y a les comportements qui sont faits de la même façon partout intuitivement.

Partout ? Non, JavaScript fait différemment !

C'est principalement ici que je vais présenter des expériences perso.

{{< figure src="https://media.giphy.com/media/wvQIqJyNBOCjK/giphy.gif" alt="gif rage" caption="y a vraiment besoin d'une description ?" >}}

### Le traitement des dates

On commence doucement. Imagine, tu as une date, *1 janvier 2020 à minuit*.
Et que tu la veux à UTC+2 et bien ce n’est pas facile !

Avec JS, l'objet Date est **OBLIGATOIREMENT** localisé avec le navigateur. En France, à UTC+1 en hiver.
Donc tu prends ton timestamp (utc), tu ajoutes 2 heures. Et tu as donc ta date en utc+2 ...

Bon bah maintenant tu veux la formater avec le formatter de JS, qui prend obligatoirement l'objet Date.
Bah ce con rajoute 1 heure, bah oui on est en UTC+1.

{{< notice >}}
Ouais bah enlève 1h !
{{< /notice >}}

Ouais bah non, ça dépend où est l'utilisateur.
Et imagine qu'il ne veut pas une date à sa timezone actuelle, mais une autre...

Tu en veux une autre ?

Tu crées une date avec un offset, tu veux récupérer l'offset, tu penses récupérer l'offset de cette date ? :joy:
Bah non, ça retourne ton offset à toi, celui du navigateur en gros.

Ha et si tu es en offset UTC+1 et bien tu obtiens -60. Non pas 60 ou 1, mais -60 ...

```javascript
const date = new Date('August 19, 2020 23:15:30 GMT+07:00');
console.log(date1.getTimezoneOffset()); // => -60
```

Bon il y a surement une explication logique, mais pour un langage qui veut être simple et accessible ...

### Les headers des requêtes http

Celui-ci je l'ai toujours en travers de la gorge.

Imagine un service, Java ou PHP, qui répond à une requête HTTP en fournissant un header avec plusieurs valeurs.

```
statut: alive
statut: dead
statut: sleep
```

Simple et efficace, ça respecte le standard, tu t'attends donc à le récupérer comme ça coté JS. Et bien non !

D'abord si tu passes par un proxy JS, comme express il va automatiquement le transformer en :

```
statut: alive, dead, sleep
```

*Ton consentement n'est pas nécessaire !*

Ensuite, même si tu le reçois en multi ligne, quand tu récupères les headers sous format brut depuis la requête, tu as une String où il a décidé de lui-même de le transformer...

Tu le sens le temps que j'ai passé à chercher d'où venait le problème ?

Pour info, la [documentation](https://www.w3.org/Protocols/rfc2616/rfc2616-sec4.html) dit 
*The field value MAY be preceded by any amount of LWS, though a single SP is **preferred***.

En gros, *utilise qu'une seule valeur par ligne c'est mieux* et JS il a dit **non !**

Des trucs comme ça, c'est régulièrement quand tu fais du JS bas niveau, dans le sens en utilisant les objets de bases, sans librairies ou framework.
 
## Tout doit être en JS maintenant

Je ne sais pas quelle est l'origine de quoi, mais on a vu fleurir plein de formations de "dev web" de quelques semaines à mois.
Je ne remets pas en compte la qualité de ces formations. Mais en temps aussi réduit, on ne voit pas énormément de choses et principalement du JS.

Donc si on est amené à devoir travailler coté serveur ou embarqué, bref autre part qu'une page web.
Et bien faisons du node et importons la page web partout (coucou [electron](https://www.electronjs.org/) :wink:).

Et on oublie que JS a des avantages, mais aussi des défauts et qu'un unique outil ne s'utilise pas dans toutes les situations.
Va poser du carrelage avec un fer à souder, je te regarde.

{{< figure src="https://media.giphy.com/media/hiqTKqU40YKI0/giphy.gif" alt="gif bricolage raté" caption="un outil pour tout faire" >}}

Donc on fait de plus en plus de JS et on importe ces problèmes avec nous.

## Les librairies moisies

Je ne sais pas si c'est spécifique à JS ou non, mais je trouve que les éditeurs de solutions négligent largement les clients JavaScript.
Je ne vais pas citer de nom :wink:, mais lorsque je navigue sur les Jira de certains logiciels, je tombe sur beaucoup de problèmes liés à JS.

En gros, la version JS du client ou du logiciel est faite à moitié.
Peut-être que cela vient d'une adaptation non voulue et tardive au langage, je ne sais pas.

En plus, on retrouve une quantité énorme de librairies donc beaucoup plus supportées ou non fonctionnelles.
Si elle ne marche pas, ce n’est pas grave y en a 10 autres tout aussi jetables.
J'ai moins cette impression dans le monde Java avec Maven.

Et je n'ai pas parlé des librairies avec des dizaines de dépendances qui font qu'aggraver le problème.

{{< figure src="/images/js/node_modules.jpeg" alt="node_modules profondeur" caption="exagéré ? si peu ..." >}}

## Conclusion

Bon alors on dit quoi ? Et bien personnellement, je trouve que JS s'est super !
{{< notice >}}
Tu viens de passer 1h à le démonter ...
{{< /notice >}}

Ouais, mais j'ai fait des centaines de choses avec. Des trucs rigolos, utiles, sympas, à la con...
Et surtout c'est le langage que j'utilise tous les jours.

La communauté va vite, il y a énormément de choses qui se passe tous les jours.
Ça a permis à beaucoup de gens de faire beaucoup de choses. Et des choses super !
Il sert même à piloter des vaisseaux spatiaux ! :blush:

{{< tweet 1267227834096861184 >}}

Bon, il reste des boutons basiques au cas où ... :wink:

Le web a énormément évolué ces 20 dernières années en grande partie grâce aux évolutions de JS et c'est top !

Mais ce n'est pas un langage facile à maitriser avec des comportements étranges. 
Je ne suis donc pas étonné de voir apparaitre des solutions comme [TypeScript](https://www.typescriptlang.org/), [flow](https://flow.org/), [Dart](https://dart.dev/).
Et les 50 frameworks JavaScript par jour. Amenant leurs propres problèmes :wink:.

Mais je crois que le principal problème de JavaScript est son manque de maturité, 
il se remarque par le manque d'intégration dans les IDE pour le débogage ou les tests par exemple (IDEA avec Java :heart:), le support approximatif ...

Merci de m'avoir lu (c'était long ...), j'expose ici mon avis et ma (petite) expérience, j'attends les tiennes en commentaire (fais-nous rire :smile:).

Bisou :heart:.
