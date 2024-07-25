# JavaScript - Obfuscation 3
## Write UP

_________


<!-- TOC -->

- [JavaScript - Obfuscation 3](#javascript---obfuscation-3)
  - [Write UP](#write-up)
  - [Introduction](#introduction)
   - [Comment Ça Marche?](#comment-ça-marche)
     - [Pourquoi Utiliser l'Obfuscation?](#pourquoi-utiliser-lobfuscation)
  - [Solution Javascript - Obfuscation 3](#solution-javascript---obfuscation-3)
  - [Conclusion](#conclusion)


<!-- /TOC -->



_________

| ![Logo SC-900](/imgs/cefim.png) | ![Gato Hacker](/imgs/gato-hacker.webp) |
|----------|----------|


**Je ne pirate pas pour détruire, je pirate pour comprendre.**

_________
_________

## Introduction

- L'obfuscation en JavaScript est une technique utilisée pour rendre le code source difficile à lire et à comprendre. Cette méthode est souvent employée pour protéger le code contre le vol de propriété intellectuelle, les attaques malveillantes, ou simplement pour minimiser la taille du fichier dans les environnements de production.


_________

## Comment Ça Marche?

> L'obfuscation fonctionne en transformant le code JavaScript en une version équivalente mais beaucoup plus difficile à lire. Voici quelques techniques couramment utilisées :


- Renommage des Variables : Les noms de variables significatifs sont remplacés par des noms plus courts et sans signification, comme a, b, c, etc.
- Suppression des Espaces et des Commentaires : Tous les espaces blancs, les retours à la ligne et les commentaires sont supprimés pour rendre le code plus compact et difficile à lire.
- Encodage : Les chaînes de caractères et les valeurs numériques peuvent être encodées en utilisant des systèmes comme l'hexadécimal ou l'unicode.
- Réorganisation du Code : Le flux logique du code peut être réorganisé pour masquer sa structure d'origine.


### Pourquoi Utiliser l'Obfuscation?
- Protection de la Propriété Intellectuelle : Empêche les autres de comprendre et de réutiliser votre code sans autorisation.
- Sécurité : Rend plus difficile la tâche des attaquants cherchant à comprendre et exploiter des failles dans le code.
- Optimisation : Parfois, l'obfuscation peut réduire la taille du fichier, améliorant ainsi les temps de chargement.

Cependant, il est important de noter que l'obfuscation ne doit pas être considérée comme une solution de sécurité complète, mais plutôt comme une couche supplémentaire de protection. Les développeurs doivent toujours suivre les meilleures pratiques de sécurité en plus de l'obfuscation.

### Solution Javascript - Obfuscation 3
- Dès que vous ouvrez la page, une boîte de dialogue interactive apparaît et demande un mot de passe. Peu importe ce que vous entrez, le message "FAUX PASSWORD HAHA" apparaît.

| ![imagen 1](/imgs/Image1.png)

| ![imagen 2](/imgs/Image2.png)

- Ouvrez les outils de développement de votre navigateur En Firefox: Pulsa Ctrl+Shift+K,
- Allez dans l'onglet Débogueur et trouvez un fichier JavaScript nommé ch13.html. Dans ce fichier, il y a une fonction utilisée pour vérifier le mot de passe. Une analyse rapide montre que cette fonction renvoie toujours le message "FAUX PASSWORD HAHA", peu importe ce que vous entrez (la première ligne du code contient simplement les codes ASCII en base décimale de ce message, utilisés pour embrouiller).
- La clé se trouve dans la ligne suivante du code :
- String["fromCharCode"](dechiffre("\x35\x35\x2c\x35\x36\x2c\x35\x34\x2c\x37\x39\x2c\x31\x31\x35\x2c\x36\x39\x2c\x31\x31\x34\x2c\x31\x31\x36\x2c\x31\x30\x37\x2c\x34\x39\x2c\x35\x30"));


| ![imagen 3](/imgs/Image3.png)

- Cette ligne de code, bien qu'elle ne semble pas liée au reste, donne un indice : fromCharCode indique une décodage ASCII, et la chaîne suivante contient des nombres en hexadécimal.

- Avec l'aide de [UNPHP] (https://www.unphp.net/decode/), vous pouvez faire le décodage de l'hexadécimal au décimal.

- Après le décodage, vous obtenez une série de nombres décimaux et virgules :
       5 5 , 5 6 , 5 4 , 7 9 , 1 1 5 , 6 9 , 1 1 4 , 1 1 6 , 1 0 7 , 4 9 , 5 0
- Allez dans l'onglet Console et tapez :
      String.fromCharCode(55,56,54,79,115,69,114,116,107,49,50);

| ![imagen 4](/imgs/Image4.png)

- Apres touche dans exécuter et le flag sera dans l’ autre côte 

| ![imagen 5](/imgs/Image5.png)



### Conclusion
- La fonction String.fromCharCode en JavaScript est utilisée pour convertir des valeurs Unicode (ou des codes de caractères ASCII) en leurs caractères correspondants. Elle prend un ou plusieurs arguments numériques et renvoie une chaîne de texte formée par les caractères correspondant à ces valeurs.

- String.fromCharCode est un outil puissant pour convertir des codes de caractères numériques en texte lisible. Il est particulièrement utile dans les applications impliquant le déchiffrement de données codées, où les valeurs numériques représentent les caractères d'une chaîne.

# "La sécurité parfaite n'existe pas, seulement des défis perpétuels."
