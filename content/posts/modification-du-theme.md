---
title: "Modification d'un thème Hugo"
date: 2020-06-13T21:11:00+0200
lastmod: 2020-06-17
draft: false
tags: 
- Hugo
- Jamstack
- test
- theme
- blog
keywords: 
- Hugo
- Jamstack
- test
- theme
- font
- JetBrainsMono
- favicon
- icon
- blog
toc: true
description: "Modification du thème"
---

Bon ce [thème](https://github.com/Track3/hermit) est sympa, mais je voudrais le personnaliser et ajouter des fonctionnalités.

## Modification des couleurs

La personnalisation ça commence par choisir de nouvelles couleurs !

Je lis donc la doc, je copie-colle le fichier `_predefined.scss` dans le dossier `assets/scss`.
Ca ne marche pas, je relis la doc. Il faut avoir la version extended de Hugo :innocent:.
La version **classique** ne compile pas les fichiers `.scss`. Très bien, j'installe la bonne version et c'est reparti !

Je choisi des couleurs venant du thème [Nord](https://www.nordtheme.com/), je trouve ça joli et je n'ai aucune qualité d'artiste :sweat_smile:.

- $theme: [#b48ead](https://www.color-hex.com/color/b48ead), couleur d'appui, celle des liens, elle risque de changer.
- $text: [#e5e9f0](https://www.color-hex.com/color/e5e9f0), couleur du texte, un quasi blanc.
- $light-grey: [#2e3440](https://www.color-hex.com/color/2e3440), couleur du fond.
- $dark-grey: [#3b4252](https://www.color-hex.com/color/3b4252), couleur du menu du bas;
- $highlight-grey: [#434c5e](https://www.color-hex.com/color/434c5e), couleur de `ça`;
- $midnightblue: [#4c566a](https://www.color-hex.com/color/4c566a), couleur des bouts de code;

Je suis assez content du résultat, c'est cohérant et j'aime bien ! Donc continuons ! :+1:

## Ajout des derniers articles dans l'accueil

La page d'accueil est très jolie, mais ça me gêne de faire 2 clics pour arriver à un article.
J'aimerais que le dernier article ou les 2 derniers soient mis en avant dans l'accueil.
Mais pour ça, il va falloir modifier directement les templates.

J'ajoute un dossier `layouts/_default` à la racine du projet, je copie-colle baseof.html et je modifie le title.
Je relance le serveur de dev (`hugo serve`) et je vois que le `title` à changer ! :+1:

Donc, ce que je mets dans ce dossier surcharge le thème. Il faut donc que je trouve le template qui gère l'accueil et que je le modifie.

Le fichier correspondant est `index.html`, logique, donc il ne faut pas le mettre dans `layouts/_default` mais dans `layouts`.
J'ajoute un bouton et je vois qu'il s'affiche, on avance :+1:.

Je me base sur le `related-posts.html`, le composant qui affiche **Voir également** à la fin des articles.

```html
{{- $related := .Site.RegularPages.Related . | first 5 }}
{{ with $related }}
<div class="related-posts thin">
   <h2>{{ i18n "seeAlso" }}</h2>
   <ul>
   {{ range . }}
   <li><a href="{{ .RelPermalink }}">{{ .Title }}</a></li>
   {{ end }}
   </ul>
</div>
{{ end -}}
```

De ce que je comprends :
- on va chercher les pages et on prend les 5 premières
- on les affiche sous forme de liste avec le lien

Je commence par extraire la variable `5` après le first.
Pour cela, j'ajoute dans ma config sous `params` la variable `numberArticlesPreview` et je lui donne la valeur 3.

Ensuite d'apres la [doc](https://gohugo.io/variables/site/), il suffit de remplacer le `5` par `.Site.Params.numberArticlesPreview`.
Facile :+1:.

Et pour finir, le **voir également** ne me plait pas trop, je vais donc le ressortir aussi dans une variable.

On obtient donc dans le `index.html` :

```html
{{- $related := .Site.RegularPages | first .Site.Params.numberArticlesPreview }}
{{- $name := .Site.Params.namePreview }}
{{ with $related }}
<nav>
    <div class="related-posts thin">
        <h2>{{ $name }}</h2>
        <ul>
            {{ range . }}
            <li><a href="{{ .RelPermalink }}">{{ .Title }}</a></li>
            {{ end }}
        </ul>
    </div>
</nav>
{{ end -}}
```

Et le résultat final :

{{< figure src="/images/accueil.png" alt="capture de l'accueil" caption="Mon accueil avec les articles !" >}}

Je suis hyper content ! :blush:

## Date en Francais

Dans la liste des articles, la date associée est en anglais et surtout le format ne me plait pas :

{{< figure src="/images/date.png" alt="Date en anglais" caption="Date en anglais" >}}

Dans la config, on peut configurer le formattage. Mais ce n'est pas le problème.

Avec mon moteur de recherche préféré, je tombe sur cet [article](https://gohugo.io/content-management/multilingual/#customize-dates) dans la documentation officielle pour expliquer justement comment traduire en Français.
Si c'est pas magnifique ! :blush:

Donc c'est repartit, je copie-colle le fichier `list.html` dans mon `layout/_default`, je cherche la ligne qui affiche la date :

```html
<span class="post-day">{{ .Date.Format .Site.Params.dateformShort }}</span>
```

Il récupère la date de l'article et applique le format définit dans les paramètres.
Je pense que ça va être compliqué d'avoir la traduction et le formattage.

Je suis donc la documentation, je crée le fichier `data/mois.yaml` :

```yaml
1: "janvier"
2: "février"
3: "mars"
4: "avril"
5: "mai"
6: "juin"
7: "juillet"
8: "août"
9: "septembre"
10: "octobre"
11: "novembre"
12: "décembre"
```

Et je modifie la ligne en faisant directement un copié-collé, c'est juste ce qu'il me faut !

```html
<span class="post-day">{{ .Date.Day }} {{ index .Site.Data.mois (printf "%d" .Date.Month) }} {{ .Date.Year }}</span>
```

{{< figure src="/images/date2.png" alt="Date en français" caption="Date en français" >}}

Parfait ! :blush:

J'en ai profité pour changer les dates dans les métadonnées en bas de chaque article. Ainsi que tout en haut de chaque article, juste avant le titre.

## Changement de la font

La police utilisée pour les bouts de code est pas mal. Mais celle que j'utilise dans tous mes IDE est [JetBrainsMono](https://www.jetbrains.com/fr-fr/lp/mono/).
Je l'apprécie beaucoup et elle est particulièrement adaptée au code.
Je la mets donc partout et en plus elle est sous licence en [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0).

Que demander de plus ? :smile:

- Je télécharge l'archive sur le site
- J'extrais la police dans `/static/fonts`
- J'importe la police et je l'applique

```css
@font-face {
  font-family: "JetBrainsMono";
  font-style: normal;
  src: url(/fonts/JetBrainsMono-Regular.woff2?#iefix) format('woff2'), url(/fonts/JetBrainsMono-Regular.woff) format('woff');
}

$fonts: "Trebuchet MS", Verdana, "Verdana Ref", "Segoe UI", Candara, "Lucida Grande", "Lucida Sans Unicode", "Lucida Sans", Tahoma, sans-serif;
$code-fonts: "JetBrainsMono", Consolas, "Andale Mono WT", "Andale Mono", Menlo, Monaco, "Lucida Console", "Lucida Sans Typewriter", "DejaVu Sans Mono", "Bitstream Vera Sans Mono", "Liberation Mono", "Nimbus Mono L", "Courier New", Courier, "YaHei Consolas Hybrid", monospace, "Segoe UI Emoji", "PingFang SC", "Microsoft YaHei";
```

Et voilà ! Le bout de code juste au-dessus utilise normalement JetBrainsMono !
 

## Modification de l'icône

Bon, je rappelle que je ne suis pas un artiste. Je ressors ma doc, je vois un [lien](https://realfavicongenerator.net/) pour générer les icônes.

Je sors donc mon paint.net, lance une image en 260x260, je mets le même fond que le thème et je mets un B avec la font `JetBrainsMono`.
Je vous ai dit que j'adorais cette font ?

Ensuite :
- J'exporte mon fichier
- Je l'importe avec le site
- Je clique sur oui partout
- Je télécharge l'archive
- Et je copie tous les fichiers dans `/static`

Et voilà, facile ! :+1: 

## Conclusion

Et bien, c'est plus facile que ce que je pensais !

Toutes les modifications sur le style sont simplissimes.
Sur les parties de template d'Hugo, la syntaxe est un peu particulière, ou du moins, je ne suis pas habitué.
Mais on se débrouille avec la documentation et en testant.

Mais c'est plutôt facile en tâtonnant et modifiant des bouts de composants, le serveur de dev affichant directement le résultat.
Avec des erreurs à la compilation explicite. La documentation aide beaucoup, elle est très bien faite !
Il est possible que je modifie d'autres choses à l'avenir.

Je rappelle que le blog est sur un dépôt public si vous voulez voir à quoi il ressemble. Il y a même un lien avec le commit au bas de la page :wink:.

Merci de m'avoir lu :heart:. 