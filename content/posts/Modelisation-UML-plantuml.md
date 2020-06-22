---
title: "Modélisation et schémas UML simplissime avec PlantUML"
date: 2020-06-22T23:50:00+0200
lastmod: 2020-06-22
draft: false
tags: 
- dev
- outil
keywords: 
- uml
- plantuml
- outil
toc: true
---

Article assez court pour vous présenter un outil que j'utilise très régulièrement [PlantUML](https://plantuml.com/fr/) !

Si comme moi, vous êtes quelqu'un de visuel, qui a besoin de voir des schémas pour comprendre, mais qui a la flemme de les faire.

{{< figure src="https://media.giphy.com/media/BmmfETghGOPrW/giphy.gif" alt="gif réflexion maths" caption="moi essayant de comprendre un truc" >}}

Alors cet outil est fait pour vous !

En gros, c'est un outil pour générer beaucoup de schémas notamment [UML](https://fr.wikipedia.org/wiki/UML_(informatique)) hyper simplement.
Moi, ceux que j'utilise le plus :

- Diagrammes de séquence, pour le fonctionnement et les communications d'un service
- Diagrammes de cas d'utilisation, pour l'utilisation d'une interface ou d'un système
- Diagrammes de classes, pour l'architecture d'un composant
- Diagrammes d'activité, pour expliquer un algo ou un cheminement de pensée

Il sait globalement créer tous les diagrammes UML. Mais il ne se limite pas à UML, en plus il sait faire :

{{< figure src="/images/uml2.png" alt="mindmap UML" caption="mindmap de qualité" class="right" >}}

- Maquette d'interface graphique
- Diagrammes de Gantt 
- Diagrammes d'idées, mindmap 

Et plein d'autres que je ne connais pas :blush:.

## Comment ça marche ?

On peut l'utiliser avec :
- Le [serveur en ligne](http://www.plantuml.com/plantuml/uml)
- Un jar à télécharger, qui va lire le contenu et les modifications d'un dossier
- Une extension IDEA, c'est cette version que j'utilise

L'avantage de l'extension c'est que c'est généré directement dans l'IDE et qu'on peut exporter dans différents formats en un clic.
On prend un fichier, on écrit du texte dedans et l'outil crée un schéma. **C'est tout !**

Par exemple, imaginons un échange entre une page web et un service d'authentification ultra basique, faisons un petit digramme de séquence pour bien visualiser.
```
@startuml
App -> Gateway: POST identifiant
Gateway -> front : token

App --> Gateway: GET utilisateur
App <-- Gateway: utilisateur
@enduml
```

Bon forcement, il y a une syntaxe à respecter, mais on obtient en 2 minutes un schéma clair et efficace :

{{< figure src="/images/uml1.png" alt="capture schéma de séquence UML" caption="c'est vraiment très intéressant" >}}

Facile :+1: ! 

La syntaxe dépendra du schéma, on peut contrôler un peu la représentation et la signification en choisissant une flèche ou un marqueur plutôt qu'une autre.
En gros, c'est vraiment facile à utiliser.
 
Et comme c'est du texte, on peut le versionner et le générer [automatiquement](https://plantuml.com/fr/running) :wink:.
Par exemple avec Maven, Gradle ou pour générer des diagrammes d'une API swagger.

On peut, en théorie, générer une représentation totale d'un système !
Construire des diagrammes de séquence pour chaque test ou une API.
Générer un diagramme de Gantt pour gérer un projet (faut être motivé).

Si vous avez un composant ou un service relativement compliqué à utiliser un bon schéma dans le readme fera gagner du temps à tout le monde :smile:.

## PlantUML c'est cool

Ce n'est pas l'outil le plus indispensable du monde, encore moins le plus sexy.
Mais, c'est un outil super sympa, facile à utiliser et très bien documenté ! 
Et surtout il aide beaucoup de monde :blush:.
La documentation fournit beaucoup d'exemples que l'on peut éditer et montre tout ce qu'il faut pour personnaliser les schémas.

Ça vous servira j'espère pour des rapports, des documentions, mais aussi pour avoir une meilleure vision.

Bref, je l'ai utilisé pendant mes études et aujourd'hui très régulièrement au travail et je vous conseille d'en faire autant :wink:.

Bisou :heart:.