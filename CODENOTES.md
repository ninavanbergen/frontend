# Aantekening van What is Scope?
__Scope__ = is the set of rules that determines where and how a variable (identifier) can be looked up.
This look-up may be for the purpose of assigning to the variable, which is an LHS reference, or it 
may be for the purposes of retrieving its value, which is an RHS reference. 
Scope is waar variabele worden opgeslagen, waar je ze kan vinden. "Waar leeft een variable".
Engine doet het werk. Zorgt ervoor dat het programma wordt ingelezen en worden doorgegeven
aan de content.
__LHS__ = left hand side, references result from assignment operations. Scope related assignments 
can occur either with the = operator or by passing arguments to function parameters. Gaat over de 
container, waar is de declaratie van de variabele.
__RHS__ = right hand side. Wat is de waarde van de variabele.
The JS engine first compiles code before it executes, and in so doing, it splits up statements
like __var a = 2;__ into two separate steps:
* Als eerst, __var a__ to declare in die scope. Dit gebeurd in het begin, voor de code execution.
* Later, __a = 2__ to look up the variable (LHS reference) and assign to it if found.
Beide RHS en LHS reference look-ups beginnen at the currently executing scope, and if need be,
they work their way up the nested scope, one scope at a time, looking for the identifier, totdat
ze bij de global komen en stoppen, en either find it or don't. 

Onvoltooide RHS references geven een ReferenceError als resultaat. Onvoltooide LHS references geven 
automatisch, implicity-created global of that name als resultaat, of een ReferenceError.

# Compiler Theory
JS is een compiled language. In een traditionele compiled language process, a chunk of source
code, your program, will undergo 3 stappen voordat het wordt executed, dat betekend roughly
'compilation':
* Tokenzing/lexing: Het opbreken van een string van karakters in betekenisvolle chunks, genaamd
tokens.
* Parsing: Taking a stream (array) van tokens en turning die into a tree van geneste elementen.
Die collectively represent the grammatical structure van het programma. Die tree heet AST
(Abstract Syntax Tree).
* Code-Generation: Het proces of taking an AST en turning het into een executable code. Dit gedeelte
hangt af van de language, the platform it's targeting, etc. 

# Les voorbeeld
__Function scope / lexical scope__ = Als variabele in een functie leeft, dan leeft hij in de scope van de functie.
Als je een variable in een block declareert, dan is het een global scope. (window)
Zodra er geen referentie gevonden kan worden naar een variabele, krijg je een ReferenceError.
Dit krijg je als je, je var in een functie zet, en deze buiten de functie aanroept.

