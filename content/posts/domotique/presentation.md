---
title: "Home Assistant, le premier essai"
date: 2021-02-12T20:51:00+0200
lastmod: 2021-02-12
draft: false
tags:
- domotique
- home assistant

keywords:
- domotique
- home assistant
- presentation
---

Salut ! Dans cet article quelques explications sur les concepts de base, l'idée ce n'est pas de faire un tuto, la documentation sera toujours meilleure !
Mais plutôt présenter rapidement et passer au concret le plus rapidement possible !

On va parler de supervisor, d'intégrations, de plugins ...

Je suis loin d'être expert, je transmets juste mon utilisation et ma compréhension.
Mais je pense que c'est un bon début :wink:.

## La base

On va passer rapidement sur les éléments du menu principal :
- Aperçu : affichage des informations cartes et badges, le tableau de bord
- Carte : carte avec la maison et les personnes
- Journal : journal des évènements par ordre chronologique
- Histoire : journal plus complet avec toutes les entités
- File Editor : éditeur de fichier, pour les configurations
- Navigateur multimédia : affiche les médias

{{< figure src="https://media.giphy.com/media/xTiN0m5rI2WK4xRJRe/giphy.gif" alt="motivé" caption="On reste motivé !" >}}

### Outils de développement

On peut penser que c'est réservé aux développeurs du logiciel, mais pas du tout.
Il servira à debugger les objets, les manipuler, tester des choses.

Il fournit aussi des exemples, hyper pratique pour ne pas galérer pendant la configuration !

Ça peut servir pour connaitre l'état courant d'une entité, c'est à dire connaitre la température retournée d'un capteur.
Appeler un service, commander une entité, un service externe ...
Lancer un évènement pour voir comment le système réagit.

Clairement sous-coté !

### Supervisor

On peut confondre avec les intégrations, mais ce sont les "paquets", les logiciels internes au fonctionnement du système.
On peut installer VS Code, le DNS, le partage de fichier dans Windows, un serveur MQTT, ...

Ce sont les applications du système. On peut également redémarrer chaque composant interne. Faire des sauvegardes ou des restaurations.

### Configuration

C'est ici que l’on contrôle les intégrations (objets, services ...), les entités (tout ce qui est visible, configurable, communicant avec le système).

Les blueprints, plans pré conçus par la communauté. Les automatisations à créer soi-même.
Les entrées, des boutons, barre de saisies ... Les balises NFC, les utilisateurs...


## Lançons Spotify sur la TV !

Au premier lancement Home Assistant a tout de suite trouvé plusieurs intégrations, comme un grand !
On commence par Google Cast sur ma télévision, en 3 clics c'est fait.

On peut éteindre, mettre en pause lancer des lectures :smile: !

Mon idée c'est de mettre Spotify sur la TV, on va donc ajouter l'intégration, mais ça demande un peu de configuration.
On part sur la [documentation](https://www.home-assistant.io/integrations/spotify/), ce n’est pas hyper compliqué, c'est bien expliqué et ça se fait bien !

Donc je mets le token dans le fichier secrets.yaml et dans le fichier de configuration j'ai :

```yaml
Spotify:
  client_id: fd7cc1...
  client_secret: !secret Spotify
```

On va juste reboot régulièrement Home Assistant... Et voilà j'ai un badge avec la pochette du morceau en lecture !

Si je clique dessus et que je mets lecture ça lit directement sur la TV ! Je n’ai rien eu à faire !

On peut maintenant imaginer un scénario simple, du style à 16h30 met telle chanson (pour ne pas oublier le gouter !).

## Mes plugins

Voici la liste des plugins que j'ai actuellement d'installée :

- Samba Share, pratique pour copier-coller des fichiers depuis Windows
- Visual Studio Code, un peu plus sympa que File editor
- deCONZ, pour la communication zigbee, mais on en reparlera
- Duck DNS, pour pouvoir accéder depuis l'extérieur de mon réseau au logiciel
- HACS, store non officiel de composants, thèmes, intégrations ...

## Conclusion

Voilà, c'est la fin du premier véritable article sur Home Assistant.
L'idée c'était de faire un petit tour et de mettre un peu les mains dans le cambouis !

La bise :wink:.