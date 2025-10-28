# Qu'est-ce que HTML ?

- HTML est un langage de balisage qui définit la structure du contenu. Un document HTML est une suite d'éléments utilisés pour encadrer ou envelopper le contenu textuel afin de définir sa structure et de lui faire adopter un certain comportement.
- Prenons un exemple — le contenu suivant sera affiché sur la même ligne lorsqu'il sera affiché sur une page web, car il n'est pas structuré de quelque manière que ce soit :

  ```
  Instructions de la vie :
  Manger
  Dormir
  Répéter
Si nous enveloppons ce contenu avec les éléments HTML suivants, nous pouvons transformer cette seule ligne en un paragraphe `<p>` et trois puces `<li>` :

**HTML**
```html
<p>Instructions de la vie&nbsp;:</p>

<ul>
  <li>Manger</li>
  <li>Dormir</li>
  <li>Recommencer</li>
</ul>
```

- Ce code HTML s'affichera ainsi dans un navigateur web :

<img width="660" height="660" alt="image" src="https://github.com/user-attachments/assets/7a3ef38e-0c0b-4cfd-9e05-147cac188a72" />

- En plus de structurer du texte, HTML a de nombreux autres usages : faire en sorte que du texte ou des images mènent à d'autres pages web, intégrer des images ou des vidéos, créer des tableaux de données, etc.

# Créer votre premier document HTML

- Voyons comment les éléments individuels sont combinés pour former une page HTML. Dans cette section, vous allez créer un fichier HTML de base et examiner sa composition.
    - Dans votre dossier projets-web, créez un nouveau dossier nommé mon-premier-site.
    - À l'intérieur de mon-premier-site, créez un nouveau fichier appelé index.html, et insérez-y le code suivant exactement comme indiqué.

**HTML**
```html
<!doctype html>
<html lang="fr">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>Ma page de test</title>
  </head>
  <body>
    <img src="" alt="Mon image de test" />
  </body>
</html>
```

- Voici ce que nous avons :

- `<html></html>` : L'élément <html> englobe tout le contenu de la page et est parfois appelé élément racine. Il inclut aussi l'attribut lang, qui définit la langue principale du document.
- `<head></head>` : L'élément <head> sert de conteneur pour tout ce que vous souhaitez inclure dans la page HTML qui n'est pas du contenu affiché aux visiteur·euse·s. Cela inclut par exemple des mots-clés et une description de la page pour les résultats de recherche, du CSS pour la mise en forme, des déclarations d'encodage de caractères, etc.
- `<meta name="viewport" content="width=device-width">` : Cet élément viewport garantit que la page s'affiche à la largeur de la zone d'affichage du navigateur, empêchant les navigateurs mobiles d'afficher des pages plus larges que la zone d'affichage puis de les réduire.
- `<title></title>` : L'élément <title> définit le titre de votre page, qui apparaît dans l'onglet du navigateur où la page est chargée. Il sert aussi à décrire la page lorsqu'on l'ajoute aux favoris.
- `<body></body>` : L'élément <body> contient tout le contenu que vous souhaitez afficher aux utilisateur·ice·s web lorsqu'ils visitent votre page, qu'il s'agisse de texte, d'images, de vidéos, de jeux, de pistes audio, etc. Pour l'instant, il ne contient qu'un seul élément <img>, mais nous ajouterons plus de contenu par la suite.

# Images

- Revenons sur l'élément `<img>` :

**HTML**
```html
<img src="" alt="Mon image de test" />
```

- Cela permet d'intégrer une image dans notre page à l'endroit où elle apparaît. Cela se fait via l'attribut src `source`, qui contient le chemin vers le fichier image à intégrer.
- Nous avons également inclus un attribut `alt` alternatif. Dans l'attribut alt, vous indiquez un texte descriptif pour les personnes qui ne peuvent pas voir l'image, pour les raisons suivantes :
    - Elles sont en situation de handicap visuel. Les utilisateur·ice·s avec un handicap visuel important utilisent souvent des outils appelés lecteurs d'écran qui lisent le texte alternatif à voix haute.
    - Un problème empêche l'affichage de l'image. Si l'attribut `src` ne contient pas un chemin valide vers une image, le texte alternatif sera affiché à la place :

<img width="108" height="36" alt="image" src="https://github.com/user-attachments/assets/aff88dfc-a025-41c3-aaa5-bbee7aca5c72" />

- Le texte alternatif que vous écrivez doit fournir suffisamment d'informations à la lectrice ou au lecteur pour qu'il·elle comprenne ce que l'image représente. Dans cet exemple, notre texte actuel « Mon image de test » n'est pas idéal car il n'apporte aucune information descriptive sur l'image. Une bien meilleure alternative pour notre logo Firefox serait « Le logo de Firefox : un renard enflammé entourant la Terre ».

- Affichons maintenant votre image.
    - Dans le dossier `mon-premier-site`, créez un nouveau dossier appelé `images` et placez-y l'image que vous avez choisie à l'étape précédente.
    - Dans la valeur de l'attribut `src` de la balise `<img>`, indiquez le chemin vers votre image. Elle se trouve dans un dossier appelé `images`, qui est dans le même répertoire que votre fichier `index.html`, donc le chemin sera `images/` suivi du nom de votre image. Par exemple, si votre image s'appelle `firefox-icon.png`, votre attribut `src` ressemblera à ceci : `src="images/firefox-icon.png"`.
    - Remplacez la valeur de l'attribut `alt` — « Mon image de test » — par un texte qui décrit mieux votre image.
    - Ouvrez votre fichier `index.html` dans un navigateur web. Vous devriez voir votre image s'afficher. Si ce n'est pas le cas, vérifiez votre élément `<img>` avec notre code : assurez-vous qu'il ne manque aucune partie de la syntaxe, comme les guillemets. Vérifiez aussi que le nom du fichier image est correct.

# Baliser du texte

- Cette section décrira certains des éléments HTML essentiels pour baliser et structurer le texte d'un document.

## Titres

- Les éléments de titre permettent d'indiquer les parties du contenu qui sont des titres ou des sous-titres. De la même façon qu'un livre peut avoir un titre principal, des titres de chapitre, des sous-titres, un document HTML peut en avoir également. HTML contient 6 niveaux de titre `<h1>-<h6>`, même si on en utilisera généralement 3 à 4 au plus :

**HTML**
```html
<!-- 4 niveaux de titres : -->
<h1>Mon titre principal</h1>
<h2>Mon titre de deuxième niveau</h2>
<h3>Mon sous-titre</h3>
<h4>Mon sous-sous-titre</h4>
```

> [!NOTE]
> **Note :** En HTML, tout ce qui est écrit entre `<!--` et `-->` est un **commentaire HTML**.  
> Le navigateur ignore les commentaires lorsqu'il affiche le document.  
> Autrement dit, ce qui est écrit en commentaire est uniquement visible dans le code et pas sur la page.  
> Les commentaires permettent d'ajouter des notes utiles à propos du code ou de la logique.

- Essayez maintenant d'ajouter un titre pertinent à votre page HTML avant l'élément `<img>`. Sauvegardez le fichier et observez le dans un navigateur pour voir l'effet.

## Paragraphes

- Les éléments `<p>` servent à contenir des paragraphes de texte ; vous les utiliserez fréquemment pour baliser le contenu textuel ordinaire :

**HTML**
```html
<p>Voici un paragraphe simple</p>
```

- Ajoutez votre texte d'exemple du précédent chapitre dans un ou plusieurs paragraphes, placés juste en dessous de votre élément `<img>`. Enregistrez et affichez votre page dans un navigateur.

## Listes

- Une bonne partie du contenu web prend la forme de listes. HTML possède des éléments dédiés. Baliser une liste se fait toujours avec au moins deux éléments. Les types de liste les plus fréquemment utilisés sont les listes ordonnées et les listes non-ordonnées :
    - Listes non ordonnées : utilisées pour les listes où l'ordre des éléments n'a pas d'importance, comme une liste de courses. Celles-ci sont enveloppées dans un élément `<ul>`.
    - Listes ordonnées : utilisées pour les listes où l'ordre des éléments a de l'importance, comme une liste d'instructions de cuisine dans une recette. Celles-ci sont enveloppées dans un élément `<ol>`.

- Chaque élément d'une liste est placé dans un élément `<li>`.

- Ainsi, si on veut qu'une partie de notre paragraphe devienne une liste, à la place de :

**HTML**
```html
<p>À Mozilla, nous formons une communauté de</p>

<ul>
  <li>Bidouilleuses</li>
  <li>Concepteurs</li>
  <li>Constructrices</li>
</ul>

<p>qui travaillent ensemble…</p>
```
 
- Essayez d'ajouter une liste ordonnée ou non-ordonnée à votre page d'exemple.

# Créer des liens

- Les liens sont importants, ce sont eux qui forment la toile qu'est le Web ! Pour ajouter un lien, on utilisera un élément `<a>` « a » correspondant à « ancre ». Pour placer un lien dans votre paragraphe, suivez les étapes suivantes :
    - Identifiez le texte voulu ici nous prendrons le texte « Manifeste Mozilla ».
    - Entourez-le avec les balises ouvrantes et fermantes d'un élément <a> comme suit :

**HTML**
```html
<a>Manifeste Mozilla</a>
```

- Ensuite :
    - Ajoutez un attribut href à l'élément `<a>` :

**HTML**
```html
<a href="">Manifeste Mozilla</a>
```

- Ensuite :
    - Renseignez la valeur de cet attribut avec l'adresse web vers laquelle vous voulez créer le lien :

**HTML**
```html
<a href="https://www.mozilla.org/fr/about/manifesto/">Manifeste Mozilla</a>
```

- Attention, vous pourriez obtenir des résultats inattendus si vous omettez la partie `https://` ou `http://`, qui indique le protocole, au début de l'adresse. Après avoir créé un lien, cliquez dessus pour vous assurer qu'il pointe à l'endroit voulu.




















































































`    `



































































































































































