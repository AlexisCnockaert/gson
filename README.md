# PROJET PARTIE 2 GL

## RAPPORT ET EXPLICATIONS DES MODIFICATIONS

LIEN DU GIT : https://github.com/AlexisCnockaert/gson/tree/main/gson/src/test/java/com/google/gson/internal/bind

Commit 1 : https://github.com/google/gson/commit/1bfd2a0a94d849c85dfb2f7a8a1398c06a7bb120 : 
Le but ici etait de clarifier l'intention de la méthode avec l'ajout de stack.isEmpty pour montrer que l'on veut bien récupérer l'élément en haut de la pile, donc null si il n'existe pas. Comparé au début on comprend un peut mieux le but de la fonction en raison de la présentation des différents cas

Commit 2 : https://github.com/google/gson/commit/dc47fa0236e0e0bc11fed4c233a19048bbfd583e

Ici j'ai ajouter un test pertinent qui, à l'aide des méthodes liées aux tableaux json implémentées dans jsontreewriter, vérifie que la sortie finale du json n'est pas affectée si on essae d'écrire une valeur de niveau supérieur dans un TABLEAU Json sans qu'elle soit dans un objet au préalable. Ce test reprend la logique d'un test déja présent dans la classe de test mais l'applique ici pour les tableaux json afin de vérifier que chaque aspect du comportement de la classe JsonTreeWriter est testé séparèment l'un de l'autre.

Commit 3 : https://github.com/google/gson/commit/daf241863b2e88a6c6d11ab0e65f6615740af758

Il s'agit ici d'une petite modificaiton permettant de mieux comprendre l'intention du code : pour la variable retournée product qui devient jsonElement (assez explicite) et le rennomage de la méthode name en writeFieldName : Le nom writeFieldName indique clairement que cette méthode est utilisée pour écrire un nom de champ dans un objet JSON. Cela rend son intention plus évidente par rapport à simplement name.
Par convention de nommage cohérente, on pourrait aussi renommer les méthodes "value" en "writeValue". Ce changement implique aussi de renommer les méthodes de bases venant de la classe parent JsonWriter.

Commit 4 : https://github.com/google/gson/commit/b47d21ad12efd36c7cbecfcff764d2ec0ba75e3d

Ici on s'attaque a la classe principale gson, étant déja dotée d'une methode newbuilder permettant de créer un gson avec la configuration actuelle de la classe, j'ai rajouter deux méthodes create permettant de créer un gson avec une config par défaut et un gson avec la config passée en paramètre, permettant une création plus large et prècise.
Cette modification rend la situation résultante meileure qu'avant, offrant une meilleure lisibilité et facilité à utiliser la classe (qui est la principale ici).

