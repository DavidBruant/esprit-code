<!--
    "Prendre une décision", c'est à dire, réagir à une situation qui invite à faire un choix

    2 définitions de "prendre une décision" :
    - l'une où on a écrit le code qui nous mène à cette décision nous-même
    - l'autre où l'on n'a pas écrit le code
-->

# La prise de décision de l'individu, vu comme du code

J'ai passé du temps à écouter et observer des humain.e.s\
Et j'ai passé du temps à créer des logiciels

La conjonction de ces 2 expériences a mené à une façon de penser la psychée humaine que j'essaye de partager ici


## Qu'est-ce que le "code" ?

Une manière de voir le code, c'est de penser à une recette de cuisine. Une suite d'instruction qui sont suivie à la lettre par la machine. Quand on change la recette, on a un résultat différent. Quand on applique la même recette 2 fois, on obtient le même résultat.

Il est probable que vous ayez déjà écrit des "formules Excel". Si c'est le cas, vous avez déjà écrit du code.

Le code permet aussi *d'écouter* des *évènements* et d'y *réagir* en appliquant une recette donnée (que l'on appelle une *fonction*)

### Réaction rose

Par exemple, le code suivant (en langage *JavaScript*) décrit que quand on clique sur un bouton, ce bouton devient rose :

```js
ajouterRéaction(bouton, 'clic', function(){
    bouton.style.backgroundColor = 'pink'
})
```

<!--
(désolé pour le mélange de français et d'anglais, JavaScript ne laisse pas le choix)
?
-->

Et on peut voir un bouton qui utilise ce code ici : 

<button>Je vais devenir rose</button>

<!--
Un jour, rendre le code interactif et proposer de changer le rose en une autre couleur
-->


### Réaction alternante

On peut compliquer le code pour que quand on clique à nouveau sur le bouton, il reprenne sa couleur initiale

```js
const couleur_initiale = 'grey';
bouton.style.backgroundColor = couleur_initiale; // initialisation de la couleur

ajouterRéaction(bouton, 'clic', function(){
    // si la couleur actuelle du bouton est la couleur initiale...
    if(bouton.style.backgroundColor === couleur_initiale) // alors...
        // changer la couleur en rose
        bouton.style.backgroundColor = 'pink'

    else // sinon (la couleur est déjà rose)
        // changer la couleur en le gris initial
        bouton.style.backgroundColor = 'grey'
})
```

Et le bouton correspondant :

<button>Je passe d'une couleur à l'autre</button>

Et en complexifiant le code, on pourrait créer des séquences plus complexe, comme:

**rose, jaune, gris,** rose, jaune, gris, rose, jaune, gris ...

ou 

**rose, gris, rose, gris, jaune,** rose, gris, rose, gris, jaune ...

ou même une séquence complètement aléatoire où on ne sait pas à l'avance sur quelle couleur on va tomber

Une fois que l'on sait le résultat que l'on souhaite obtenir, il suffit d'écrire le code correspondant


### Le dire avec des mots

On va changer un peu la configuration. Désormais, il va y avoir une zone où on écrira un texte et une zone qui va réagir à ce texte. Un peu comme si ce texte était envoyé comme un message.

On peut imaginer que la zone se colorise selon la couleur décrite par le message

```js
ajouterRéaction(zone, 'message', function(message){
    zone.style.backgroundColor = message
})
```

<input type="text" value="pink"/>

<!--
    input.value.trim()
-->

<output></output>

Il y a déjà écrit "pink", mais vous pouvez effacer et essayer "black" ou "grey" ou "chocolate" ou "purple" ou une autre couleur en anglais

Et un peu pareil, selon le message, on peut choisir de faire des choses différentes que changer la couleur. Par exemple, on pourrait dire que quand on écrit "grand", "moyen" ou "petit", ça change la taille de la zone

```js
ajouterRéaction(zone, 'message', function(message){
    // si le message est 'petit', 'moyen' ou 'grand'
    if(message === 'petit' || message === 'moyen' || message === 'grand') // alors...
        // changer la taille
        changerTaille(zone, message)
    
    else // sinon
        // changer la couleur
        zone.style.backgroundColor = message
})
```


### Ptèt c'est la même chose avec les gens

Si l'évènement, c'était genre un bisou sur la joue

Ptèt que ça peut générer de la gène et faire rougir...

```js
ajouterRéaction('bisou sur la joue', function(){
    rougir()
})
```

... ou ptèt mettre en colère et coller une gifle...


```js
ajouterRéaction('bisou sur la joue', function(){
    gifler()
})
```

... ou ptèt générer de la tendresse et retourner le bisou...


```js
ajouterRéaction('bisou sur la joue', function(){
    faireUnBisouSurLaJoue()
})
```

Mais la même réaction à chaque fois ?\
Sûrement que non

La réaction dépend généralement du contexte, comme qui a donné le bisou, dans quelle situation, etc.

<!--
    - mettre une réaction avec un if qui s'adapte au contexte
    - rajouter une visualisation avec des boutons sur ce qu'on peut faire à une personne et voir comment elle réagit
        - la personne et son code en-dessous

-->
