# You Don't Know JS: Mise en route
# Chapitre 2 : Dans le JavaScript

Dans le chapitre précédent, j'ai fait l'introduction des blocs de base de construction d'un programme, tels que les variables, les boucles, les conditions et les fonctions. Bien sûr, tout le code affiché est écrit en JavaScript. Mais dans ce chapitre, nous voulons nous focaliser de manière plus spécifique sur les choses que vous avez besoin de savoir au sujet de JavaScript afin de mettre le pied à l'étrier en tant que développeur JS.

Nous allons présenter plusieurs concepts dans ce chapitre qui ne seront explorés que plus tard dans d'autres livres *YDKJS*.
You pouvez considérer ce chapitre comme un survol des différents sujets couverts en détail au travers du reste de cette série.

Si vous êtes nouveau en JavaScript, attendez-vous à passer un peu de temps à passer en revue plusieurs fois les concepts et exemples de code. Toute bonne fondation est posée brique par brique, donc ne vous attendez pas à tout comprendre lors de la première passe !

Votre voyage pour apprendre profondément JavaScript commence là.

**Remarque :** Comme je l'ai dit dans le chapitre 1, vous devriez définitivement essayer tout ce code vous-même quand vous lisez et travaillez tout au long de ce chapitre. Notez que certains morceaux de code ici utilisent des fonctionnalités introduites dans la nouvelle version de JavaScript à l'heure où sont écrites ces lignes (communément appelé "ES6" pour 6ème édition de ECMAScript -- le nom officiel de la spécification JS). S'il s'avère que vous utilisez un navigateur plus ancien, prè-ES6, le code pourrait ne pas fonctionner. Une mise à jour récente d'un navigateur moderne (comme Chrome, Firefox, ou IE) devrait être utilisé.

## Valeurs & Types

Comme nous l'avons vu dans le Chapitre 1, JavaScript possède des valeurs typées, et non pas des variables typées. Les types natifs suivants sont disponibles :

* `string`
* `number`
* `boolean`
* `null` et `undefined`
* `object`
* `symbol` (nouveau dans ES6)

JavaScript fournit un opérateur `typeof` qui peut examiner une valeur et vous dire de quel type il s'agit :

```js
var a;
typeof a;				// "undefined"

a = "hello world";
typeof a;				// "string"

a = 42;
typeof a;				// "number"

a = true;
typeof a;				// "boolean"

a = null;
typeof a;				// "object" -- weird, bug

a = undefined;
typeof a;				// "undefined"

a = { b: "c" };
typeof a;				// "object"
```

La valeur de retour de l'opérateur `typeof` est toujours l'une des six (sept en ES6 ! - le type symbole) chaîne de caractères. C'est à dire, `typeof "abc"` retourne `"string"`, et non pas `string`.

Remarquez comment dans cet extrait, la variable `a` contient tous les différents types de valeurs, et en dépit des apparences, `typeof a` ne demande pas le "type de `a`" mais plutôt le "type de la valeur qui est en ce moment dans `a`". Seules les valeurs ont des types en JavaScript ; les variables sont de simples conteneurs pour ces valeurs.

`typeof null` est un cas intéressant parce qu'il retourne de manière erronée `"objet"`, alors qu'on s'attendrait à ce qu'il retourne `"null"`.

**Attention :** Il s'agit d'un bug qui est là depuis un moment en JS, mais qui a très peu de chance d'être corrigé. Il existe bien trop de code qui s'appuie sur ce bug et ainsi donc, le corriger causerait encore d'avantage de bugs !

Aussi, notez `a = undefined`. Nous mettons explicitement `a` à la valeur `undefined`, mais cela n'a aucune différence comportementale avec une variable qui n'aurait aucune valeur, comme avec la ligne `var a;` au début de l'extrait de code. Une variable peut obtenir cet état "undefined" de plusieurs manières, comme par exemple les fonctions qui ne retourne aucune valeurs ou l'utilisation de l'opérateur `void`.

### Objets

Le type `objet` se réfère à une valeur composée à laquelle vous pouvez affecter des propriétés (que l'on nomme locations) qui possèdent toutes leurs propres valeurs de quelconque type.

```js
var obj = {
	a: "hello world",
	b: 42,
	c: true
};

obj.a;		// "hello world"
obj.b;		// 42
obj.c;		// true

obj["a"];	// "hello world"
obj["b"];	// 42
obj["c"];	// true
```

Il peut être utile de représenter cette valeur `obj` visuellement :

<img src="fig4.png">

On peut accéder aux propriétés avec la *notation par point* (c'est à dire, `obj.a`) ou avec la *notation par crochets* (c'est à dire, `obj["a"]`). La notation par point est généralement facile à lire et donc préférable autant que possible.

La notation par crochet est utile si le nom d'une propriété a des caractères spéciaux, comme `obj["hello world!"]` -- de telles propriétés sont souvent appelées *clés* quand on y accède via la notation par crochets. La notation `[]` requiert soit une variable (voir plus tard pour explication) ou une littérale de type `string` (qu'il faut entouré de `" .. "` ou `' .. '`).

Évidemment, la notation par crochets est aussi utile si vous voulez accéder à une propriété/clé mais dont le nom est stocké dans une autre variable, tel que :

```js
var obj = {
	a: "hello world",
	b: 42
};

var b = "a";

obj[b];			// "hello world"
obj["b"];		// 42
```

 Pour plus d'informations sur les `objets` JavaScript, voir *this & Prototype d'Objet* dans cette même collection, en particulier le Chapitre 3.

Il existe un certain nombre d'autres types de valeurs avec lesquels vous interagirez fréquemment dans les programmes JavaScript : *array* (tableau) et *function* (fonction). Mais plutôt que d'être des types natifs de bonne et due forme, ceux-ci devraient être considérés comme des sous-types -- des versions spécialisés du type `object`.

#### Tableaux

Un tableau est un `object` qui contient des valeurs (de quelconque type) non pas forcement dans des propriétés/clés nommées, mais plutôt dans des positions indexées numériquement.

```js
var arr = [
	"hello world",
	42,
	true
];

arr[0];			// "hello world"
arr[1];			// 42
arr[2];			// true
arr.length;		// 3

typeof arr;		// "object"
```

**Remarque :** Les langages qui commencent à compter à partir de zéro, comme le JS, utilise `0` comme index du premier élément.

Il peut être utile de représenter `arr` visuellement :

<img src="fig5.png">

Comme les tableaux sont des objets spéciaux (comme `typeof` le suggère), ils peuvent aussi avoir des propriétés, y compris la propriété mise à jour automatiquement `length` (longueur).

Vous pourriez en théorie utiliser un tableau comme un objet normal avec vos propres propriétés nommées, ou bien vous pourriez utiliser `object` et seulement lui donner des propriétés numériques (`0`, `1`, etc.) comme à un tableau. Cependant, c'est considérer généralement comme une mauvaise utilisation des types respectifs.

L'approche la meilleure et la plus naturelle est d'utiliser des tableaux pour les valeurs positionnées numériquement et utiliser les `object`s pour les propriétés nommées.

#### Fonctions

L'autre sous-type `object` que vous utiliserez dans vos programmes JS est la fonction :

```js
function foo() {
	return 42;
}

foo.bar = "hello world";

typeof foo;			// "function"
typeof foo();		// "number"
typeof foo.bar;		// "string"
```

Une fois de plus, les fonctions sont des sous-types d'`objects` -- `typeof` retourne `"function"` ce qui suggère qu'une `function` est un type majeur -- et peut donc avoir des propriétés, mais vous n'allez utiliser les propriétés des objets fonctions (comme `foo.bar`) dans très peu de cas.

**Remarque :** Pour plus d'informations sur les valeurs et leurs types en JS, voir les deux premiers chapitre de *Types & Grammaire* de cette collection.

### Méthodes des types natifs

The built-in types and subtypes we've just discussed have behaviors exposed as properties and methods that are quite powerful and useful.

Les types natifs et sous-types, dont on vient de parler, ont des comportements qui sont exposés en tant que propriétés ainsi que des méthodes qui sont relativement puissantes et utiles.

Par exemple:

```js
var a = "hello world";
var b = 3.14159;

a.length;				// 11
a.toUpperCase();		// "HELLO WORLD"
b.toFixed(4);			// "3.1416"
```

Le "comment" derrière le fait d'être capable d'appeler `a.toUpperCase()` est plus compliqué que simplement l'existence d'une méthode sur cette valeur.

En gros, il existe une forme "wrapper" (ou enrobeur) d'objet nommé `String` (avec `S` majuscule), qu'on appelle une "native", qui fait pair avec le type natif `string`; c'est cet "enrobeur" d'objet qui définit la méthode `toUpperCase()` sur son prototype.

Quand vous utilisez une valeur native comme `"hello world"` en tant qu'objet en référencant une propriété ou une méthode (`a.toUpperCase()` dans l'extrait de code précédent), JS "emboîte" automatiquement la valeur dans sa contre-partie l'"enrobeur" d'objet (cachée sous le capot).

Une valeur `string` peut être wrappée par un objet `String`, un `number` peut être wrappé par un objet `Number`, et un `boolean` peut être wrappé par un objet `Boolean`. Le plus souvent, vous n'avez pas besoin de vous soucier d'utiliser directement cette forme d'objet wrappers de valeurs -- préférez la forme native dans pratiquement tous les cas et JavaScript prendra soin du reste pour vous.

**Remarque :** Pour plus d'informations sur les natifs JS et l'"emboîtement", voir le Chapitre 3 de *Types & Grammaire* de cette collection. Afin de mieux comprendre le prototype d'un objet, voir le Chapitre 5 de *this & Prototypes d'Objets* de cette collection.

### Comparer les valeurs

Il y a deux principaux types de comparaison de valeur dont vous aurez besoin dans vos programmes JS : *égalité* et *inégalité*. Le résultat de quelconque comparaison est une valeur `boolean` au sens strict (`true` ou `false`), quels que soient les types de valeurs comparés.

#### Contrainte

Nous avons vu brièvement la contrainte dans le chapitre 1, revisitons cela maintenant.

La contrainte se présente sous deux formes en JavaScript : *explicite* et *implicite*. La contrainte explicite, c'est simplement quand vous pouvez voir de manière évidente dans le code qu'une conversion d'un type à un autre va se produire, alors que la contrainte implicite est quand la conversion de type se passe plus comme un effet de bord d'une autre opération.

Vous avez probablement entendu dire que la "contrainte c'est le mal" du fait qu'il y a clairement des endroits où la contrainte peut produire des résultats surprenants. Il n'y a rien de plus frustrant pour des développeurs que quand le langage les surprend.

La contrainte n'est pas le mal, et n'a pas non plus à être surprenante. En fait, la majorité des cas que vous pouvez construire avec contrainte de type sont tout à fait raisonnables et compréhensibles, et peuvent même être utilisés pour *améliorer* la lisibilité de votre code. Mais nous n'irons pas beaucoup plus loin dans ce débat -- le Chapitre 4 de *Types & Grammaire* de cette collection en couvrent la totalité.

Voici un exemple de contrainte *explicite* :

```js
var a = "42";

var b = Number( a );

a;				// "42"
b;				// 42 -- le nombre !
```

Et voici un exemple de contrainte implicite :

```js
var a = "42";

var b = a * 1;	// "42" contraint implicitement en 42 ici

a;				// "42"
b;				// 42 -- le nombre !
```

#### Truthy & Falsy

Dans le Chapitre 1, nous avons brièvement mentionné la nature "truthy" et "falsy" des valeurs : quand une valeur non-`boolean` est contrainte en un `boolean`, est ce qu'elle devient `true` ou `false`, respectivement ?

La liste des valeurs "falsy" en JavaScript est comme suit :

* `""` (chaîne vide)
* `0`, `-0`, `NaN` (`number` invalide)
* `null`, `undefined`
* `false`

Toute autre valeur qui n'est pas liste "falsy" est "truthy". Voici quelques exemples de celles-ci :

* `"hello"`
* `42`
* `true`
* `[ ]`, `[ 1, "2", 3 ]` (arrays)
* `{ }`, `{ a: 42 }` (objects)
* `function foo() { .. }` (functions)

It's important to remember that a non-`boolean` value only follows this "truthy"/"falsy" coercion if it's actually coerced to a `boolean`. It's not all that difficult to confuse yourself with a situation that seems like it's coercing a value to a `boolean` when it's not.

#### Egalité

Il y a quatre opérateurs d'égalité : `==`, `===`, `!=`, et `!==`. Les formes `!` sont bien sûr les versions symétriques "non-égales" de leurs contreparties; la *non-égalité* ne devrait pas être confondue avec l'*inégalité*.

La différence entre `==` et `===` est habituellement caractérisé par le fait que `==` vérifie l'égalité de valeur et `===` vérifie l'égalité de valeur et de type. Cependant, c'est imprécis. La façon convenable de les caractérisés est que `==` vérifie l'égalité de valeur avec la contrainte autorisée, et `===` vérifie l'égalité de valeur sans permettre que la contrainte intervienne ; `===` est souvent appelé "égalité strict" pour cette raison.

Considérez la contrainte implicite qui est autorisée par la comparaison d'égalité-faible `==` et pas autorisé avec l'égalité-stricte `===` :

```js
var a = "42";
var b = 42;

a == b;			// true
a === b;		// false
```

Dans la comparaison `a == b`, JS remarque que les types ne concordent pas, donc il passe par une série ordonnée d'étapes pour contraindre l'une ou les deux valeurs dans un type différent jusqu'à ce que les types concordent, là où alors une simple égalité de valeur peut être vérifiée.

Si vous y réfléchissez, il y a deux façons possibles que `a == b` donne `true` via contrainte. Soit on finit par comparer `42 == 42` soit `"42" == "42"`. De laquelle s'agit-il ?

La réponse est : `"42"` devient `42`, pour effectuer la comparaison `42 == 42`. Dans un exemple si simple, ça n'a pas l'air d'avoir de l'importance de quelle manière le processus s'effectue, car au final le résultat est le même. Il existe des cas plus complexes où l'important n'est pas seulement le résultat mais *comment* on y arrive.

Le `a === b` produit `false`, car la contrainte n'est pas autorisée, donc la comparaison de simple valeur échoue évidemment. Plusieurs développeurs sentent que `===` est plus prévisible, donc ils insistent toujours sur l'utilisation de cette forme et préconisent de rester éloigner de la forme `==`. Je pense que cette perspective est vraiment étroite. Je crois que `==` est un outil puissant qui est utile dans vos programmes, *si vous prenez le temps d'apprendre comment ça marche. *

Nous n'allons pas couvrir tous les détails de comment la contrainte fonctionne dans la comparaison `==`. La majeur partie fait sens, mais il existe des cas particuliers auxquels il faut faire attention. Vous pouvez lire la section 11.9.3 de la spécification ES5 (http://www.ecma-international.org/ecma-262/5.1/) pour voir les règles exactes, et vous serez surpris par combien cette mécanique est simple et direct, comparée à toute la hype qui l'entoure.

Pour résumé un tas de détails en quelques morceaux digestes, et pour vous aider à savoir quand utiliser `==` ou `===` dans diverses situations, voici mes règles simples :

* Si une des valeurs de la comparaison (droite ou gauche de l'opérateur) a une chance d'être la valeur `true` ou `false`, évitez `==` et utilisez `===`
* Si une des valeurs de la comparaison a une chance d'être ces valeurs spécifiques (`0`, `""`, or `[]` -- tableau vide), évitez `==` et utilisez `===`.
* Dans *tous* les autres cas, vous êtes sauf pour utiliser `==`. Non seulement c'est sûr, mais dans de nombreux cas cela simplifie votre code d'une manière qui améliore la lisibilité.

Ces règles se résument à vous conduire à avoir un œil critique sur votre code et à penser à quelles sortes de valeurs peuvent se présenter dans les variables qui sont comparées par égalité. Si vous êtes certains de ces valeurs, et que `==` est sûr, utilisez-le ! Si vous n'êtes pas sûr des valeurs, utilisez `===`. C'est aussi simple que ça.

La forme de non-égalité `!=` va de pair avec `==`, et la forme `!==` va de pair avec `===`. Toutes les règles et observations dont nous venons de discuter s'appliquent symétriquement aux comparaisons de non-égalité.

Vous devriez faire particulièrement attention aux règles de comparaison `==` et `===` si vous comparez deux valeurs non-primitives, comme `objects` (cela inclut `function` et `array`). Car ces valeurs sont tenues pour référence, les deux comparaisons `==` et `===` vérifieront simplement si les références correspondent, mais rien de ce qui est des valeurs sous-jacentes.

Par exemple, les `array`s sont par défaut contraints en `string` par le simple fait de joindre toutes les valeurs avec des virgules (`,`). Il se peut que vous pensiez que deux `array`s avec le même contenu soient égaux avec `==`, mais en fait ils ne le sont pas :

```js
var a = [1,2,3];
var b = [1,2,3];
var c = "1,2,3";

a == c;		// true
b == c;		// true
a == b;		// false
```

**Remarque :** Pour plus d'informations sur les règles de comparaison d'égalité avec `==`, voir la spécification ES5 (section 11.9.3) et aussi consultez le Chapitre 4 de *Types & Grammaire* de cette collection; voir le Chapitre 2 pour plus d'informations sur ce qui différencie valeurs et références.

#### Inégalité

Les opérateurs `<`, `>`, `<=`, et `>=` sont utilisés pour l'inégalité, référencés dans la spécification comme "comparaison relationnelle". Typiquement, ils seront utilisés avec des valeurs comparables ordinairement comme les `number`s. Il est facile de comprendre que `3 < 4`.

Mais les valeurs JavaScript `string` peuvent aussi être comparées par inégalité, en utilisant les règles typiques alphabétiques (`"bar" < "foo"`).

Quant est-il de la contrainte ? Des règles similaires comme la comparaison `==` (bien que pas exactement identique) s'appliquent aux opérateurs d'inégalité. Notez qu'il n'existe pas d'opérateurs de "strict inégalité" qui empêcheraient la contrainte de la même manière que l'opérateur `===` le fait.

Voyez :

```js
var a = 41;
var b = "42";
var c = "43";

a < b;		// true
b < c;		// true
```

Que se passe-t-il ici ? Dans la section 11.8.5 de la spécification ES5, il est dit que si les deux valeurs dans une comparaison `<` sont des `string`s, comme dans `b < c`, la comparaison est faite lexico-graphiquement (soit alphabétiquement comme un dictionnaire). Mais si l'une ou les deux ne sont pas une `string`, comme dans `a < b`, alors les deux valeurs sont contraintes en `number`s, et typiquement une comparaison numérique a lieu.

Le plus gros piège dans lequel vous pourriez tomber ici dans le cas de comparaison entre deux types de valeurs potentiellement différents -- souvenez-vous, il n'existe pas de formes d'"inégalité strict" utilisable -- est quand une des valeurs ne peut pas être changée en un nombre valide, tel que :

```js
var a = 42;
var b = "foo";

a < b;		// false
a > b;		// false
a == b;		// false
```

Un instant, comment est-ce que ces trois comparaisons peuvent-elles être toutes `false` ? Parce que la valeur `b` est contrainte en une "valeur numérique invalide" `NaN` dans les comparaisons `<` et `>`, et la spécification dit que `NaN` n'est ni supérieur ni inférieur à quelconque autre valeur.

La comparaison `==` échoue pour d'autres raisons. `a == b` a des chances d'échouer si elle est interprétée comme `42 == NaN` ou `"42" == "foo"` -- comme nous l'avons expliqué précédemment, le premier est en effet le cas.

**Remarque :** Pour plus d'informations au sujet des règles de comparaisons d'inégalité, voir la section 11.8.5 de la spécification ES5 et consulter également le Chapitre 4 de *Types & Grammaire* de cette collection.

## Variables

En JavaScript, les noms de variables (de même que les noms de fonctions) doivent être des *identifiants* valides. Les règles strictes et complètes pour les caractères valides dans les identifiants sont un peu complexes quand on considère les caractères non-traditionnels tel que l'Unicode. Cependant, si vous considérez uniquement les caractères alphanumériques ASCII typiques, les règles sont simples.

Un identifiant doit commencer avec `a`-`z`, `A`-`Z`, `$`, ou `_`. Il peut alors contenir n'importe quel caractère en plus des numéros `0`-`9`.

Généralement, la même règle s'applique aussi bien à un nom de propriété qu'à un identifiant de variable. Cependant, certains mots ne peuvent pas être utilisés comme des variables, mais sont valides pour des noms de propriété. 
Ces mots sont appelés "mots réservés", et incluent les mots-clés JS (`for`, `in`, `if`, etc.) ainsi que `null`, `true`, et `false`.


**Remarque :** Pour plus d'information sur les mots réservés, voir l'Appendice 1 de *Types et Grammaire* de cette collection.

### Portées de fonction

Vous pouvez utiliser le mot-clé `var` pour déclarer une variable qui appartiendra à la portée de la fonction en cours, ou à la portée globale si déclarée au niveau le plus haut en dehors de toute fonction.

#### Hissage (hoisting)

A chaque fois qu'une `var` apparaît dans une portée, cette déclaration est prise pour appartenir à la portée entière et accessible partout et tout au long.

De manière métaphorique, le comportement est appelé *hissage*, quand une déclaration `var` est conceptuellement "déplacée" en haut de sa portée englobante. Techniquement, ce processus est expliqué plus précisément par comment le code est compilé, mais nous pouvons passer ces détails pour le moment.

Voyez :

```js
var a = 2;

foo();					// fonctionne parce que la 
						// déclaration `foo()` est "hissée"

function foo() {
	a = 3;

	console.log( a );	// 3

	var a;				// la déclaration a est "hissée"
						// en haut de `foo()`
}

console.log( a );	// 2
```

**Attention :** Il ni d'usage ni une bonne idée de s'appuyer sur le *hissage* pour utiliser une variable plus tôt dans sa portée avant que sa déclaration n'apparaisse; ça peut être assez déroutant. Il est beaucoup plus courant et accepté d'utiliser les déclarations de fonctions *hissées*, comme nous le faisons avec l'appel `foo()` qui apparaît avant sa déclaration formelle.

#### Portées imbriquées

Quand vous déclarer une variable, elle est disponible n'importe où dans cette portée, ainsi que dans les portées inférieures/intérieures. Par exemple:

```js
function foo() {
	var a = 1;

	function bar() {
		var b = 2;

		function baz() {
			var c = 3;

			console.log( a, b, c );	// 1 2 3
		}

		baz();
		console.log( a, b );		// 1 2
	}

	bar();
	console.log( a );				// 1
}

foo();
```

Remarquez que `c` n'est pas disponible dans `bar()`, parcequ'elle déclaré seulement à l'intérieur de la portée de `baz()`, et que `b` n'est pas disponible à `foo()` pour la même raison.

Si vous essayez d'accéder à la valeur d'une variable dans une portée dans laquelle elle n'est pas disponible, vous recevrez une erreur `ReferenceError`. Si vous essayez de définir une variable qui n'a pas été déclarée, vous allez soit finir par créer une variable dans la portée globale (c'est mal !) ou recevoir une erreur, en fonction du "mode strict" (voir "Mode Strict"). Regardons ça de plus près :


```js
function foo() {
	a = 1;	// `a` n'est pas formellement déclarée
}

foo();
a;			// 1 -- oops, automatiquement en variable globale :(
```

C'est une très mauvaise pratique. Ne le faites pas ! Déclarer toujours vos variables formellement.

En plus de créer des déclarations pour variables au niveau des fonctions, ES6 vous permet (*let* en anglais) de déclarer des variables qui n'appartiennent qu'à des blocs individuels (paires de `{ .. }`), en utilisant le mot clé `let`. Hormis quelques détails nuancés, les règles de portées seront grossièrement les mêmes comme nous l'avons vu avec les fonctions :

```js
function foo() {
	var a = 1;

	if (a >= 1) {
		let b = 2;

		while (b < 5) {
			let c = b * 2;
			b++;

			console.log( a + c );
		}
	}
}

foo();
// 5 7 9
```

Parce qu'on utilise `let` au lieu de `var`, `b` appartiendra seulement à la déclaration `if` et ainsi pas à toute la portée de la fonction `foo()`. De manière similaire, `c` appartient seulement à la boucle `while`. La portée de bloc est très utile pour gérer les portées de vos variables d'une manière plus fine, ce qui rend votre code plus maintenable au fil du temps.

**Remarque :** Pour plus d'informations au sujet des portées, voir *Portées & Fermetures* dans cette collection. Voir *ES6 et au-delà* de cette collection pour plus d'informations au sujet de la portée de bloc `let`.

## Conditions

En addition à la déclaration `if` que nous avons introduite brièvement dans le Chapitre 1, JavaScript fourni quelques autres mécanismes de conditions auxquels on devrait jeter un œil.

Parfois, vous vous retrouverez à écrire une série de déclarations `if..else.if` comme cela :

```js
if (a == 2) {
	// faire quelque chose
}
else if (a == 10) {
	// faire autre chose
}
else if (a == 42) {
	// faire encore autre chose
}
else {
	// solution de repli ici
}
```

Cette structure fonctionne, mais elle est un peu verbeuse parce qu'il faut définir `un` test pour chaque cas. Voici une autre option, la déclaration `switch`:

```js
switch (a) {
	case 2:
		// faire quelque chose
		break;
	case 10:
		// faire autre chose
		break;
	case 42:
		// faire encore autre chose
		break;
	default:
		// solution de repli ici
}
```

Le `break` est important si vous voulez que les déclarations dans un `cas` uniquement s'exécutent. Si vous omettez le `break` d'un `case`, et que ce `case` concorde ou s'exécute, l'exécution continuera dans les prochaines déclarations `case` même si ce `case` ne concorde pas. Ce soi-disant "échec" est parfois voulu/désiré :

```js
switch (a) {
	case 2:
	case 10:
		// des trucs cools
		break;
	case 42:
		// d'autres trucs
		break;
	default:
		// solution de repli
}
```

Ici, si `a` est soit `2` ou `10`, le code "des trucs cools" sera exécuté.

Une autre forme de condition en JavaScript est l'"opérateur de condition", souvent appelé "opérateur ternaire". C'est comme une version plus concise de la simple déclaration `if..else`, telle que :

```js
var a = 42;

var b = (a > 41) ? "hello" : "world";

// similaire à :

// if (a > 41) {
//    b = "hello";
// }
// else {
//    b = "world";
// }
```

Si l'expression de test (`a < 41`) est évaluée comme `true`, la première clause (`"hello"`) sera le résultat, sinon ça sera la seconde clause (`"world"`), et quel que soit le résultat, il sera ensuite affecté à `b`.

L'opérateur de condition n'a pas à être utilisé dans une affectation, mais c'est généralement l'usage le plus commun.

**Remarque :** Pour plus d'informations sur les conditions de test et autres pattern pour `switch` et `? :`, voir *Types & Grammaire* dans cette collection.

## Mode Strict

ES5 a ajouté au langage le "mode strict", qui renforce les règles pour certains comportements. Généralement, ces restrictions sont perçues comme utile pour rendre le code plus sûr et comme un ensemble de lignes directrices. Aussi, le fait d'adhérer au mode strict rendra votre code généralement plus optimisable par le moteur. Le Mode Strict est un gros gain pour le code, et vous devriez l'utiliser dans tous vos programmes.

Vous pouvez choisir le mode strict pour une seule fonction, ou pour un fichier entier, en fonction d'où est-ce que vous mettez le pragma du mode strict.

```js
function foo() {
	"use strict";

	// ce code est en mode strict

	function bar() {
		// ce code est en mode strict
	}
}

// ce code n'est pas en mode strict
```

Comparez cela à :

```js
"use strict";

function foo() {
	// ce code est en mode strict

	function bar() {
		// ce code est en mode strict
	}
}

// ce code est en mode strict
```

Une différence clé (amélioration !) avec le mode strict est qu'il interdit la déclaration implicite de variable globale automatique qui se produit quand on oubli le `var` :

```js
function foo() {
	"use strict";	// enclenchement du mode strict
	a = 1;			// `var` manquant, ReferenceError
}

foo();
```

Si vous enclenchez le mode strict dans votre code, et que vous recevez des erreurs, ou que votre code commence à se comporter étrangement, vous serez sûrement tenter d'éviter le mode strict. Mais ça serait une mauvaise idée de céder à cet instinct. Si le mode strict provoque des problèmes dans votre programme, c'est un signe quasi-sûr qu'il a des choses à corriger dans votre programme.

Non seulement le mode strict garde votre code sur le droit chemin, mais non seulement il le rendra plus optimisable, mais il représente aussi la direction future du langage. Il serait plus simple pour vous de vous habituer au mode strict maintenant que de sans cesse le repousser -- il sera juste plus dur de s'y mettre plus tard !

**Remarque :** Pour plus d'informations sur le mode strict, voir le Chapitre 5 de *Types & Grammaire* de cette collection.

## Utiliser les fonctions comme valeurs

Jusque-là, nous avons parlé des fonctions comme étant le principal mécanisme de *portée* en JavaScript. On se souvient de la syntaxe de la déclaration `function` comme ci-dessous :

```js
function foo() {
	// ..
}
```

Bien que cela ne paraisse pas évident en regardant la syntaxe, `foo` est en fait juste une variable située dans la portée englobante extérieure à laquelle est donnée une référence à la `function` déclarée. Ainsi, la `function` elle-même est une valeur, juste comme `42` ou `[1,2,3]` le seraient.

Cela peut sembler être un concept un peu étrange à première vue, donc prenez un temps pour y songer. Non seulement vous pouvez passer une valeur (argument) *à* une fonction, mais *une fonction elle-même* peut être une valeur, assignable à des variables, ou passée d'autres fonctions ou une retournée d'autres fonctions.

Ainsi, une fonction devrait être considérée comme une expression, tout comme quelconque autre valeur ou expression.

Considérez :

```js
var foo = function() {
	// ..
};

var x = function bar(){
	// ..
};
```

La première expression de fonction assignée à la variable `foo` est appelée *anonyme* parce qu'elle n'a pas de `nom`.

La seconde expression de fonction est *nommée* (`bar`), et on lui a référencé `x` comme variable assignée. Les *expressions de fonction nommées* sont généralement préférables, bien que les *expressions de fonction anonymes* soient encore très courantes.

Pour plus d'information, voir *Portée & Fermetures* de cette collection.

### Expression de Fonction Invoquée Immédiatement (IIFEs en anglais)

Dans l'extrait de code précédent, aucun des expressions de fonction n'est exécutée -- nous le pourrions seulement si nous avions inclut `foo()` ou `x()`, par exemple.

Il existe une autre manière d'exécuter une expression de fonction, qu'on appelle plus généralement *expression de fonction exécutée immédiatement* (IIFE) :

```js
(function IIFE(){
	console.log( "Hello!" );
})();
// "Hello!"
```

La notation `( .. )` extérieure qui entoure l'expression de fonction `(function IIFE(){ .. })` est juste une nuance de grammaire JS requise pour prévenir son traitement comme une déclaration de fonction normale.

Le `()` à la fin de l'expression -- la ligne `})();` -- est ce qui en fait exécute l'expression de fonction référencée immédiatement avant.

Ça peut paraître étrange, mais ça n'est pas aussi bizarre que ça en a l'air au premier coup d'œil. Voyez les similitudes entre `foo` et `IIFE` ici :

```js
function foo() { .. }

// expression de fonction en référence à `foo`,
// puis `()` l'exécute
foo();

// expression de fonction `IIFE`,
// puis `()` l'exécute
(function IIFE(){ .. })();
```

Comme vous pouvez le voir, écrire le `(function IIFE(){ .. })` avant son `()` exécuteur est essentiellement la même chose que d'inclure `foo` avant son exécuteur `()`; dans les deux cas, la référence à la fonction est exécutée avec `()` immédiatement après.

Puisqu'une IIFE est juste une fonction, et que les fonctions créent des *portées* de variables, utiliser une IIFE de cette manière est souvent utiliser pour déclarer des variables qui n'affecterons pas le code en dehors de la IIFE :

```js
var a = 42;

(function IIFE(){
	var a = 10;
	console.log( a );	// 10
})();

console.log( a );		// 42
```

Les IIFEs peuvent aussi avoir des valeurs de retour :

```js
var x = (function IIFE(){
	return 42;
})();

x;	// 42
```

La valeur `42` est retournée par la fonction nommée `IIFE`, qui elle-même est exécutée, puis assignée à `x`;

### Fermetures


La *fermeture* est un des concepts les plus importants et souvent l'un des moins compris du JavaScript. Je ne vais pas le couvrir pas en détail ici, mais je vous invite à lire *Portée & Fermetures* de cette collection. Cependant je veux expliquer quelques petites choses à son sujet afin que vous compreniez le concept général. C'est une des techniques les plus importantes pour votre ensemble de compétences en JavaScript.

Vous pouvez penser à une fermeture comme à un moyen de se "souvenir" et continuer à accéder la portée d'une fonction (ses variables) même quand la fonction a fini son exécution.

Voyez :

```js
function faireAdditionneur(x) {
	// le paramètre `x` est une variable interne

	// la fonction interne `ajouter()` utilise `x`, donc
	// elle possède une "fermeture" sur elle
	function ajouter(y) {
		return y + x;
	};

	return ajouter;
}
```

La référence à la fonction interne `ajouter()`, qui est retournée à chaque appel à la fonction externe `faireAdditionneur(..)`, est capable de se souvenir de toute valeur `x` passée dans `faireAdditionneur(..)`. Maintenant, utilisons `faireAdditionneur(..)` :

```js
// `plusUn` reçoit une référence à la fonction interne `ajouter()`
// avec une fermeture sur le paramètre `x` de
// la fonction externe `faireAdditionneur(..)`
var plusUn = faireAdditionneur( 1 );

// `plusDix` reçoit une référence à la fonction interne `add(..)`
// avec une fermeture sur le paramètre `x` de
// la fonction externe `faireAdditionneur(..)`
var plusDix = faireAdditionneur( 10 );

plusUn( 3 );		// 4  <-- 1 + 3
plusUn( 41 );		// 42 <-- 1 + 41

plusDix( 13 );		// 23 <-- 10 + 13
```

Un peu plus d'explications sur comment fonctionne ce code :

1. Quand nous appelons `faireAdditionneur(1)`, nous recevons en retour une référence à sa fonction interne `ajouter()` qui se souvient de `x` comme  valeur `1`. Nous appelons cette référence à la fonction : `plusUn(..)`.
2. Quand nous appelons `faireAdditionneur(10)`, nous recevons une autre référence à sa fonction interne `add()` qui se souvient de `x` comme valeur `10`. Nous appelons cette référence à la fonction : `plusDix()`.
3. Quand nous appelons `plusUn(3)`, ça ajoute `3` (son `y` interne) à `1` (souvenu par `x`), et nous obtenons `4` en résultat.
4. Quand nous appelons `plusDix(13)`, ça ajoute `13` (son `y` interne) à `1` (souvenu par `x`), et nous obtenons `23` en résultat.

Ne vous inquiétez pas si cela paraît étrange et déroutant au premier abord -- ça peut l'être en effet ! Il va falloir beaucoup de pratique pour le comprendre pleinement.

Mais faites-moi confiance, une fois que vous l'avez compris, c'est l'une des techniques les plus puissante et utile dans tout le domaine de la programmation. Ça vaut définitivement l'effort de laisser votre cerveau méditer sur les fermetures pour un moment. Dans la prochaine section, nous pratiquerons d'avantage les fermetures.

#### Modules

L'usage le plus commun des fermetures en JavaScript est le pattern module. Les modules vous permettent de définir des détails d'implémentation (variables, fonctions) privés, qui sont caché du monde extérieur, ainsi qu'un API publique qui *est* accessible de l'extérieur.

Considérez :

```js
function User(){
	var username, password;

	function doLogin(user,pw) {
		username = user;
		password = pw;

		// faire le reste du travail de login
	}

	var publicAPI = {
		login: doLogin
	};

	return publicAPI;
}

// create a `User` module instance
var fred = User();

fred.login( "fred", "12Battery34!" );
```

La fonction `User()` sert de portée externe qui maintient les variables `username` et `password`, ainsi que la fonction interne `doLogin()`; ce sont tous des détails internes privés de ce module `User` auxquels on ne peut pas accéder à partir du monde extérieur.

**Attention :** Nous n'appelons pas exprès `new User()` ici, en dépit du fait que ça puisse paraître d'usage pour la plupart des lecteurs. `User()` est juste une fonction, non pas une classe à instancier, donc elle est juste appelée normalement. Utiliser `new` serait inapproprié et en fait un gâchis de ressources.

Exécuter `User()` crée une *instance* du module `User` -- une portée toute nouvelle est créée, et ainsi une toute nouvelle copie de chacune de ces variables/fonctions. Nous affectons cette instance à `fred`. Si nous lançons `User()` une fois de plus, nous obtiendrons une nouvelle instance entièrement à part de `fred`.

La fonction interne `doLogin()` possède une fermeture sur `username` et `password`, ce qui signifie qu'elle va garder l'accès à ces variables même après que la fonction `User()` ait terminé son exécution.

`publicAPI` est un objet avec une propriété/méthode, `login`, qui est une référence à la fonction interne `doLogin()`. Quand nous retournons `publicAPI` de `User()`, cela devient l'instance qu'on appelle `fred`.

À ce stade, la fonction externe `User()` a terminé son exécution. Normalement, on pourrait penser que les variables internes `username` et `password` ont disparu. Mais ici, non, parce qu'il y a une fermeture dans la fonction `login()` qui les gardent en vie.

C'est pourquoi nous pouvons appeler `fred.login(..)` -- qui est pareil que d'appeler le `doLogin(..)` interne -- et elle peut toujours accéder aux variables internes `username` et `password`.

Il y a de fortes chances qu'avec juste un coup d'œil aux fermetures et au pattern module, certaines choses soient toujours déroutantes. Ce n'est pas grave ! Ça prend du temps pour digérer tout ça.

A partir d'ici, allez lire *Portées et Fermetures* de cette collection pour une exploration en profondeur.

## L'identifiant `this`

Un autre concept généralement mal compris en JavaScript est l'identifiant `this`. De nouveau, il y a plusieurs chapitres sur ce sujet dans *this & Prototypes d'Objets* de cette collection, donc nous allons simplement introduire le concept.

Bien qu'il puisse paraître que `this` est rattaché aux "patterns orientées-objet", en JS `this` est un mécanisme différent.

Si une fonction possède une référence `this`, cette référence `this` pointe habituellement sur un `object`. Mais sur quel `object` elle point dépend de comment la fonction a été appelée.

Il est important de réaliser que `this` *ne se réfère pas* à la fonction elle-même, comme c'est souvent compris incorrectement.

En voici une illustration rapide :

```js
function foo() {
	console.log( this.bar );
}

var bar = "global";

var obj1 = {
	bar: "obj1",
	foo: foo
};

var obj2 = {
	bar: "obj2"
};

// --------

foo();				// "global"
obj1.foo();			// "obj1"
foo.call( obj2 );		// "obj2"
new foo();			// undefined
```

Il y a quatre règles pour comment `this` est initialisé, et elles sont démontrées dans les quatre dernières lignes de cet extrait de code.


1. `foo()` définit `this` comme objet global en mode non strict -- en mode strict, `this` serait `undefined` (indéfini) et vous recevriez lors de l'accès à la propriété `bar` -- donc `"global"` est la valeur trouvée pour `this.bar`.
2. `obj1.foo()` définit `this` comme objet `obj1`.
3. `foo.call(obj2)` définit `this` comme objet `obj2`.
4. `new foo()` définit `this` comme un objet vide tout neuf.

En un mot : Pour comprendre vers quoi `this` pointe, vous devez examiner comment la fonction a été appelée. La réponse sera l'une des quatre manières vues précédemment, et vous obtiendrez ainsi l'identité de `this`.

**Remarque :** Pour plus d'informations au sujet de `this`, voir les Chapitres 1 et 2 de *this et Prototypes d'Objets* de cette collection.

## Prototypes

Le mécanisme de prototype est assez compliqué. Nous y jetterons seulement un oeil ici. Je vous conseillerais de passer plus de temps sur la révision des Chapitres 4-6 de *this & Prototypes d'Objet* de cette collection pour tous les détails.

Quand vous référencez une propriété sur un objet, si cette propriété n'existe pas, JavaScript va automatiquement utiliser la référence interne du prototype de cet objet pour trouver un autre objet dans lequel chercher la propriété. Vous pourriez voir cela un peu comme une solution de repli si une propriété est absente.

La liaison entre la référence interne au prototype d'un objet et sa "solution de repli" se produit au moment où l'objet est créé. La façon la plus simple de l'illustrer est avec un utilitaire intégrée appelée `Object.create(..)`.

Voyez :

```js
var foo = {
	a: 42
};

// création de `bar` et liaison à `foo`
var bar = Object.create( foo );

bar.b = "hello world";

bar.b;		// "hello world"
bar.a;		// 42 <-- délégué à `foo`
```

Le schéma ci-dessous peut vous aider à visualiser les objets `foo` et `bar` et leurs relations :

<img src="fig6.png">

La propriété `a` n'existe pas sur l'objet `bar`, mais puisque `bar` a un lien prototypal sur `foo`, JavaScript va automatiquement de nouveau à la recherche de `a` sur l'objet `foo`, là où on peut le trouver.

Cette liaison semble être une fonctionnalité du langage quelque peu étrange. La façon la plus fréquente d'utiliser -- et je dirais même d'abuser -- cette fonctionnalité est d'essayer d'émuler/simuler un mécanisme de "classe" avec "héritage".

Cependant, il y a une manière plus naturelle d'appliquer les prototypes. C'est un pattern qu'on appelle "délégation de comportement", où vous concevez intentionnellement vos objets reliés afin qu'ils soient capables de *déléguer* une partie des comportements nécessaires.

**Remarque :** Pour plus d'informations sur les prototypes et la délégation de comportement, voir les Chapitres 4-6 de *this & Prototypes d'Objets* de cette collection.

## Ancien & Nouveau

Quelques-unes des fonctionnalités que nous avons déjà couvertes, et certainement plusieurs des fonctionnalités couvertes dans le reste de cette collection, sont de nouvelles additions au langage et ne seront pas nécessairement disponibles dans les navigateurs les plus anciens. En fait, certaines des fonctionnalités les plus récentes n'ont pas encore été implémentées dans aucun navigateur stable.

Alors, que faisons-nous avec ces nouvelles choses ? Est-ce qu'on doit attendre des années ou des décennies avant que ces anciens navigateurs tombent dans les oubliettes ?

C'est l'approche de nombreuses personnes à la vue de cette situation, mais ce n'est vraiment pas la bonne approche à avoir envers le JS.

Il existe deux techniques principales utilisables pour "apporter" le nouveau JavaScript dans les anciens navigateurs : le polyfilling et la transpilation.

### Polyfilling

Le mot "polyfill" est un terme inventé (par Remy Sharp) (https://remysharp.com/2010/10/08/what-is-a-polyfill) utilisé pour faire référence au fait de prendre la définition d'une nouvelle fonctionnalité et de produire un code avec un comportement équivalent, mais qui soit capable de s'exécuter dans des environnements JS plus anciens.

For example, ES6 defines a utility called `Number.isNaN(..)` to provide an accurate non-buggy check for `NaN` values, deprecating the original `isNaN(..)` utility. But it's easy to polyfill that utility so that you can start using it in your code regardless of whether the end user is in an ES6 browser or not.

Par exemple, ES6 défini un utilitaire appelé `Number.isNaN(..)` qui fournit une vérification exempte de bug pour les valeurs `NaN`, dépréciant ainsi l'utilitaire original `isNaN(..)`. Il est facile de polyfiller cet utilitaire afin de pouvoir l'utiliser dans votre code, quel que soit le navigateur de votre utilisateur final, qu'il soit compatible ES6 ou pas. 

Considérez :

```js
if (!Number.isNaN) {
	Number.isNaN = function isNaN(x) {
		return x !== x;
	};
}
```

La déclaration `if` empêche que le polyfill ne soit appliquée dans les navigateurs ES6, où cette fonctionnalité existe déjà. Si elle n'existe pas, on définit `Number.isNaN(..)`.

**Remarque :** La vérification que nous faisons ici tire avantage d'une bizarrerie sur la valeur `NaN`, qui est que c'est la seule valeur dans tout le langage qui n'est pas égale à elle-même.

Toutes les nouvelles fonctionnalités ne sont pas intégralement polyfiables. Parfois, la plupart du comportement peut être polyfié, mais il y a toujours quelques déviations. Vous devriez prendre de grandes précautions quand vous implémentez vous-même un polyfill, en vous assurant d'adhérer à la spécification aussi strictement que possible.

Ou mieux encore, utilisez un ensemble déjà contrôlé de polyfills auxquels vous pouvez vous fier, tels que ceux fournis par ES5-shim (https://github.com/es-shims/es5-shim) et ES6-Shim (https://github.com/es-shims/es6-shim).

### Transpilation

Il n'existe aucun moyen de polyfié une nouvelle syntaxe ajoutée au langage. Dans un ancien moteur JS, la nouvelle syntaxe lancerait une erreur de type unrecognized/invalid (syntaxe non reconnue ou invalide).

Ainsi donc, la meilleure option que nous avons est d'utiliser un outil qui converti votre code moderne en ancien code équivalent. Ce processus est appelé généralement "transpilation", une terminologie issue d'une fusion des verbes transformer + compiler.

Fondamentalement, votre code est rédigé sous une forme syntaxique nouvelle, mais ce que vous déployez pour le navigateur est du code transpilé dans une forme syntaxique ancienne. Typiquement, on ajoutera le transpileur dans le processus de "build" (construction de l'application), de la même manière qu'avec votre linter (vérificateur de code) ou votre minifier (compresseur de code).

Vous devez sûrement vous demander pourquoi se fatiguer à écrire dans la nouvelle syntaxe alors qu'elle est finalement transpilée en ancien code -- pourquoi ne pas juste écrire en code ancien directement ?

Il existe plusieurs raisons importantes, auxquelles vous devriez faire attention, qui jouent en faveur de la transpilation :

* La nouvelle syntaxe qui est ajouté au langage est conçue pour rendre votre code plus lisible et maintenable. Les équivalents plus anciens sont souvent beaucoup plus compliqués. Vous préférerez écrire dans une syntaxe plus neuve et claire, pas uniquement pour vous mais aussi pour tous les autres membres de l'équipe de développement.
* Si vous transpilez uniquement pour les anciens navigateurs, mais livrez la nouvelle syntaxe aux nouveaux navigateurs, vous tirez avantage des optimisations de performance des navigateurs grâce à la nouvelle syntaxe. Cela permet aussi aux fabricants de navigateurs d'avoir davantage de code en production sur lesquels tester leurs implémentations et optimisations.
* L'utilisation de la nouvelle syntaxe plus tôt permet qu'elle soit testée de manière plus robuste dans le monde réel, ce qui fournit des retours précoces aux membres du comité JavaScript (TC39). Si les problèmes sont trouvés suffisamment tôt, ils peuvent être changés/corrigés avant que ces erreurs de conception deviennent permanentes.

Voici un exemple rapide de transpilation. ES6 ajoute une fonctionnalité appelée "valeurs de paramètre par défaut"

```js
function foo(a = 2) {
	console.log( a );
}

foo();		// 2
foo( 42 );	// 42
```

Simple, n'est-ce-pas ? Utile aussi ! Mais ceci appartient à la nouvelle syntaxe qui est invalide dans les moteurs pre-ES6. Donc, que va faire le transpileur afin de faire tourner ce code dans des environnements plus anciens ?

```js
function foo() {
	var a = arguments[0] !== (void 0) ? arguments[0] : 2;
	console.log( a );
}
```

Comme vous le voyez, on vérifie si la valeur de `arguments[0]` est `void 0` (aussi dit `undefined`), et si c'est le cas, on fournit la valeur `2` par défaut; sinon, on assigne ce qui est passé.

En plus de la possibilité d'utiliser maintenant une syntaxe plus jolie, même dans les anciens navigateurs, étudier le code transpilé permet d'expliquer le comportement voulu plus clairement.

Vous ne l'avez peut-être pas remarqué en regardant la version ES6, mais `undefined` est la seule valeur qui ne peut pas être explicitement passée comme paramètre avec valeur par défaut, cependant le code transpilé rend ça plus clair.

Le dernier détail qu'il est important de souligner au sujet des transpileurs est qu'ils devraient maintenant être considérer comme faisant partie du standard de l'ensemble de l'écosystème et processus de développement JS. JS va continuer à évoluer, bien plus rapidement qu'avant, et régulièrement de nouvelle formes syntaxiques et fonctionnalités vont être ajoutées.

Si vous utilisez une transpileur par défaut, vous serez toujours capable de passer à la dernière nouvelle syntaxe au moment où vous le jugerez utile, plutôt que d'attendre des années que les navigateurs d'aujourd'hui disparaissent.

Vous pouvez choisir parmi un bon nombre de transpileur. Voici quelques bonnes options au moment où ces lignes sont écrites :

* Babel (https://babeljs.io) (formerly 6to5) : Transpile ES6+ en ES5
* Traceur (https://github.com/google/traceur-compiler) : Transpile ES6, ES7, et au-delà en ES5

## Non-JavaScript

Jusque-là, la seule chose que nous ayons couverte est le langage JS lui-même. La réalité est que la plupart du JS est écrit pour tourner et interagir dans des environnements comme les navigateurs. Un bon morceau du code que vous écrivez n'est pas, strictement parlant, contrôlé par JavaScript. Ça peut paraître un peu bizarre.

Le JavaScript non-JavaScript le plus fréquent que vous allez rencontrer est l'API DOM. Par exemple : 

```js
var el = document.getElementById( "foo" );
```

La variable `document` existe en tant que variable globale quand votre code tourne dans un navigateur. Ce n'est ni fourni par le moteur JS, ni contrôlé par la spécification JavaScript en particulier. Ça prend la forme de quelque chose qui ressemble terriblement à un `object` JS normal, mais ce n'est pas exactement ça. C'est un `object` special, souvent appelé un "objet hôte".

De plus, la méthode `getElementById(..)` sur `document` ressemble à une fonction JS normale, mais il s'agit d'une interface finement exposée à une méthode native fournie par le DOM de votre navigateur. Dans quelques navigateurs (nouvelle génération), ce niveau peut aussi être en JS, mais traditionnellement le DOM et son comportement est implémenté en quelque chose comme C/C++

Un autre exemple est les entrées/sorties (I/O en anglais pour Input/Output)

`alert(..)`, la favorite de tous, affiche une boîte de dialogue dans la fenêtre du navigateur de l'utilisateur. `alert(..)` est fourni à vos programmes JS par le navigateur, non pas par le moteur JS lui-même. L'appel que vous faîtes envoie un message aux mécaniques internes navigateur et celui-ci s'occupe de dessiner et afficher la boîte de dialogue.

Il en va de même avec `console.log(..)` ; votre navigateur fournit des tels mécanismes et les attaches à la boîte à outil pour développeur.

Ce livre, et toute cette collection, se focalise sur JavaScript le langage. C'est pourquoi vous ne verrez pas de couverture substantielle de ces mécanismes JavaScript non-JavaScript. Néanmoins, vous devez être conscient qu'ils existent, puisqu'ils seront dans tous les programmes JS que vous écrirez !

## Passage en revue

La première étape pour apprendre la manière de programmer le JavaScript est d'avoir une compréhension basique de ces mécaniques fondamentales comme les valeurs, types, fonctions, fermetures, `this`, et prototypes.

Évidemment, chacun de ces sujets mérite d'être couvert bien plus grandement que ce que vous avez pu voir ici, mais c'est pour cette raison qu'ils ont des chapitres et livres qui leur sont dédiés tout le long du reste de cette collection. Une fois que vous êtes à l'aise avec les concepts et exemples de code de ce chapitre, le reste de la collection vous attend pour vraiment creuser et connaître le langage en profondeur.

Le chapitre final de ce livre résumera brièvement chacun des titres de cette collection ainsi que les autres concepts qu'ils couvrent en plus de ce que nous avons déjà exploré.
