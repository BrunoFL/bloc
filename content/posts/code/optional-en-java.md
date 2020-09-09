---
title: "Les Optional en Java, c'est bien, mangez-en !"
date: 2020-09-095T20:00:03+0200
lastmod: 2020-09-09
draft: false
tags: 
- java
- dev
keywords: 
- java
- optional
toc: true
---

Hey ! Avec ce titre pas ouf, j'aimerais te convaincre, que les [Optional](https://docs.oracle.com/javase/8/docs/api/java/util/Optional.html)
 en Java c'est vraiment cool ! Et qu'ils ne sont pas suffisamment utilisés !

Ça date de Java 8, ouais ce n’est pas tout jeune, mais ça veut dire que tu peux forcément l'utiliser ! :wink:

Son principal objectif est d'éviter les `NullPointerException` et l'utilisation du `null` en général.
En gros, pour éviter les erreurs.

Mais il y a aussi un autre objectif, ajouter du sens aux fonctions, je vais m'expliquer :smirk:.

## Comment on fait ?

On part d'un objet, et on va le mettre dans un container, dans un Optional :
```java
public Optional<String> getValue(){ 
    String value = null; 
    // Faites des choses intelligentes ici 
    return Optional.ofNullable(value); 
}
```
Première chose, depuis l'extérieur on voit que la fonction retourne un `Optional`, donc on sait que potentiellement la fonction peut retourner `null`.

Et pour moi, on touche le principal avantage, la fonction peut retourner `null`, on le sait et on ne peut pas l'ignorer !

Ensuite, on peut facilement le manipuler :
```java
Optional<String> value = Optional.ofNullable("plok");
if (value.isPresent()){ // On teste
    String val = value.get() // On récupère
}
if (value.isEmpty()){

}
```

C'est facile, c'est plus joli qu'un `value == null`, plus facile à lire. Il y a aussi son opposé pour éviter un `!`.
Et on finit par un `get` pour avoir la valeur, c'est simple, c'est classe, c'est cool ! :blush:

## Mais ce n'est pas tout !

Et non ! Là il y a la base, mais il y a des petits trucs en plus :

```java
value.orElse("Default"); // Une valeur s'il n’y en a pas
value.orElseThrow(new Exception("Merde !")); // Une exception s'il n’y en a pas
value.ifPresent(val -> System.out.println(val)) // Une lambda ?
```

Avec le `orElse` on peut faciliter l'implémentation de valeur par défaut, avec le `orElseThrow` soulever des erreurs particulières 
et avec le `ifPresent` faire un code particulier.

Je l'utilise dans le cas de la vérification de paramètre dans une API, je vérifie si ma requête possède la valeur et selon le cas je définis une valeur.
Sinon, je peux soulever une Exception en fonction du cas.

{{< figure src="https://media.giphy.com/media/kEKcOWl8RMLde/giphy.gif" alt="joie" caption="Joie sur nous !" >}}

Et c'est particulièrement utile dans les cas des Stream !
Il y a d'autres fonctions à aller tester, je ne vais pas tout faire ! :wink:

## Les inconvénients ?

Bah je ne trouve pas qu'il y en ait. Il faut juste l'utiliser au bon moment.
La norme (et le [créateur](https://stackoverflow.com/questions/26327957/should-java-8-getters-return-optional-type/26328555#26328555) de la classe) montre juste qu'il ne faut pas l'utiliser dans certains cas :
- Si la fonction ne peut pas retourner `null`, un getter par exemple, ouais c'est bête à dire, mais la routine tout ça ...
- En attribut de classe
- En paramètre d'une fonction
- Pour les collections, retourner une collection vide

D'une manière générale, éviter d'avoir des `null`, reste la meilleure solution.

## Conclusion

Bref, les `Optional`, c'est hyper facile à utiliser, ça simplifie et ça sécurise, mais c'est malheureusement pas assez utilisé !
En plus et c'est hyper cool d'avoir un code plus clair et plus lisible !

Plus aucune raison de ne pas le faire !

Tu connaissais ? Tu les as déjà utilisés ?

Merci :heart:, bisou.
