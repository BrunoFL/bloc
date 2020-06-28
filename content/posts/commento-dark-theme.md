---
title: "Adapter Commento à un dark thème"
date: 2020-06-18T18:01:00+0200
lastmod: 2020-06-18
draft: false
tags: 
- Hugo
- Jamstack
- commentaire
- theme
- commento
- blog
keywords: 
- Hugo
- Jamstack
- test
- theme
- commentaire
- commento
- disqus
- blog
- dark
toc: true
---

Si comme moi vous avez intégré commento avec un thème dark vous avez peut-être remarqué quelque chose.

{{< figure src="/images/commento/commento-dark.png" alt="Commento dark theme" caption="Kewaa ???" >}}

**On ne voit rien du tout !!! :angry:**

La moitié des textes ne sont pas visibles, les boutons c'est pareil. En plus, j'ai l'impression qu'ils ont utilisé le même [thème de couleur](https://www.nordtheme.com/) que moi donc on ne voit rien.
Bref ce n’est pas top. Et le souci c'est qu'on s'en rend compte qu'à partir du moment où il y a des commentaires.

On va régler ça rapidement ! :wink:

## La solution

Pour un problème de style, il faut du CSS !

J'ai d'abord testé en ajoutant un fond un clair sur certaines parties.
Puis je me suis dit que ce serait plus joli sur la totalité, en plus les commentaires ressortiront mieux !

```css
#comments {
    background-color: #eceff4;
    padding: 10px;
    border-radius: 10px;
}
```

1. Je commence par définir une couleur de fond clair.
2. J'ajoute un petit espacement (`padding`) pour éviter que les composants touchent les bordures.
3. Et j'arrondis la bordure pour que ce soit plus joli.

J'applique le tout à la div qui sert à insérer les commentaires.
Je mets le tout dans un fichier css, j'ajoute le fichier à ma config.

{{< figure src="/images/commento/commento-dark2.png" alt="Commento dark theme" caption="Mieux !!" >}}

**Et voilà :+1:**

## Conclusion

Un problème facile à régler et à personnaliser !

Ce problème peut paraitre anecdotique, mais il ne faut jamais lésiner sur l'accessibilité.
Il ne faut pas oublier qu'en France, la proportion de daltoniens est d'environ 8 % chez les hommes et de 0,4 % chez les femmes[^1]. 

J'espère que ça pourra vous aider, bisou :heart:.

[^1]: https://fr.wikipedia.org/wiki/Daltonisme.