# You Don't Know JS : Mise en route
# Chapitre 3 : Dans YDKJS

De quoi traite toute cette collection de livres ? Dit simplement, il s'agit de prendre au sérieux la tâche d'apprendre *toutes les parties de JavaScript*, pas simplement un sous-ensemble du langage que quelqu'un a appelé les "bonnes parties", et pas juste la quantité minimale dont vous avez besoin pour terminer votre travail.

Les développeurs sérieux dans d'autres langages s'attendent à fournir un effort pour apprendre la plupart ou la totalité du (ou des) langages en lesquels ils écrivent principalement, mais les développeurs JS semblent sortir du lot dans le fait de ne pas apprendre beaucoup du langage. Ce n'est pas une bonne chose, et ce n'est pas quelque chose qu'on devrait permettre d'être la norme.

La collection *You Don't Know JS* (*YDKJS*) est en contraste avec les approches typiques d'apprentissage du JS, et ne ressemble à presqu'aucun autre livre sur le JS que vous lirez. Il vous défi de sortir de votre zone de confort et vous demandez les questions du "pourquoi ?" plus profondes pour chacun des comportements que vous rencontrez. Est-ce que vous vous sentez prêt à relever le défi ?

Je vais utiliser ce dernier chapitre pour résumer brièvement ce qu'il faut attendre du reste des livres de cette collection, et comment construire efficacement une fondation pour l'apprentissage du JS basée sur *YDKJS*.

## Portée et Fermetures

Probablement l'une des choses les plus fondamentales que vous aurez besoin de saisir rapidement est comment la portée des variables fonctionne vraiment en JavaScript. Ce n'est pas suffisant d'avoir une *croyance* anecdotique sur ce qu'est une portée. 

Le titre *Portée et Fermetures* commencent par brutaliser la conception erronée que JS est un "langage interprété" et ainsi non compilé. Eh non.

Le moteur JS compile votre code juste avant (et même parfois durant) l'exécution. Donc nous pouvons utiliser notre compréhension plus profonde de l'approche du compilateur dans notre code pour comprendre comment il trouve et gère les déclarations de variables et fonctions. Et par la même, nous rencontrons la métaphore typique pour la gestion de portée d'une variable JS, "Hissage."

Comprendre la "portée lexicale" est critique, c'est ce sur quoi nous basons notre exploration des fermetures dans le dernier chapitre du livre. Les fermetures sont probablement le concept le plus important de tout JS, mais si vous n'avez pas déjà compris comment fonctionne une portée, les fermetures resterons très certainement hors de votre portée.

Une application pratique importante des fermetures est le modèle de "module", comme nous l'avons introduit brièvement dans le Chapitre 2 de ce livre. Le modèle de module est probablement le modèle d'organisation de code le plus prévalent dans tout JavaScript ; une compréhension profonde de ce modèle devrait être une de vos plus grandes priorités.

## this et Prototypes d'Objet

La fausse-vérité probablement le plus répandue au sujet de JavaScript est que le mot-clé `this` fait référence à la fonction dans laquelle il apparaît. C'est affreusement faux.

Le mot-clé `this` est lié dynamiquement à comment la fonction en question est exécutée, et il s'avère qu'il y a quatre règles simples pour comprendre et déterminer pleinement ce lien de `this`.

Le mot-clé `this` est étroitement relié étroitement au mécanisme de prototype, qui est une chaîne de recherche de propriété, similaire à comment les variables de portée lexicale sont retrouvées. Mais, il y a un énorme abus attaché aux prototypes : l'idée d'émuler des classes et de l'héritage (soi-disant "prototypal").

Malheureusement, le désir d'apporter les concepts de classe et d'héritage au JavaScript est juste la pire chose que vous pourriez essayer de faire, parce que la syntaxe vous piège, vous faisant croire qu'il il y a quelque chose comme une classe, alors qu'en fait le mécanisme de prototype, fondamentalement opposé dans son comportement, est à l'œuvre.

Le problème est de savoir s'il est mieux d'ignorer la non-correspondance et prétendre que vous être en train d'implémenter l'"héritage", ou s'il est plus approprié d'apprendre et d'accueillir à bras ouvert la manière de fonctionner du système de prototype d'objet. Ce dernier est nommé de manière plus approprié "délégation de comportement".

Il y a là plus qu'une préférence syntaxique. La délégation est un modèle de conception complétement différent, et plus puissant, qui remplace le besoin de concevoir avec des classes et de l'héritage. Mais ces affirmations iront droit à la figure de la plupart des articles de blog, livres et conférences sur le sujet et ce tant que JavaScript existera.

Les affirmations que je fais concernant la délégation par opposition à l'héritage ne viennent pas d'une aversion pour le langage et sa syntaxe, mais du désir de voir la véritable capacité de la langue correctement utilisée et les interminables frustrations et confusions balayées.

Mais le cas que je fais concernant les prototypes et la délégation me tiens bien plus à cœur que ce que je voudrais me laisser dire ici. Si vous êtes prêt à reconsidérer tout ce que vous connaissez des "classes" JavaScript et de l'"héritage", je vous offre la chance de "prendre la pilule rouge" (*Matrix* 1999) et de consulter les Chapitres 4-6 de *this et Prototypes d'Objet* de cette collection.

## Grammaire et Types

Le troisième titre de cette collection se préoccupe principalement à s'attaquer à un autre sujet hautement controversé: la coercition. Il n'y a probablement aucun sujet qui cause plus de frustration aux développeurs JS que celui de quand vous parlez de la confusion autour de la coercition implicite.

De loin, la sagesse conventionnelle est de dire que la coercition implicite est une "mauvaise partie" du langage et qu'elle devrait être évitée à tout prix. En fait, certain ont même été jusqu'à dire qu'il s'agit d'un "défaut" dans la conception du langage. En effet, il y a des outils dont le travail est simplement de se scanner votre code et de se plaindre si vous faites quoi que ce soit qui ressemble de loin à l'usage de ce mécanisme.

Mais est ce que la coercition est à ce point déroutante, à ce point mauvaise, à ce point traitre, que votre code est condamné dès que vous commencez à l'utiliser ?

Je dis non. Après s'être équipé et compris comment les types et les valeurs fonctionnent véritablement dans les Chapitres 1-3, le Chapitre 4 prend part à ce débat et explique entièrement comment la coercition fonctionne, dans tous ces recoins, en long et en large. Nous voyons simplement quelles parties de la coercition sont réellement surprenantes et quelles parties sont en fait tout à fait censées si on se donne le temps d'apprendre.

Mais je ne suggère pas seulement que la coercition est censée et apprenable, j'affirme que la coercition est un outil incroyablement utile et totalement sous-estimé que *vous pouvez utiliser dans votre code*. Je dis que la coercition, quand utilisée convenablement, non seulement fonctionne, mais rend votre code meilleur. Tous ce qui doutent s'étoufferont sûrement à la vue d'une telle prise de position, mais je crois qu'il s'agit là d'une des principales clés pour passer dans un autre niveau de JS.

Est-ce que vous voulez simplement suivre ce que la foule dit, ou êtes-vous prêt à mettre de côté tous vos aprioris de côté et à regarder la coercition d'un point de vue nouveau ? *Types et Grammaire* de cette collection va *contraindre* votre manière de penser.

## Asynchronisme et Performance


Les trois premiers titres de cette collection se focalisent sur les mécanismes fondamentaux du langage, mais le quatrième titre s'écarte légèrement afin de couvrir les modèles qui plafonnent les mécaniques du langage pour gérer la programmation asynchrone. L'asynchronisme n'est pas simplement critique pour la performance de vos applications, il devient de plus en plus le facteur critique d'écriture et de maintenance.

Le livre commence par mettre au clair la confusion qu'il existe autour de la terminologie et des concepts tels que "asynchronisme", "parallèle", et "concurrent", et explique en profondeur comment ces choses-là s'appliquent ou non au JS.

Puis nous examinons les callbacks comme méthode principale pour créer l'asynchronisme. Mais nous remarquons là rapidement que le callback seul est désespérément inefficace pour les demandes modernes de la programmation asynchrone. Nous identifiant deux déficiences majeures liées au codage par callback seulement : l'*Inversion de Contrôle* (IoC), perte de confiance et manque de clarté.

Pour adresser ces deux déficiences majeures, ES6 introduit deux mécanismes (et modèle) : les promesses et les générateurs.

Les promesses sont un enrobeur, ne dépendant pas du temps, autour d'une "valeur future", ce qui vous permet de raisonner et composer avec elles que cette valeur soit prête ou non. De plus, elles résolvent efficacement les problèmes de confiance et IoC en routant les callbacks au travers d'un mécanisme solide et composable. 

Les générateurs introduisent un nouveau mode d'exécution des fonctions JS, où le générateur peut être mis en pause à des points de `cession` (`yield`) et être repris de manière asynchrone plus tard. La fonction pause-et-reprise permet de traiter le code séquentiel synchrone dans le générateur de manière asynchrone dans les coulisses.
Ce faisant, nous abordons les confusions non-linéaires, non locales, des rappels et rendons ainsi notre code synchrone asynchrone pour être plus raisonnable.

Mais c'est la combinaison des promesses et des générateurs qui " produit ou cède " notre modèle de codage asynchrone le plus efficace à ce jour en JavaScript. En fait, une grande partie de la sophistication future de l'asynchronisme à venir en ES7 et plus tard sera certainement construite sur cette base. Pour s'attaquer sérieusement à une programmation efficace dans un monde asynchrone, vous aurez besoin d'être vraiment à l'aise avec la combinaison des promesses et des générateurs.

Les promesses et les générateurs consistent à exprimer des modèles qui permettent à nos programmes de fonctionner plus simultanément et d'obtenir ainsi plus de traitement dans une période plus courte, mais JS a de nombreuses autres facettes traitant de l'optimisation des performances qui méritent d'être explorées.

Le Chapitre 5 explore des sujets tels que le parallélisme de programmes avec les Web Workers et le parallélisme de données avec SIMD, ainsi que des techniques d'optimisation de bas niveau telles que ASM.js. Le Chapitre 6 examine l'optimisation des performances sous l'angle de techniques d'analyse comparative appropriées, notamment les types de performances à prendre en compte et les éléments à ignorer.

Écrire du JavaScript de manière efficace signifie écrire du code qui peut casser les barrières que pose la contrainte d'être exécuté dynamiquement dans un large éventail de navigateurs et d'autres environnements. Cela nécessite beaucoup de planification complexe et détaillée et des efforts de notre part pour faire en sorte qu'un programme fasse mieux que "marcher.

Le livre * Asynchronisme et Performance * est conçu pour vous donner tous les outils et les compétences dont vous avez besoin pour écrire du code JavaScript qui fait sens et performant.

## ES6 et Au-delà


Peu importe à quel point vous avez maîtrisé JavaScript à ce stade, la vérité est que JavaScript n'arrêtera jamais d'évoluer, et de plus, la fréquence d'évolution augmente rapidement. Ce fait est presque une métaphore pour l'esprit que je veux donner à cette collection : reconnaître que nous ne *connaîtrons* jamais complètement chaque recoin de JS, parce que dès que vous pensez maîtriser tout, il y a de nouvelles choses qui vont voir le jour et que vous devrez apprendre.

Ce titre est dédié à la fois à une vision à court et à moyen terme de l'orientation que le langage prend, et pas seulement aux choses * connues * comme ES6 mais les choses * probables * au-delà.

Alors que tous les titres de cette collection abordent le statut de JavaScript au moment de la rédaction de ce texte, qui est à mi-chemin de l'adoption d'ES6, l'accent principal de la collection a été davantage sur ES5. Maintenant, nous voulons attirer notre attention sur ES6, ES7, et ...

Comme ES6 est presque terminé au moment de l'écriture de ces lignes, * ES6 et Au-delà * commence par diviser les éléments concrets du paysage ES6 en plusieurs catégories clés, y compris la nouvelle syntaxe, les nouvelles structures de données (collections) et les nouvelles capacités de traitement et API. Nous couvrons chacune de ces nouvelles fonctionnalités ES6, avec différents niveaux de détail, y compris l'examen des détails qui sont abordés dans d'autres livres de cette collection.

Voici quelqu'une des choses passionnantes à lire sur ES6 : déstructuration, valeurs de paramètres par défaut, symboles, méthodes concises, propriétés calculées, fonctions de flèches, délimitation de bloc, promesses, générateurs, itérateurs, modules, proxies, weakmaps, et bien plus encore! Ouf, ES6 nous met un sacré coup !

La première partie du livre est une feuille de route pour tout ce que vous devez apprendre pour vous préparer pour le nouveau JavaScript amélioré que vous allez écrire et explorer au cours des prochaines années.

La dernière partie du livre attire l'attention sur un bref aperçu des choses auxquelles nous pouvons nous attendre à voir dans le proche avenir de JavaScript. La plus importante découverte ici est que, post-ES6, JS va probablement évoluer fonctionnalité par fonctionnalité plutôt que version par version, ce qui signifie que nous pouvons nous attendre à voir ces choses à venir plus tôt que vous ne l'imaginez.

Le futur de JavaScript est radieux. N'est-ce pas le bon moment pour commencer à l'apprendre ?

## Passage en revue

La collection * YDKJS * se consacre à une proposition : que tous les développeurs JS peuvent et devraient apprendre toutes les parties de ce grand langage. Les opinions des gens, les suppositions faites par les frameworks, les dates limite des projets ne devraient pas être des excuses pour ne pas apprendre et ne pas comprendre profondément le JavaScript.

Nous prenons chaque domaine d'intérêt important du langage et consacrons un livre court mais dense pour en explorer pleinement toutes les parties que vous pensiez peut-être connaître mais que vous n'avez probablement pas complètement étudiées.

"Vous ne connaissez pas JS" n'est pas une critique ou une insulte. C'est le résultat de quelque chose que j'ai réalisé ; c'est que nous tous, y compris moi-même, devons accepter que l'apprentissage de JavaScript n'est pas un but final mais un processus. Nous ne connaissons pas encore JavaScript. Mais nous le connaîtrons !
