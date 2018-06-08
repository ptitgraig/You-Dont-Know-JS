# You Don't Know JS: Démarrage
# Chapter 1: Dans la programmation

Bienvenue dans la serie *You Don't Know JS* (*YDKJS*).

*Mettre le pied a l'étrier* est un introduction à plusieurs concepts de base de la programmation -- nous nous penchons bien-sûr, sur JavaScript plus spécificquement (souvent appelé JS) -- et à comment approcher et comprendre le reste des livres de cette série. Si vous démarrez avec la programmation et/ou JavaScript, ce livre explorera ce que vous avez besoin de savoir pour *mettre le pied a l'étrier*

Ce livre commence par expliquer globalement les principes de base de la programmation. Il est utile si vous démarrez *YDKJS* avec peu ou aucune expérience de la programmation, et si vous cherchez a ce que ces livres vous aides a comprendre la programmation au travers de JavaScript.

L'approche du chapître 1 se veut être un aperçu des choses que vous voudrez apprendre et des choses à mettre en pratique *dans la programmation*. Il existe aussi d'autres resources de très bonne qualité qui peuvent vous aider à creuser d'avantage ces sujets, je vous encourage à apprendre d'elles en plus de ce chapître.

Une fois à l'aise avec les bases générales de la programmation, le Chapître 2 va vous guidez dans la familiarisation avec la façon de programmer avec JavaScript. Le Chapître 2 est une introduction à ce qu'est JavaScript, mais une fois de plus, il ne s'agit pas d'un guide exhaustif -- c'est la raison pourquoi il existe d'autres livres *YDKJS* !

Si vous êtes déjà plutôt à l'aise avec JavaScript, dirigez-vous vers le Chapître 3 en premier lieu afin d'avoir de jeter un oeil sur quoi attendre de *YDKJS*, puis allez-y!

## Code

Commençons avec le commencement.

Un programme, souvent appelé *code source* ou juste *code*, est un ensemble d'instructions spéciales qui disent à l'ordinateur quelles sont les tâches à executer. D'habitude, le code est suavegardé dans un fichier texte, bien qu'avec JavaScript vous puissiez saisir du code directement dans une console de développement navigateur, ce que nous couvrirons sous peu.

L'ensemble des règles de formattage valide et de combinaisons d'instructions est appelé un *langage informatique*, parfois appelé *syntaxe*, très comparable à ce que la langue Anglaise définie comment épellé les mots et comment créer une phrase valide utilisant des mots et de la ponctutaion.

### Déclarations

Dans une langage informatique, un groupe de mots, nombres et opérateurs qui execute une tâche spécifique est une *déclaration*. En JavaScript, une déclaration peut ressemler à ce qi suit :

```js
a = b * 2;
```

Les caracteres `a` et `b` sont appelés *variables* (voir "Variables"), qui sont de simples boîtes dans lesquelles vous pouvez stocker ce que vous voulez. Dans un programme, les variables contiennent des valeurs (comme le nombre `42`) qui vont être utilisées par le programme. Voyez-les comme de conteneurs symboliques pour les valeurs elles-meme.

En comparaison, le `2` est juste une valeur, appelée une *valeur literale*, parcequ'elle est seule et n'est pas stockée dans une variable.

Les caractères `=` et `*` sont des *opérateurs* (voir "Opérateurs") -- ils accomplissent des actions avec les valeurs et variables telles que l'affectation et la multiplication.

La plupart des déclarations en JavaScript se termine avec un point-virgule(`;`).

La déclaration `a = b * 2;` dit à l'ordinateur, en gros, de prendre la valeur stockée dans la variable `b`, de multiplier cette valeur par `2`, et ensuite de stocker le résultat dans une autre variable qu'on a apelle `a`.

Les programmes sont juste une collections de plusieurs déclarations comme celles-ci, qui ensemble, décrivent toutes les étapes necessaires pour atteindre le but visé par le programme.

### Expressions

Les déclarations sont faites d'une ou plusieurs *expressions*. Une expression représente n'importe qu'elle réfèrence à une variable ou valeur ou a un ensemble de variable(s) et valeur(s) combinées à des opérateurs.

Par exemple:

```js
a = b * 2;
```

Cette déclaration contient quatre expressions:

* `2` est une *expression de valeur literale*
* `b` est une *expression de variable*, qui a pour intention de retrouver sa valeur actuelle
* `b * 2` is an *expression arithmetique*, qui a pour intention d'effectuer la multiplication
* `a = b * 2` is an *expression d'affectation*, qui a pour intention d'affecter le résultat de l'expression `b * 2` à la variable `a` (d'avantage d'affectations plus tard)

Une expression générale qui est seule est appelé également *déclaration d'expression*, comme par exemple:

```js
b * 2;
```

Cette forme de déclaration d'expression n'est pas très fréquente ou utile, en général elle n'aura aucun effet sur l'execution du programme --  elle rechercherait la valeur de `b` et la multiplierait par `2`, mais ne ferait rien avec le résultat.

Une déclaration d'expression plus commune est un *appel de déclaration d'expression (voir "Fonctions")*, car l'intégralité de la déclaration est l'expression d'appel à la fonction elle-même:

```js
alert( a );
```

### Exécuter un programme

Comment est ce que ces collections de déclarations de programmation disent à l'ordinateur que faire ? Le programme a besoin d'être *exécuté*, chose qu'on apelle aussi *lancer un programme*.


Les déclarations telles que `a = b * 2` sont utiles pour les développeurs quand ils lisnet ou écrivent, mais ne sont pas directement sous une forme compréhensible par l'ordinateur. Ainsi donc, un utilitaire spécial est utilisé (soit un *intepreteur* ou un *compileur*) pour traduire le code que vous écrivez en commandes compréhensible par un oridnateur.

Pour quelques langage informatique, cette traduction de commandes est faite de bas en haut, ligne par ligne, chaque fois que le programme est lancé, ce qui est apellé usuallement *intepréter le code*.

Pour d'autres langages, la traduction est faite en avance de phase, on apelle ça la *compilation* de code, donc quand un programme se *lance* plus tard, ce qui est exécuté est en fait les instructions déjà compilées par l'ordinateur prêtes à l'emploi.

On affirme d'habitude que JavaScipt est *interprété*, parceque votre code source JavaScript est traité à chaque fois qu'il est lancé. Mais ce n'est tout à fait précis. En fait, le moteur JavaScript *comile* le program à la volée puis lance le code compilé immédiatement.

**Note:** Pour plus d'informations sur la compilation JavaScript, voir les eux premiers chapître de *Portées et Fermetures* de cette série.


## A vous d'essayer

Ce chapître va vous introduire à chaque concept de programmation en utilisant un bout de code, tout écrit en JavaScript (évidemment !).

Je ne le soulignerais jamais assez : alors que vous parcourez ce chapître -- il est possible que vous le parcourirez plusieurs fois -- je vous conseil de mettre en pratique chacun de ces concepts en écrivant le code vous-même. La plus simple manière de faire cela est d'ouvrir la console pour développeur dans le navigateur de votre choix (Firefox, Chrome, IE, etc.).

**Astuce :** Vous pouvez lancer la console pour développeur avec un raccourci clavier ou à partir du menu. Pour plus d'informations sur le démarrage et l'utilisation de la console dans votre navigateur préféré, voir "Maîtrise La Console d'Outils pour Développeurs" (http://blog.teamtreehouse.com/mastering-developer-tools-console). Afin de saisir plusieurs lines dans la console en une seule fois, utilisez `<shift> + <enter>` pour aller à ala ligne. Une fois que vous tappez `<entrée>`, la console va exécuter tout ce que vous avez saisi.

Familiarisons-nous avec l'action de lancer du code dans la console. Premièrement, je suggère d'ouvrir un onglet vide dans votre navigateur. Je préfère faire cela en tappant `about:blank` dans la barre d'adresse. Ensuite, assurez-vous que votre console pour dévelppeur est ouverte, comme je viens de le mentionner.

Maintenant, tappez ce code est voyez comment il s'exécute:

```js
a = 21;

b = a * 2;

console.log( b );
```

Ecrire le code précédent dans la console de Chrome devrait produire quelque chose comme ça:

<img src="fig1.png" width="500">

Allez-y, essayez. La meilleur manière d'apprednre la programmation est de commencer à programmer!

### Sortie

Dans le bout de code précédent, nous avons utilisé `console.log(..)`. Brièvement, regardons ce que signifie cette ligne de code.

Vous l'avez sûrement deviné, mais c'est ainsi que nous affichons le texte (ou aussi *afficher* le texte à l'utilisateur) dans la console pour développeur. Il y a deux caractéristiques de cette déclaration que nous devrions expliquer.

Premièrement, lq partie `log( b )` est apellé une appel de fonction (voir "Fonctions"). Ce qui se passe ici, c'est que nous passons la variable `b`  à cette fonction, laquelle prend la valeur de `b` et l'affiche dans la console.

Deuxièmement, la partie `console.` est une référence à un objet dans lequel se trouve la fonction `log(...)`. Nous couvrirons les objets et leurs propriétés plsus en détails dans le Chapître 2.

Une autre manière d'afficher quelque chose de visible est de lancer une déclaration de type `alert(..)`. Par exemple :

```js
alert( b );
```

Si vous lancez ça, vous remarquerez qu'au lieu d'afficher la sortie dans la console, il s'affiche une boîte popup "OK" qui contient la valeur de la variable `b`. Cela étant dit, l'utilisation de `console.log(...)` va généralement rendre votre apprentissage de la programmation et l'execution de vos programmes plus simple que l'utilisation de `alert(..)`, car vous pouvez afficher plusieurs valeurs à la fois dans interrompre l'interface du navigateur.

Dans ce livre, nous utiliserons `console.log(..)` comme méthode d'affichage.

### Entrée

Alors que nous parlons de Sortie, vous vous posez peut-être la question de l'Entrée (c'est à dire recevoir des informations provenant de l'utilisateur).

La façon la plus fréquente pour obtenir cela est par le biais de page HTML qui montrent à l'utilisateur des élèments de formulaire (comme des boîtes de texte) dans lesquelles il peut saisir des valeurs, puis nous utilisons le JS pour lire ces valeurs et les utilisées dans les variables de notre programme.

Mais il existe une manière plus simple d'obtenir une entrée utilisateur. Et dans une soucis de simplifier l'apprentissage et à des fins de démonstration, c'est cette méthode que nous utiliserons tout au long de ce livre. La fonction `prompt(..)`:

```js
age = prompt( "Quel âge avez-vous:" );

console.log( age );
```

Comme vous l'avez probablement deviner, le message que vous passez à `prompt(..)` -- dans le cas présent `"Quel âge avez-vous:"` -- est affiché dans la popup.

Ca devrait ressemble à ceci:

<img src="fig2.png" width="500">

Une fois que vous avez soumis le texte saisi en cliquant sur "OK", vous remarquerez que la valeur que vous avez saisie est stockée dans la variable `age`, que nous affichons en *sortie* avec `console.log(..)` :

<img src="fig3.png" width="500">

Afin de garder les choses le plus simple possible lors de notre apprentissage des concepts de bases de la programmation, les exemples de ce livre ne requiert pas de sasie. Mais maintenant que vous avez vu comment utiliser `prompt(...)`, si vous voulez, vous pouvez vous mettre au défi d'essayer d'utiliser les méthodes de saisie d'Entrée dans votre exploration des exemples.

## Opérateurs

Les opérateurs sont comment nous exécutons des actions sur des variables et valeurs. Nous avons déjà vu deux opérateurs, le `=` et le `*`.

L'opérateur `*` exécute une multiplication. Simple non ?

L'opérateur `=` est utilisé pour l'*affectation* -- nous calculons premièrement la valeur à *droite* (la valeur source) de `=` et ensuite nous la placons dans la variable que nous spécifions à gauche (variable cible).

**Attention** Cette façon de specifier une déclaration à l'envers peut sembler étrange. Au lieu de `a = 42`, certains préférent changer l'ordre de manière à ce que la valeur source soit à gauche et la variable cible à droite, comme `42 -> a` (ce n'est pas du JavaScript valide !). Malheureusement, la forme ordonnée comme `a = 42`, et autres variations similaires, est relativement prévalante dans les langages de programmation mordernes. C'est quelque peu non-naturel, passez simplement un peu de temps à repasser cet ordre dans votre tête afin de vous y habituer.

Considérez:

```js
a = 2;
b = a + 1;
```

Ici , nous affectons la valeur `2` à la variable `a`. Ensuite, nous prenons la valeur de la variable `a` (toujours `2`), y ajoutons `1`, résultant à la valeur `3`, puis stockons cette valeur dans la variable `b`.

Bien que le mot-clé `var` ne soit pas,techniquement, un opérateur, vous en aurez besoin dans tous vos programmes; car c'est la principale façcon de *déclarer* (ou *créer*) des *var*iables (voir "Variables").

Vous devriez toujours déclarer le nom de la variable avant de l'utiliser vous l'utilisiez. Mais vous n'avez besoin de déclarer qu'une seule fois une variable par *portée* (voir "Portée"); après ça, elle peut-être utilisé autant de fois que nécessaires. Par exemple :

```js
var a = 20;

a = a + 1;
a = a * 2;

console.log( a );	// 42
```

Voici quelqu'uns des opérateurs les plus communs en JavaScript :

* Affectation: `=` comme dans `a = 2`
* Math: `+` (addition), `-` (soustraction), `*` (multiplication), et `/` (division), comme dans `a * 3`.
* Affectation composée: `+=`, `-=`, `*=`, et `/=` sont des opérateurs composés qui combinent une opération mathématique avec une affectation, comme dans `a += 2` (pareil avec `a = a + 2`).
* Incrementation/Decrementation: `++` (incrementation), `--` (decrementation), comme dans `a++` (similaire à `a = a + 1`).
* Accès aux Propriétés d'un Objet: `.` comme dans `console.log()`.

   Les objets sont des valeurs qui contiennent d'autres valeurs à des endroits qui portent un nom spécifique appelés propriétés. `obj.a` signifie qu'il y a un objet `obj` avec une propriété nommée `a`. On peut aussi accéder à une propriété par `obj["a"]`. Voir Chapître 2.
* Egalité: `==` (égalité-faible), `===` (égalité-stricte), `!=` (inégalité-faible), `!==` (inégalité-stricte), comme dans `a == b`.

   Voir "Valeurs & Types" dans le Chapître 2.
* Comparaison: `<` (inférieur à), `>` (supérieur à), `<=` (inférieur à ou égalité-faible), `>=` (supérieur à ou égalité-faible), comme dans `a <= b`.

   Voir "Valeurs & Types" dans le Chapître 2.
* Logique: `&&` (et), `||` (ou), comme dans `a || b` qui selectionne soit `a` *ou* `b`.

   Ces opérateurs sont utilisés pour exprimer des conditions composées (voir "Conditions"), comme soit `a` *ou* `b` est vrai (true).

**Remarque:** Pour beaucoup plus de détails et couverture des opérateurs non-mentionnés ici, voir le Mozilla Developer Network (MDN)'s "Expressions and Operators" (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators).

## Valeurs et Types

Si vous demandez à un employé d'un magasin de téléphone combien coûte un certain téléphone, et qu'il vous réponde "quatre-vingt-dix-neuf, quatre-vingt-dix-neuf" (99,99 EUR), il vous donne un véritable nombre en euro qui représente ce que vous aurez besoin de payer pour l'acheter. Si vous vouslez acheter deux examplaires de ce model, vous pouvez facilement faire un calcul mental pour doubler cette valeur et obtenir 199.98 EUR.

Si ce même employé choisi un autre model similaire mais dit "c'est gratuit" (peut-être en faisant signe de guillement avec ses doigts), il ne vous donne pas un nombre, mais une autre représentation du prix attendu (0.00 EUR) -- le mot "gratuit".

Quand plus tard vous demandez si le téléphone inclut un chargeur, cette réponse ne peut être que "oui" ou "non".

De façon très similaire, quand vous exprimez des valeurs dans une programme, vous choisissez différentes représentations pour ces valeurs, basé sur ce que vous plannifiez de faire avec elles.

Dans la terminologie de programmation, ces différentes représentations de valeurs sont apellées *types*. JavaScript possède des types encastrés pour chacune de ces soit-disantes valeurs *primitives*

* Quand vous faites des maths, vous voulez un `number` (nombre).
* Quand vous affichez une valeur sur l'écran, vous avez besoin d'une `string` (un ou plusieurs caractère, mots, phrases).
* Quand vous avez besoin de prendre une décision dans votre programme, vous avez besoin d'un `booleen` (`true` ou `false` -- `vrai` ou `faux`).

Les valeurs qui sont inclusent directement dans le code source sont appelées *litérales*. Les litérales de type `string` sont encerclées par des guillemets double `"..."` ou des guillements simples (`'...'`) -- la seule différence est stylistique. Les litérales `number` et `boolean` sont présentéss telles quelle (c'est à dire `42`, `true`, etc.).

Considérer:

```js
"I am a string";
'I am also a string';

42;

true;
false;
```

Au delà des types de valeur `string`/`number`/`boolean` value types, il est commun pour un langage de programmation de fournir des *arrays* (tableau), *objects* (objets), *functions* (fonctions), et plus encore. Nous couvrirons d'avantage le sujet des valeurs et des types tout au long de ce chapître et du prochain.

### Conversion entre types

Si vous avez un `number` mais que vous avez besoin de l'afficher à l'écran, il faudra convertir la valeur en `string`, et en JavaScript cette conversion est appelé "coercion" (coercition ou contrainte). De la même manière, si quelqu'un saisi une série de caractères numériques dans un formulaire sur un site e-commerce, on a affaire à une `string`, mais si vous avez ensuite besoin d'utiliser cette valeur pour faire des opération mathématiques, vous devez la "contraindre" ou "coercer" à un nombre.

JavaScript fourni plusieurs outils pour forcer une coercition entre *types*. Par exemple :

```js
var a = "42";
var b = Number( a );

console.log( a );	// "42"
console.log( b );	// 42
```

Using `Number(..)` (a built-in function) as shown is an *explicit* coercion from any other type to the `number` type. That should be pretty straightforward.

Ici, l'utilisation de `Number(..)` (une fonction encastrée) est un exemple de coercition *explicite* de n'importe quel type vers le type `number`. C'est plutôt simple et direct.

Cependant, la comparaison deux valeurs qui ne sont pas du même type, qui implique une *coercition* implicite, est une sujet controversé.

Lorsqu'on compare la `string` `"99.99"` au nombre `99.99`, la plupart des gens dirait qu'ils sont équivalent. Mais ils ne sont pas exactement identiques, n'est pas ? C'est la même valeir sous deux représentations différentes, deux différents *types*. On pourrait dire qu'ils sont "faiblement égales" ?

Pour vous aider dans ces fréquentes situations, JavaScript va parfois coercer *implicitement* les valeurs vers les types correspondants. 

Donc si on utilise l'opérateur de faible égalité `==` pour faire la comparaison `"99.99" == 99.99`, JavaScript va convertir le `"99.99"` de gauche en son équivalment numérique (`number`) `99.99`. La comparaison devient donc `99.99 == 99.99`, qui est bien sur vraie `true`.

Bien que conçue pour vous aidez, la coercition implicite peut être source de confusion si vous n'avez pas pris le temps d'apprendre les règles qui gouvernent son comportement. La plupart des développeurs JS ne l'ont jamais pris, ainsi le sentiment général est que la coercition implicite est belle et bien source de confusion et endommage le programme par la présence de bugs innatentus, et donc devrait être éviter. Cela a même parfois été appelé un défaut de conception du langage.

Cependant, la coercition implicite est une mécanique qui *peut être apprise*, et de surcroit *devrait être apprise* par quiconque souhaitant sérieusement programmer en JavaScript. Non seulement, le sentiment de confusion se dissipe une fois les règles apprises, mais elle peut améliorer vos programmes ! L'effort vaut le coup.

**Remarque:** Pour plus d'informations sur la coercition, voir le Chapître 2 de ce titre et le Chapître 4 du titre *Types & Grammaire* de cette série.

## Commentaires de code

Il se peut que l'employé du magasin de téléphone prennent quelques notes au sujet des caractéristiques d'un nouveau téléphone ou au sujet des nouvelles offres de son entreprise.
Ces notes sont seulement pour les employés -- elles n'ont pas pour but d'être lues par les clients. Néanmoins, ces notes aident les employés à fournir un meilleur travail en documentant les comments et pourquois de ce qu'ils devraient dire aux clients.

Une des leçons les plus importantes sur l'écriture de code est que le code n'est pas uniquement écrit pour l'ordinateur. Le code est tout autant, si ce n'est plus, pour le développeur que pour l'ordinateur.

Votre ordinateur ne se préoccupe que du code machine, une suite de 0s et 1s binaires, qui proviennent de la *compilation*. Vous pourriez écrire un quantité quasi infinie de programmes qui finiraient dans la même série de 0s et de 1s. Les choix que vous faites sur la manière d'écrire votre programme ont de l'importance -- non seulement pour vous, mais aussi pour les membres de votre équipe et même pour votre futur-vous.

Vous devriez vous efforcer non seulement d'écrire des programmes qui fonctionnent, mais des programmes qui sont claires quand examinés. Vous pouvez allez loin dans cet effort en choisissant de bons noms pour vos variables (voir "Variables") et fonctions (voir "Functions).

Mais une autre part importante est le commentaire de code. Il s'agit de morceaux de textes dans votre programme qui sont ajoutés purement pour expliquer les choses à un être-humain. L'interpreteur/compilateur ignorera toujours ces commentaires.

Il existe des tas d'opinions sur ce qu'est un code bien commenté; nous ne pouvons pas définir des règles absolues et universelles. Mais il y a  quelques observations et lignes directrices qui se révèlent assez utiles:

* Du code sans commentaires est sous-optimal.
* Trop de commenataires (un par ligne, par exemple) est probablement le signe d'un code mal écrit.
* Les commentaires devraient expliquer le *pourquoi*, non pas le *comment*. Ils peuvent occasionnellement expliquer le *comment* si le code est particulièrement déroutant.

En JavaScript, il y a deux types de commentaires possibles : les commentaires mono-ligne et les multi-lignes.

Considérez:

```js
// Ceci est un commentaire mono-ligne

/* Mais celui-çi
       est un commentaire
             multi-ligne.
                      */
```

Le commentaire mono-ligne `//` est approprié si vous allez mettre un commentaire au-dessus d'une seule déclaration, ou-bien en fin de ligne.
Tout ce qui suit `//` sur la ligne est traité comme commentaire (et ainsi ignoré par le compilateur), et ce jusqu'en fin de ligne. Il n'y a pas de restriction sur ce qui peut être écrit dans un commentaire mono-ligne.

Considérez:

```js
var a = 42;		// 42 is the meaning of life
```

Le commentaire multi-ligne `/* .. */` est approprié si vous avez plusieurs lignes d'explication qui en valent la peine dans votre commentaire.

Voici un usage courant de commentaire multi-ligne :

```js
/* La valeur suivante est utilisée parceque
   il a été montré qu'elle répond à
   toutes les questions de l'univers. */
var a = 42;
```

On peut aussi le mettre n'importe où sur une ligne, même au milieu parceque `*/` termine le commentaire. Par exemple :

```js
var a = /* valeur artbitraire */ 42;

console.log( a );	// 42
```

La seule chose que ne peux pas apparaître dans un commentaire multi-ligne est le `*/` parcequ'il serait intérpreté comme fin de commentaire.

Il est définitivement conseillé de commencer votre apprentissage de la programmation en prenant l'habitude de commenter votre code. Tout au long du reste de ce chapître, vous verez que j'utilise des commentaires pour expliquer les choses, ainsi donc, faites la même chose lors de votre mise en pratique. Croyez-moi, quiconque lira votre code vous remerciera !

## Variables

Most useful programs need to track a value as it changes over the course of the program, undergoing different operations as called for by your program's intended tasks.

The easiest way to go about that in your program is to assign a value to a symbolic container, called a *variable* -- so called because the value in this container can *vary* over time as needed.

In some programming languages, you declare a variable (container) to hold a specific type of value, such as `number` or `string`. *Static typing*, otherwise known as *type enforcement*, is typically cited as a benefit for program correctness by preventing unintended value conversions.

Other languages emphasize types for values instead of variables. *Weak typing*, otherwise known as *dynamic typing*, allows a variable to hold any type of value at any time. It's typically cited as a benefit for program flexibility by allowing a single variable to represent a value no matter what type form that value may take at any given moment in the program's logic flow.

JavaScript uses the latter approach, *dynamic typing*, meaning variables can hold values of any *type* without any *type* enforcement.

As mentioned earlier, we declare a variable using the `var` statement -- notice there's no other *type* information in the declaration. Consider this simple program:

```js
var amount = 99.99;

amount = amount * 2;

console.log( amount );		// 199.98

// convert `amount` to a string, and
// add "$" on the beginning
amount = "$" + String( amount );

console.log( amount );		// "$199.98"
```

The `amount` variable starts out holding the number `99.99`, and then holds the `number` result of `amount * 2`, which is `199.98`.

The first `console.log(..)` command has to *implicitly* coerce that `number` value to a `string` to print it out.

Then the statement `amount = "$" + String(amount)` *explicitly* coerces the `199.98` value to a `string` and adds a `"$"` character to the beginning. At this point, `amount` now holds the `string` value `"$199.98"`, so the second `console.log(..)` statement doesn't need to do any coercion to print it out.

JavaScript developers will note the flexibility of using the `amount` variable for each of the `99.99`, `199.98`, and the `"$199.98"` values. Static-typing enthusiasts would prefer a separate variable like `amountStr` to hold the final `"$199.98"` representation of the value, because it's a different type.

Either way, you'll note that `amount` holds a running value that changes over the course of the program, illustrating the primary purpose of variables: managing program *state*.

In other words, *state* is tracking the changes to values as your program runs.

Another common usage of variables is for centralizing value setting. This is more typically called *constants*, when you declare a variable with a value and intend for that value to *not change* throughout the program.

You declare these *constants*, often at the top of a program, so that it's convenient for you to have one place to go to alter a value if you need to. By convention, JavaScript variables as constants are usually capitalized, with underscores `_` between multiple words.

Here's a silly example:

```js
var TAX_RATE = 0.08;	// 8% sales tax

var amount = 99.99;

amount = amount * 2;

amount = amount + (amount * TAX_RATE);

console.log( amount );				// 215.9784
console.log( amount.toFixed( 2 ) );	// "215.98"
```

**Note:** Similar to how `console.log(..)` is a function `log(..)` accessed as an object property on the `console` value, `toFixed(..)` here is a function that can be accessed on `number` values. JavaScript `number`s aren't automatically formatted for dollars -- the engine doesn't know what your intent is and there's no type for currency. `toFixed(..)` lets us specify how many decimal places we'd like the `number` rounded to, and it produces the `string` as necessary.

The `TAX_RATE` variable is only *constant* by convention -- there's nothing special in this program that prevents it from being changed. But if the city raises the sales tax rate to 9%, we can still easily update our program by setting the `TAX_RATE` assigned value to `0.09` in one place, instead of finding many occurrences of the value `0.08` strewn throughout the program and updating all of them.

The newest version of JavaScript at the time of this writing (commonly called "ES6") includes a new way to declare *constants*, by using `const` instead of `var`:

```js
// as of ES6:
const TAX_RATE = 0.08;

var amount = 99.99;

// ..
```

Constants are useful just like variables with unchanged values, except that constants also prevent accidentally changing value somewhere else after the initial setting. If you tried to assign any different value to `TAX_RATE` after that first declaration, your program would reject the change (and in strict mode, fail with an error -- see "Strict Mode" in Chapter 2).

By the way, that kind of "protection" against mistakes is similar to the static-typing type enforcement, so you can see why static types in other languages can be attractive!

**Note:** For more information about how different values in variables can be used in your programs, see the *Types & Grammar* title of this series.

## Blocks

The phone store employee must go through a series of steps to complete the checkout as you buy your new phone.

Similarly, in code we often need to group a series of statements together, which we often call a *block*. In JavaScript, a block is defined by wrapping one or more statements inside a curly-brace pair `{ .. }`. Consider:

```js
var amount = 99.99;

// a general block
{
	amount = amount * 2;
	console.log( amount );	// 199.98
}
```

This kind of standalone `{ .. }` general block is valid, but isn't as commonly seen in JS programs. Typically, blocks are attached to some other control statement, such as an `if` statement (see "Conditionals") or a loop (see "Loops"). For example:

```js
var amount = 99.99;

// is amount big enough?
if (amount > 10) {			// <-- block attached to `if`
	amount = amount * 2;
	console.log( amount );	// 199.98
}
```

We'll explain `if` statements in the next section, but as you can see, the `{ .. }` block with its two statements is attached to `if (amount > 10)`; the statements inside the block will only be processed if the conditional passes.

**Note:** Unlike most other statements like `console.log(amount);`, a block statement does not need a semicolon (`;`) to conclude it.

## Conditionals

"Do you want to add on the extra screen protectors to your purchase, for $9.99?" The helpful phone store employee has asked you to make a decision. And you may need to first consult the current *state* of your wallet or bank account to answer that question. But obviously, this is just a simple "yes or no" question.

There are quite a few ways we can express *conditionals* (aka decisions) in our programs.

The most common one is the `if` statement. Essentially, you're saying, "*If* this condition is true, do the following...". For example:

```js
var bank_balance = 302.13;
var amount = 99.99;

if (amount < bank_balance) {
	console.log( "I want to buy this phone!" );
}
```

The `if` statement requires an expression in between the parentheses `( )` that can be treated as either `true` or `false`. In this program, we provided the expression `amount < bank_balance`, which indeed will either evaluate to `true` or `false` depending on the amount in the `bank_balance` variable.

You can even provide an alternative if the condition isn't true, called an `else` clause. Consider:

```js
const ACCESSORY_PRICE = 9.99;

var bank_balance = 302.13;
var amount = 99.99;

amount = amount * 2;

// can we afford the extra purchase?
if ( amount < bank_balance ) {
	console.log( "I'll take the accessory!" );
	amount = amount + ACCESSORY_PRICE;
}
// otherwise:
else {
	console.log( "No, thanks." );
}
```

Here, if `amount < bank_balance` is `true`, we'll print out `"I'll take the accessory!"` and add the `9.99` to our `amount` variable. Otherwise, the `else` clause says we'll just politely respond with `"No, thanks."` and leave `amount` unchanged.

As we discussed in "Values & Types" earlier, values that aren't already of an expected type are often coerced to that type. The `if` statement expects a `boolean`, but if you pass it something that's not already `boolean`, coercion will occur.

JavaScript defines a list of specific values that are considered "falsy" because when coerced to a `boolean`, they become `false` -- these include values like `0` and `""`. Any other value not on the "falsy" list is automatically "truthy" -- when coerced to a `boolean` they become `true`. Truthy values include things like `99.99` and `"free"`. See "Truthy & Falsy" in Chapter 2 for more information.

*Conditionals* exist in other forms besides the `if`. For example, the `switch` statement can be used as a shorthand for a series of `if..else` statements (see Chapter 2). Loops (see "Loops") use a *conditional* to determine if the loop should keep going or stop.

**Note:** For deeper information about the coercions that can occur implicitly in the test expressions of *conditionals*, see Chapter 4 of the *Types & Grammar* title of this series.

## Loops

During busy times, there's a waiting list for customers who need to speak to the phone store employee. While there's still people on that list, she just needs to keep serving the next customer.

Repeating a set of actions until a certain condition fails -- in other words, repeating only while the condition holds -- is the job of programming loops; loops can take different forms, but they all satisfy this basic behavior.

A loop includes the test condition as well as a block (typically as `{ .. }`). Each time the loop block executes, that's called an *iteration*.

For example, the `while` loop and the `do..while` loop forms illustrate the concept of repeating a block of statements until a condition no longer evaluates to `true`:

```js
while (numOfCustomers > 0) {
	console.log( "How may I help you?" );

	// help the customer...

	numOfCustomers = numOfCustomers - 1;
}

// versus:

do {
	console.log( "How may I help you?" );

	// help the customer...

	numOfCustomers = numOfCustomers - 1;
} while (numOfCustomers > 0);
```

The only practical difference between these loops is whether the conditional is tested before the first iteration (`while`) or after the first iteration (`do..while`).

In either form, if the conditional tests as `false`, the next iteration will not run. That means if the condition is initially `false`, a `while` loop will never run, but a `do..while` loop will run just the first time.

Sometimes you are looping for the intended purpose of counting a certain set of numbers, like from `0` to `9` (ten numbers). You can do that by setting a loop iteration variable like `i` at value `0` and incrementing it by `1` each iteration.

**Warning:** For a variety of historical reasons, programming languages almost always count things in a zero-based fashion, meaning starting with `0` instead of `1`. If you're not familiar with that mode of thinking, it can be quite confusing at first. Take some time to practice counting starting with `0` to become more comfortable with it!

The conditional is tested on each iteration, much as if there is an implied `if` statement inside the loop.

We can use JavaScript's `break` statement to stop a loop. Also, we can observe that it's awfully easy to create a loop that would otherwise run forever without a `break`ing mechanism.

Let's illustrate:

```js
var i = 0;

// a `while..true` loop would run forever, right?
while (true) {
	// stop the loop?
	if ((i <= 9) === false) {
		break;
	}

	console.log( i );
	i = i + 1;
}
// 0 1 2 3 4 5 6 7 8 9
```

**Warning:** This is not necessarily a practical form you'd want to use for your loops. It's presented here for illustration purposes only.

While a `while` (or `do..while`) can accomplish the task manually, there's another syntactic form called a `for` loop for just that purpose:

```js
for (var i = 0; i <= 9; i = i + 1) {
	console.log( i );
}
// 0 1 2 3 4 5 6 7 8 9
```

As you can see, in both cases the conditional `i <= 9` is `true` for the first 10 iterations (`i` of values `0` through `9`) of either loop form, but becomes `false` once `i` is value `10`.

The `for` loop has three clauses: the initialization clause (`var i=0`), the conditional test clause (`i <= 9`), and the update clause (`i = i + 1`). So if you're going to do counting with your loop iterations, `for` is a more compact and often easier form to understand and write.

There are other specialized loop forms that are intended to iterate over specific values, such as the properties of an object (see Chapter 2) where the implied conditional test is just whether all the properties have been processed. The "loop until a condition fails" concept holds no matter what the form of the loop.

## Functions

The phone store employee probably doesn't carry around a calculator to figure out the taxes and final purchase amount. That's a task she needs to define once and reuse over and over again. Odds are, the company has a checkout register (computer, tablet, etc.) with those "functions" built in.

Similarly, your program will almost certainly want to break up the code's tasks into reusable pieces, instead of repeatedly repeating yourself repetitiously (pun intended!). The way to do this is to define a `function`.

A function is generally a named section of code that can be "called" by name, and the code inside it will be run each time. Consider:

```js
function printAmount() {
	console.log( amount.toFixed( 2 ) );
}

var amount = 99.99;

printAmount(); // "99.99"

amount = amount * 2;

printAmount(); // "199.98"
```

Functions can optionally take arguments (aka parameters) -- values you pass in. And they can also optionally return a value back.

```js
function printAmount(amt) {
	console.log( amt.toFixed( 2 ) );
}

function formatAmount() {
	return "$" + amount.toFixed( 2 );
}

var amount = 99.99;

printAmount( amount * 2 );		// "199.98"

amount = formatAmount();
console.log( amount );			// "$99.99"
```

The function `printAmount(..)` takes a parameter that we call `amt`. The function `formatAmount()` returns a value. Of course, you can also combine those two techniques in the same function.

Functions are often used for code that you plan to call multiple times, but they can also be useful just to organize related bits of code into named collections, even if you only plan to call them once.

Consider:

```js
const TAX_RATE = 0.08;

function calculateFinalPurchaseAmount(amt) {
	// calculate the new amount with the tax
	amt = amt + (amt * TAX_RATE);

	// return the new amount
	return amt;
}

var amount = 99.99;

amount = calculateFinalPurchaseAmount( amount );

console.log( amount.toFixed( 2 ) );		// "107.99"
```

Although `calculateFinalPurchaseAmount(..)` is only called once, organizing its behavior into a separate named function makes the code that uses its logic (the `amount = calculateFinal...` statement) cleaner. If the function had more statements in it, the benefits would be even more pronounced.

### Scope

If you ask the phone store employee for a phone model that her store doesn't carry, she will not be able to sell you the phone you want. She only has access to the phones in her store's inventory. You'll have to try another store to see if you can find the phone you're looking for.

Programming has a term for this concept: *scope* (technically called *lexical scope*). In JavaScript, each function gets its own scope. Scope is basically a collection of variables as well as the rules for how those variables are accessed by name. Only code inside that function can access that function's *scoped* variables.

A variable name has to be unique within the same scope -- there can't be two different `a` variables sitting right next to each other. But the same variable name `a` could appear in different scopes.

```js
function one() {
	// this `a` only belongs to the `one()` function
	var a = 1;
	console.log( a );
}

function two() {
	// this `a` only belongs to the `two()` function
	var a = 2;
	console.log( a );
}

one();		// 1
two();		// 2
```

Also, a scope can be nested inside another scope, just like if a clown at a birthday party blows up one balloon inside another balloon. If one scope is nested inside another, code inside the innermost scope can access variables from either scope.

Consider:

```js
function outer() {
	var a = 1;

	function inner() {
		var b = 2;

		// we can access both `a` and `b` here
		console.log( a + b );	// 3
	}

	inner();

	// we can only access `a` here
	console.log( a );			// 1
}

outer();
```

Lexical scope rules say that code in one scope can access variables of either that scope or any scope outside of it.

So, code inside the `inner()` function has access to both variables `a` and `b`, but code in `outer()` has access only to `a` -- it cannot access `b` because that variable is only inside `inner()`.

Recall this code snippet from earlier:

```js
const TAX_RATE = 0.08;

function calculateFinalPurchaseAmount(amt) {
	// calculate the new amount with the tax
	amt = amt + (amt * TAX_RATE);

	// return the new amount
	return amt;
}
```

The `TAX_RATE` constant (variable) is accessible from inside the `calculateFinalPurchaseAmount(..)` function, even though we didn't pass it in, because of lexical scope.

**Note:** For more information about lexical scope, see the first three chapters of the *Scope & Closures* title of this series.

## Practice

There is absolutely no substitute for practice in learning programming. No amount of articulate writing on my part is alone going to make you a programmer.

With that in mind, let's try practicing some of the concepts we learned here in this chapter. I'll give the "requirements," and you try it first. Then consult the code listing below to see how I approached it.

* Write a program to calculate the total price of your phone purchase. You will keep purchasing phones (hint: loop!) until you run out of money in your bank account. You'll also buy accessories for each phone as long as your purchase amount is below your mental spending threshold.
* After you've calculated your purchase amount, add in the tax, then print out the calculated purchase amount, properly formatted.
* Finally, check the amount against your bank account balance to see if you can afford it or not.
* You should set up some constants for the "tax rate," "phone price," "accessory price," and "spending threshold," as well as a variable for your "bank account balance.""
* You should define functions for calculating the tax and for formatting the price with a "$" and rounding to two decimal places.
* **Bonus Challenge:** Try to incorporate input into this program, perhaps with the `prompt(..)` covered in "Input" earlier. You may prompt the user for their bank account balance, for example. Have fun and be creative!

OK, go ahead. Try it. Don't peek at my code listing until you've given it a shot yourself!

**Note:** Because this is a JavaScript book, I'm obviously going to solve the practice exercise in JavaScript. But you can do it in another language for now if you feel more comfortable.

Here's my JavaScript solution for this exercise:

```js
const SPENDING_THRESHOLD = 200;
const TAX_RATE = 0.08;
const PHONE_PRICE = 99.99;
const ACCESSORY_PRICE = 9.99;

var bank_balance = 303.91;
var amount = 0;

function calculateTax(amount) {
	return amount * TAX_RATE;
}

function formatAmount(amount) {
	return "$" + amount.toFixed( 2 );
}

// keep buying phones while you still have money
while (amount < bank_balance) {
	// buy a new phone!
	amount = amount + PHONE_PRICE;

	// can we afford the accessory?
	if (amount < SPENDING_THRESHOLD) {
		amount = amount + ACCESSORY_PRICE;
	}
}

// don't forget to pay the government, too
amount = amount + calculateTax( amount );

console.log(
	"Your purchase: " + formatAmount( amount )
);
// Your purchase: $334.76

// can you actually afford this purchase?
if (amount > bank_balance) {
	console.log(
		"You can't afford this purchase. :("
	);
}
// You can't afford this purchase. :(
```

**Note:** The simplest way to run this JavaScript program is to type it into the developer console of your nearest browser.

How did you do? It wouldn't hurt to try it again now that you've seen my code. And play around with changing some of the constants to see how the program runs with different values.

## Review

Learning programming doesn't have to be a complex and overwhelming process. There are just a few basic concepts you need to wrap your head around.

These act like building blocks. To build a tall tower, you start first by putting block on top of block on top of block. The same goes with programming. Here are some of the essential programming building blocks:

* You need *operators* to perform actions on values.
* You need values and *types* to perform different kinds of actions like math on `number`s or output with `string`s.
* You need *variables* to store data (aka *state*) during your program's execution.
* You need *conditionals* like `if` statements to make decisions.
* You need *loops* to repeat tasks until a condition stops being true.
* You need *functions* to organize your code into logical and reusable chunks.

Code comments are one effective way to write more readable code, which makes your program easier to understand, maintain, and fix later if there are problems.

Finally, don't neglect the power of practice. The best way to learn how to write code is to write code.

I'm excited you're well on your way to learning how to code, now! Keep it up. Don't forget to check out other beginner programming resources (books, blogs, online training, etc.). This chapter and this book are a great start, but they're just a brief introduction.

The next chapter will review many of the concepts from this chapter, but from a more JavaScript-specific perspective, which will highlight most of the major topics that are addressed in deeper detail throughout the rest of the series.
