---
title: "Home Assistant, envoyer des SMS avec free"
date: 2021-02-12T22:01:00+0200
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

Salut ! Dans ce petit article toute la configuration et surtout **comment tester l'envoi de SMS avec free** via Home Assistant.

Alors évidement il vous faut un home assistant et un forfait free :wink

## La configuration

Pour commencer il faut récupérer les tokens chez free dans l'[espace client](https://mobile.free.fr/account/) puis dans les [options](https://mobile.free.fr/account/mes-options) une fois connecté.

On active l'option **Notifications par SMS** et on copie le token.

{{< figure src="/images/ha/free_sms.png" alt="notification sms" caption="on copie tout ça !" >}}

On met dans le fichier secrets.yaml le token

```yaml
free: coucoucou
```

Et dans le fichier de configuration.yaml

```yaml
- name: SMS_FREE
  platform: free_mobile
  username: IDENTIFIANT_FREE
  access_token: !secret free
```

Il faut évidement remplacer IDENTIFIANT_FREE par le votre :wink:

Et on redémarre !

## Tester si c'est bon

Il n'y a pas de message si la configuration fonctionne, il faut essayer !

Pour cela, on va dans outils de développement puis services.
Il faut ensuite choisir le service correspondant au nom, ici c'est notify.sms_free.
Et on va remplir le message !

```yaml
message: "test !"
```

Et si tout va bien, le SMS est arrivé après avoir appuyé sur appeler le service :wink:.

{{< figure src="/images/ha/notify_free.png" alt="configuration" caption="ça doit ressembler à ça" >}}

## Conclusion

J'espère que ça aura pu vous aider ! Et que vous allez l'intégrer dans vos futurs scénarios :wink:

Si je vous ai sauvé la vie, vous pouvez même m'offrir une bière :heart:.

La bise :wink:.
