# You Don't Know JS: Mettre le pied à l'étrier
# Chapître 1: Dans la programmation

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

**Remarque :** Pour plus d'informations sur la compilation JavaScript, voir les eux premiers chapître de *Portées et Fermetures* de cette série.


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

**Remarque:** Pour d'avantage de détails et une couverture des opérateurs non-mentionnés ici, voir le Mozilla Developer Network (MDN)'s "Expressions and Operators" (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators).

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

Les programmes généralement les plus utiles nécessitent le suivi des changements qu'une valeur peut subir tout au long du programme, du fait des différentes tâches appelées par  votre programme.

La façon la plus simple de traiter cela dans votre programe est d'assigner la valeur à un conteneur symbolique, apellé une *variable* -- appelé ainsi car la valeur qu'il contient peut *varier* dans le temps au besoin.

Dans certains langage de programmation, vous déclarez une variable (conteneur) pour maintenir une valeur de type spécifique, tel que `number` ou `string`. On dit du *typage statique*, connu aussi comme *typage renforcé*, typiquement, qu'il bénéfique pour qu'un programme soit correct du fait qu'il prévient les conversions de type involontaires.

D'autres langages mettent l'accent sur les types pour valeurs au lieu des variables. Le *Typage faible*, aussi connu comme *typage dynamique*, permet à une variable de contenir n'importe qu'elle type de valeur à n'importe quel moment. Typiquement, on dit de cette forme de typage qu'il est bénéfique pour la flexibilité d'un programme car il permet à une seule variable de représenter une valeur quelque soit le type qu'elle pourra prendre à un moment donné la le déroulé logique du programme.

JavaScript utilise cette dernière approche, le *typage dynamique*, ce qui signifie que les variables peuvent contenir des valeurs de n'importe quel type sans avoir besoin de renforcement de *type*.

As mentioned earlier, we declare a variable using the `var` statement -- notice there's no other *type* information in the declaration. Consider this simple program:

Comme mentionné plus tôt, nous déclarons une variable en utilisant la déclaration `var` -- remarquez qu'il n'y a aucune autre information de *type* dans la déclaration. Voyez ce simple programme :

```js
var amount = 99.99;

amount = amount * 2;

console.log( amount );		// 199.98

// convertir `amount` en string, et
// ajouter "$" au début
amount = "$" + String( amount );

console.log( amount );		// "$199.98"
```

la variable `amount` commence par contenir le nombre `99.99`, puis contient le `number` résultant de `amount * 2`, qui est `199.98`.

La première commande `console.log(..)` doit *implicitement* coercer cette valeur de type `number` en une `string` (châine de caractère) afin de l'afficher.

Ensuite, la déclaration `amount = "$" + String(amount)` *explicitement* contraint (coerce) la valeur `199.98` en une `string` et ajoute un caractère `"$"` au début. A ce niveau là, `amount` contient la valeur de type string `"$199.98"`, donc la seconde déclaration `console.log(..)` n'a besoin d'aucun coercition pour l'afficher.

Les développeurs JavaScript remarquerons la flexibilité trouvé dans l'utilisation de la variable `amount` pour chacune des valeurs `99.99`, `199.98`, et `"$199.98"`. Les fans du typage statique préférerons une variable en plus comme `amountStr` pour contenir la représentation finale de la valeur `"$199.98"` car elle est de type différent.

Dans un cas ou dans l'autre, vous remarquerez que `amount` contient une valeur qui change au long du programme, ce qui illustre le but premier des variables : gérer l'*état* d'un programme.

En d'autres mots, l'*état* tient à jour les changements subis par les valeurs pendant que votre programme s'exécute.


Une autre utilisation courante des variables est la centralisation des valeurs. On appel plus généralement ceci des *constantes*, lorsque vous déclarez une variable avec une valeur et que vous avez l'intention que cette valeur *ne change pas* tout au long du programme.

Vous déclarez ces *constantes*, souvent en haut d'un programme, de sorte qu'il est pratique pour vous d'avoir un endroit où aller pour modifier une valeur si nécessaire. Par convention, les variables JavaScript en tant que constantes sont généralement en majuscules, avec des caractères de soulignement `_` entre plusieurs mots.

Un exemple un peu bête:

```js
var TAX_RATE = 0.08;	// 8% sales tax

var amount = 99.99;

amount = amount * 2;

amount = amount + (amount * TAX_RATE);

console.log( amount );				// 215.9784
console.log( amount.toFixed( 2 ) );	// "215.98"
```

**Remarque :** De la même manière que `console.log(..)` est en fait une fonction `log(..)` à laquelle on accède en tant que propriété de la valeur `console`, `toFixed(..)` dans notre cas, est une fonction qui peut-être accéder sur les valeurs de type `number`. Les `number` en  JavaScript ne sont pas automatiquement formattés en dollar -- le moteur ne connait vos intentions et il n'existe pas de type pour la monnaie. `toFixed(..)` nous permet de spécifier à combien de décimales nous aimerions arrondir le nombre `number` et produit la `string` comme requis.

La variable `TAX_RATE` est une *constante* seulement par convention -- il n'existe rien de spécial dans ce programme qui l'empêcherait d'être changée. Cependant, si la ville augmente le taux de la taxe sur les ventes à 9%, nous pouvons toujours facilement mettre à jour notre programme en changeant la valeur de `TAX_RATE` par `0.09` à un seul endroit, plutôt que de retrouver toutes les occurences de la valeur `0.08` parsemées dans le programme et de les mettre à jour.

La nouvelle version de JavaScript à l'heure où ces lignes sont écrites (appelé communémment "ES6") inclus une nouvelle manière de déclarer des *constantes*, en utilisant `const` eu lieu de `var` :

```js
// quant à ES6:
const TAX_RATE = 0.08;

var amount = 99.99;

// ..
```

Les constantes sont utiles tout comme les variables dont les valeurs ne changent pas, hormis que les constantes préviennent aussi tout changement accidentel de la valeur après l'affectation initiale. Si vous essayez d'assigner quelconque valeur à `TAX_RATE` après cette première déclaration, votre programme rejetera ce changement (et en mode strict, échouera avec une erreur -- voir "Mode Strict" dans le Chapître 2).

A ce propos, ce genre de "protection" contre les erreurs est similaire au renforcement de type du typage statique, vous voyez donc pourquoi le typage statique d'autres langages peut être attrayant !

*Remarque :* Pour plus d'informations sur comment peuvent être utilisées les différentes valeurs dans les variables dans vos programmes, voir le titre *Types & Grammaire* de cette collection.

## Blocs

L'employé du magasin de téléphone doit passer par une série d'étapes pour terminer la vérification lorsque vous achetez votre nouveau téléphone.

De la même façon, quand on code, nous avons besoin souvent de grouper une série de déclaration ensemble, ce qu'on appel souvent un *bloc*. En JavaScript un bloc est définie comme enveloppant une ou plusieurs déclaration entre une paire d'accolades `{ .. }`. Voyez :

```js
var amount = 99.99;

// un bloc général
{
	amount = amount * 2;
	console.log( amount );	// 199.98
}
```

Ce genre de bloc autonome général `{ .. }` est valide, mais n'est pas très fréquemment vu dans les programmes JS. Typiquement, les blocs sont attachés à d'autres déclarations de contrôle, telle que la déclaration `if` (si) (voir "Conditions") ou une boucle (voir "Boucles"). Par exemple :

```js
var amount = 99.99;

// is amount big enough?
if (amount > 10) {			// <-- block attached to `if`
	amount = amount * 2;
	console.log( amount );	// 199.98
}
```

Nous expliquerons les déclarations `if` dans la prochaine section, mais comme vous pouvez le voir, le bloc `{ .. }` avec des deux déclarations est attaché à `if (amount > 10)`; les déclarations à l'intérieur du bloc ne seront traitées seulement si la condition passe.

**Remarque :** A l'inverse de la plupart des autres déclarations comme `console.log(amount);`, une déclaration de type bloc n'a pas besoin de point-virgule (;) pour se terminer.

## Conditions

"Voulez-vous ajouter des protecteurs d'écran supplémentaires à votre achat, pour 9,99 $?" L'employé du magasin de téléphone vous a demandé de prendre une décision. Et vous devrez peut-être d'abord consulter l'*état* de votre portefeuille ou de votre compte bancaire pour répondre à cette question. Mais évidemment, ce n'est qu'une simple question qui se répond par «oui ou non»



Il existe pas mal de manières d'exprimer des "conditions" (autrement-dit décisions) dans nos programmes.

The most common one is the `if` statement. Essentially, you're saying, "*If* this condition is true, do the following...". For example:

La façon la plus commune est la déclaration `if`. Essentiellement, vous dites, *If* (Si) cette condition est vraie (true), faire la chose suivante...". Par exemple :

```js
var bank_balance = 302.13;
var amount = 99.99;

if (amount < bank_balance) {
	console.log( "I want to buy this phone!" );
}
```

La déclaration `if` requiert une expression entre les parenthères `()` qui peut être résolue comme soit `true` (vraie) ou `false` (fausse). Dans ce programme, nous lui avons fourni l'expression `amount < bank_balance`, qui en effet va être évaluée soit `true` (vraie) soit `false` (fausse) en fonction du montant qu'il y a dans la variable `bank_balance`.

Vous pouvez même fournir une alternative si la condition n'est pas vraie, appelé une clause `else` (sinon). Considérez :

```js
const ACCESSORY_PRICE = 9.99;

var bank_balance = 302.13;
var amount = 99.99;

amount = amount * 2;

// Pouvons-nous nous permettre un achat supplémentaire ?
if ( amount < bank_balance ) {
	console.log( "Je vais prendre l'accessoire !" );
	amount = amount + ACCESSORY_PRICE;
}
// sinon:
else {
	console.log( "Non, merci." );
}
```

Ici, si `amount < bank_balance` est `true`, nous afficherons `Je vais prendre l'accessoire !` et ajouter `9.99` à notre variable `amount`. Sinon, la clause `else` dira que nous répondrons poliement `"Non, merci."` et laisserons le montant tel quel.

Comme nous l'avons vu plus tôt dans "Valeurs & Types", les valeurs qui ne sont pas déjà du type attendu sont souvent coercées dans ce type. La déclaration `if` s'attend à un `boolean`, mais si vous lui passez quelque chose qui n'est pas un `boolean`, il va y avoir coercition.

JavaScript défini une liste de valeurs spécifiques qui sont considérées comme "falsy" (falsifiable) car quand elles sont coercées en `boolean`, elles deviennent `false` --  comme les valeurs `0` et `""`. Toutes autres valeurs qui ne sont pas sur la liste des valeurs "falsy" sont automatiquement "thruthy" (véridiques). -- quand coercées dans un `boolean` elles deviennent `true`. Les valeurs dites véridiques sont par exemple `99.99` et `"free"`. Voir le Chapître "Truthy & Falsy" dans le Chapître 2 pour plus d'informations.

Les *Conditions* existent sous d'autres formes en dehors des `if`. Par exemple, la déclation `switch` peut être utilisée comme raccourci pour une série de déclarations `if..else` (voir Chapître 2). Les boucles (voir "Boucles") utilisent une *condition* pour déterminer si la boucle doit continuer ou stopper.

**Remarque :** Pour creuser d'avantage le sujet de la coercition qui peut se produire implicitement dans les expressions de test d'une *condition*, voir le Chapître 4 de *Types & Grammaire* de cette collection.

## Boucles

Lors des heures de pointes, il y a une file d'attente de clients qui ont besoin de parler à l'employé de magasin de téléphone. Bien qu'il est toujours des gens sur cette file, l'employé doit continuer à servir le client suivant.

Répéter une série d'actions jusqu'à ce qu'une condition échoue -- en d'autres mots, répéter seulement pendant que la condition est maintenue -- est le travail d'une boucle de programmation; les boucles peuvent prendre différentes formes, mais elles répondent toutes à une comportement de base.

Une boucle inclue une condition de test ainsi qu'un bloc (typiquement `{ .. }`). Chaque fois que le bloc de la boucle s'éxecute, on appel ça une *itération*.

Par exemple, les boucles de forme `while` (tant que) et `do..while` (faire..tant que) illustrent le concept de répétition d'un bloc de déclaration jusqu'à ce que la condition ne soit plus `true` (vraie) :

```js
while (nombreDeClients > 0) {
	console.log( "Comment puis-je vous aider ?" );

	// aider le client...

	nombreDeClients = nombreDeClients - 1;
}

// à l'inverse de

do {
	console.log( "Comment puis-je vous aider ?" );

	// aider le client...

	nombreDeClients = nombreDeClients - 1;
} while (nombreDeClients > 0);
```

La seule différence pratique entre ces deux boucles est que dans l'une d'entre elle, la condition est testée avant la première itération (`while`), et dans l'autre, la condition est testée après la première itération (`do..while`).

Dans un cas comme dans l'aitre,  si le test de la condition est `false`, la prochaine itération n'aura pas lieu. Cela siginifie que si la condition est initiallement `false`, une boucle `while` ne s'éxecutera jamais, alors qu'une boucle `do..while` s'éxecutera juste la première fois.

Parfois, vous utilisez une boucle dans le but de parcourir un certain ensemble de chiffres, comme par exemple l'ensemble de `0` à `9` (10 chiffres). Vous pouvez faire cela en affectant une variable d'itération de boucle comme `i` à la valeur `0` et l'incrémenter d'`1` à chaque itération.

**Attention :** Pour plusieurs de raisons historiques, les langage des programmation comptent presque toujours les choses en commençant par zero, c'est à dire qu'ils commencent avec `0` au lieu de `1`. Si ce mode de pensée ne vous est pas familier, cela peut être déroutant au début. Prennez le temps de pratiquer à compter à partir de `0` afin de vous sentir plus à l'aise !

La condition est testée au moment de chaque itération, presque comme si il y avait une déclaration `if` dans la boucle.

Nous pouvons utiliser la déclaration `break` pour stopper une boucle. Aussi, on pourra observer qu'il est terriblement facile de créer une boucle qui continuerait pour toujours sans une mécanique de `break`.

Illustration :

```js
var i = 0;

// une boucle `while..true` qui bouclerait pour toujours, pas vrai ?
while (true) {
	// stooper la boucle ?
	if ((i <= 9) === false) {
		break;
	}

	console.log( i );
	i = i + 1;
}
// 0 1 2 3 4 5 6 7 8 9
```

**Attention :** Ceci n'est pas nécessairement une forme pratique d'utilisation des boucles. C'est présenté ici à titre d'illustration seulement.

Alors qu'un `while` (ou `do..while`) peuvent accomplir la tâche manuellement, il existe une autre forme syntaxique appelée une boucle `for` (pour) pour ce but précis :

```js
for (var i = 0; i <= 9; i = i + 1) {
	console.log( i );
}
// 0 1 2 3 4 5 6 7 8 9
```

Comme vous le voyez, dans les deux cas, la condition `i <= 9` est `true` pour les 10 premières itérations (`i` prennant les valeurs `0` à `9`) dans l'une et l'autre forme de boucle, mais devient `false` une fois que `i` prend la valeur `10`.

La boucle `for` a trois clauses : la clause l'initialisation (`var i=0`), la clause de test de condition (`i <= 9`), et la clause de mise à jour (`i = i + 1`). Donc, si vous comptez compter avec votre boucle d'itérations, `for` est une forme plus compacte et souvent plus simple à comprendre et écrire.

Il existe d'autres formes de boucles qui ont pour but d'itérer sur des valeurs spécifiques, tel que sur les propriétés d'un objet (voir Chapître 2) où le test de conditions implicite est simplement si toutes les propriétés ont été traitées.  Le concept de "boucler jusqu'à l'echec d'une condition" ne tient pas compte de la forme de la boucle.

## Fonctions

L'employé de magasin de téléphone ne porte pas sur lui une calculette pour calculer les taxes et le montant final de l'achat. C'est une tâche qu'il faut qu'il définisse une fois pour toute et ré-utilise encore et encore. Il y a des chances que la société possède un registre de caisse (ordinateur, tablette, etc.) avec ces fonctions déjà imbriquées.

De la même manière, vous allez sûrement vouloir spérarer éclater les tâches de votre code morceaux réutilisable, au lieu de vous répétez répétitivement (calembour recherché !). La façon de faire cela est de définir une `fonction`.

Une fonction est généralement une section de code qui porte un nom et qui peut être "appelée" par son nom, et ainsi le code qu'elle contient sera lancé à chaque fois. Voyez :

```js
function printAmount() {
	console.log( amount.toFixed( 2 ) );
}

var amount = 99.99;

printAmount(); // "99.99"

amount = amount * 2;

printAmount(); // "199.98"
```

Les fonctions peuvent optionnellement prendre des arguments (aussi appelés paramètres) -- des valeurs que vous passez à la fonction. Et elles peuvent aussi optionnellement retourner une valeur.

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

La fonction `printAmount()` prend un paramètre que nous appelons `amt`. La fonction `formatAmount()` retourne une valeur. Bien-sûr, vous pouvez aussi combiner ces deux techniques dans la même fonction.

Les fonctions sont souvent utilisées pour du code que vous plannifiez d'appeler plusieur fois, mais elles peuvent être aussi utiles pour organiser des morceaux de code dans des collections auxquelles on donnera un nom, même si vous plannifiez de ne les appeler qu'une seule fois.


Voyez :

```js
const TAX_RATE = 0.08;

function calculateFinalPurchaseAmount(amt) {
	// calculer le nouveau montant avec la taxe
	amt = amt + (amt * TAX_RATE);

	// retourner le nouveau montant
	return amt;
}

var amount = 99.99;

amount = calculateFinalPurchaseAmount( amount );

console.log( amount.toFixed( 2 ) );		// "107.99"
```

Bien que `calculateFinalPurchaseAmount(..)` ne soit appelée qu'une seule fois, organiser son comportement dans une fonction séparée rend le code qui utilise cette logique (la déclaration `amount = calculateFinal...`) plus propre. Si la fonction aurait contenu plus de déclarations, les bénéfices seraient encore plus flagrants.

### Portée

Si vous demandez à l'employé du magasin de téléphone un modèle qui n'est pas en stock, il ne pourra pas vous vendre le téléphone que vous voulez. Il n'a accès qu'aux téléphones sont sont dans l'inventaire de son magasin. Il vous faudra essayer un autre magasin pour voir si vous pouvez trouver le téléphone que vous cherchez.

Il existe un terme en programmation pour ce concept : *portée* (techniquement appelée *porteé lexicale*). En JavaScript, chaque fonction a sa propre portée. Une portée est simplement un ensemble de variables et de règles qui définissent comment on accède à ces variables par leur nom. Seul le code dans cette fonction peut accèder les variables de *portée* de cette fonction.

Un nom de variable doit être unique au sein d'un même portée --  il ne peut pas y avoir deux variables `a` l'une à côté de l'autre. Mais la même variable `a` pourrait apparaître dans différentes portées.

```js
function one() {
	// ce `a` appartient seulement à la fonction `one()`
	var a = 1;
	console.log( a );
}

function two() {
	// ce `a` appartient seulement à la fonction `two()`
	var a = 2;
	console.log( a );
}

one();		// 1
two();		// 2
```

Aussi, une portée peut être imbriquée dans une autre portée, exactement comme quand un clown lors d'une fête d'anniversaire explose un ballon dans un autre ballon. Si une portée est imbriquée dans une autre, le code dans la portée la plus profonde peut accèder aux variables de l'autre portée comme de l'autre.

Voyez :

```js
function outer() {
	var a = 1;

	function inner() {
		var b = 2;

		// nous pouvons accèder à `a` et `b` ici
		console.log( a + b );	// 3
	}

	inner();

	// on ne peut accèder qu'à `a` ici
	console.log( a );			// 1
}

outer();
```

Les règles de la portée lexicale disent que le code dans une portée peut accèder aux variables de cette portée où de nimporte qu'elle portée en dehors d'elle même.

Ainsi donc, le code dans la fonction `inner()` a accès à deux variables `a` et `b`, mais le code dans `outer()` a accès seulement à `a` -- elle ne peut pas accèder à `b` car cette variable se trouve seulement dans `inner()`.

Souvenez-vous de cet extrait de code:

```js
const TAX_RATE = 0.08;

function calculateFinalPurchaseAmount(amt) {
	// calculer le nouveau montant avec la taxe
	amt = amt + (amt * TAX_RATE);

	// retourner le nouveau montant
	return amt;
}
```

La constante `TAX_RATE` (variable) est accessible de la fonction `calculateFinalPurchaseAmount(..)`, même si on ne lui a pas passé, grâce à la portée lexicale.

**Remarque : ** Pour plus d'information sur la portée lexicale, voir les trois premiers chapîtres de *Portées et Fermetures* de cette collection.

## Mise en pratique

Il n'existe aucun substitut à la pratique dans l'apprentissage de la programmation. Aucune quantité d'écriture articulée de ma part, seule, ne fera de vous un programmeur.

Avec cela en tête, essayons de mettre en pratique quelqu'uns des concepts que nous apprenons ici dans ce chapître. Je donnerai les "exigences", et vous essayerez dans une premier temps. Ensuite, consultez le code ci-dessous pour voir quelle est mon approche.


* Ecrire un programme pour calculer le prix total d'achat de votre téléphone. Vous continuerez à acheter des téléphones (indice : boucle !) jusqu'à ce que vous épuisiez votre compte en banque. Vous acheterez aussi des accessoires pour chaque téléphone aussi longtemps que le montant de votre achat est en dessous votre seuil mental de dépense.
* Après avoir calculer le montant de votre achat, ajoutez-y la taxe, puis afficher le montant de l'achat calculé, formatté convenablement.
* Enfin, vérifiez le montant avec le solde de votre compte bancaire pour voir si vous pouvez vous l'offrir ou pas.
* Vous devriez mettre en place quelques constantes pour le "taux de la taxe", le "prix de téléphone", "le prix d'un accessoire", et "le seuil de dépense", ainsi qu'une variable pour le "solde de votre compte".
* Vous devriez définir des fonctions pour calculer la taxe et pour formatter le prix avec un "$" et l'arrondir à deux décimales.
* **Défi Bonus :** Essayez d'incorporer la saisie utilisateur dans ce programme, peut être avec le `prompt(..)` découvert dans "Entrée" un peu plus tôt. Vous pouvez demander à l'utilisateur de saisir le solde de son compte en banque, par exemple. Amusez-vous et soyez créatif !

OK, allez-y. Essayez. Ne jeter pas un coup d'oeil à mon code tant que vous n'avez pas essayé vous-même !

**Remarque :** Puisque ce livre traite de JavaScript, je vais évidemment résoudre cet exercice pratique en JavaScript. Mais vous pouvez le faire dans un autre langage pour le moment si vous vous sentez plus à l'aise ainsi.

Voici ma solution en JavaScript pour cet exercice :

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

**Remarque :** La manière la plus simple de lancer ce programme JavaScript est de le saisir dans une console pour développeur dans votre navigateur préféré.

Comment ça s'est passé ? Ca ne ferait pas de lak d'essayer de nouveau maintenant que vous avez vu mon code. Jouez avec, changez les constantes pour voir comment le programme tourne avec des valeurs différentes.

## Révision

Apprendre la programmation n'est pas nécessairement un processus complexe et accablant. Il existe quelques concepts qu'il faut se mettre dans la tête.

Ceux-ci sont commes de blocs de constructions. Pour construire une grande tour, vous commencez par mettre un bloc sur un bloc sur un un bloc. C'est pareil avec la programmation. Voici quelqu'uns des blocs essentiels de la programmaiton :

* Vous avez besoin d'*opérateurs* pour effectuer des actions sur les valeurs.
* Vous avez besoin de valeurs et de *types* pour effectuer différentes sortes d'actions comme des mathématiques sur des `number` ou afficher des `string`.
* Vous avez besoin de *variables* pour stocker les données (aussi appelé *état*) durant l'exécution de votre programme.
* Vous avez besoin de *conditions* comme les déclarations `if` pour prendre des décisions.
* Vous avez besoin de *boucles* pour répéter des tâches jusqu'à ce qu'une condition cesse d'être `true`.
* Vous avez besoin de *fonctions* pour organiser votre code en morceaux logiques et réutilisables.

Les commentaires de code sont une manière efficace d'écrire du code plus lisible, ce qui rend votre programme plus facile à comprendre, maintenir et réparer plus tard s'il y a des problèmes.

Enfin, ne négligez pas la puissance de la pratique. La meilleure manière d'apprendre à écrire du code est d'écrire du code.

Je suis enthousiaste que vous soyez sur le bon chemin pour apprendre à coder désormais ! Continuez. N'oubliez pas de vérifier d'autres ressources de programmation pour débutant (livres, blogs, en-ligne, entraînement, ect.). Ce chapître et ce livre sont un très bon commencement, mais ils ne sont qu'une brève introduction.

Le prochain chapître passera en revue plusieurs des concepts de ce chapître, mais d'un point de vue plus spécifiquement JavaScript, ce qui soulignera la plupart des grands sujets qui sont adressés dans de plus amples détails tout au long de cette collection.

