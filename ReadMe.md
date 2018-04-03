# Les tests unitaires

## Liste des tâches à effectuer

- [X] Définition d'un test unitaire
- [X] A quoi sert un test unitaire
- [X] Comment fonctionne un test unitaire
- [X] Commencer l'écriture d'un test
- [ ] Panneau "Memo"
- [ ] Description des frameworks de test
- [ ] Description des environnements (IDEs)
- [ ] La methode TDD
- [ ] Examples de tests unitaire BackEnd
- [ ] Examples de tests unitaire FrontEnd

## C'est quoi un test unitaire ?

Le test unitaire est une procédure permettant de vérifier le
bon fonctionnement d'une partie d'un programme.
On écrit un test pour confronter une réalisation à sa 
spécification. Il permet de statuer sur le succés ou l'échec 
d'une vérification.  

## A quoi ça sert ?

### Trouver les erreurs rapidement

Il est préconiser d'écrire les tests avant la fonction a tester.
(Test Driven Developement) Les tests sont éxécutés durant tout le developpement, permettant
de visualiser si le code fraichement ecrit correspond au besoin.

### Sécuriser la maintenance

Lors de la modification d'un programme, les tests signalent les
eventuelles régressions. Certains tests pouvant echouer suite
à une modification, il faut donc soit réécrire le test pour 
le faire correspondre au nouveau besoin, soit corriger l'erreur
dans le code.

### Documenter le code

Les tests unitaires peuvent servir de complement à l'API. Il peut
être utile de lire les tests pour savoir comment s'utilise une
méthode. De plus, il est possible que la documentation ne soit
plus à jour alors que les tests correspondent à la réalité
de l'application.

## Comment ça fonctionne ?

### Initialisation (SetUp)

Définition d'un environnement de test complétement reproductible.

### Execution

La fonction a testé est executé.

### Vérification (Utilisation de fonction assert)

Comparaison des résultats obtenus avec un vecteur de
résultat définis. Ces tests définissent le résultat
du test : SUCCESS ou FAILURE.

### Désactivation (tearDown)

Désinstallation des fixtures pour revenir à l'état initial
du système dans le but de ne pas polluer les tests
suivant.
Tous les tests doivent être indépendant et reproductibles
unitairement.

## Utilisation

### Commencer par les tests  

Un test doit correspondre au spécification de l'application.
Il faut donc ecrire les tests en premier et les faire passer
par la suite plutôt que d'écrire le code avant et de 
prendre le risque d'être influencé par celui-ci lors de la 
rédaction des tests. La méthode TDD, propose un modèle 
simple pour l'écriture des tests unitaires :

- Ecrire une fonction de test qui doit obtenir un résultat
défini dans les spécifications. Ce code appelant un 
code qui n'existe pas encore, celui-ci doit échouer.
Ceci a pour but de tester une fonction qui test "quelque chose".

- Ecrire le code le "quelque chose" pour faire réussir
le test.

- Une fois le test en succés, rajouter un autre test pour obtenir 
un résultat légèrement different, en faisant varier les
entrées par exemple. Ce nouveau test fera faillir le code
principal.

- Modifier le code principal pour faire réussir les tests.

- Recommencer en éliminant et refactorisant les eventuelles redondances
dans le code des tests. On refactorise en même temps
le code principal.

- Un test unitaire doit tester une caractéristique
et une seule. On ne définit pas un "scénario" de test 
complexe dans un test unitaire.

- Il est déconseillé de tester les fonctions privées d'une 
classe, on se concentre à tester les fonctions publiques. 

### Pourquoi utiliser des mocks

Les mocks sont des objets permettant de simuler 
un objet réel de façon controllée. Dans certains cas, 
l'utilisation de mock est primordiale pour un gain de 
temps, de couverture de code et de fiabilité des tests.
Il sont utilisés par exemple pour :

- Simuler une base de donnée, un service Web, etc ...
Les interactions entre l'application et ces outils 
prennent du temps. L'utilisation de mock pour simuler 
leur fonctionnement peu être un gain de temps 
considérable.

- Certains cas d'erreur peuvent être difficile à 
reproduire. L'utilisation d'un mock permet ainsi de 
reproduire facilement un cas d'erreur et donc améliorer la couverture de code.
(Par exemple le catch d'une exception).

- Sans l'utilisation d'un mock, le test peut retourner une
erreur ne provenant pas du code qui est testé (par 
exemple une base de donnée).

## Environnement

Un environnement pré-configuré pour réaliser des tests unitaires
existe pour les principaux languages (notamment JAVA 
et JavaScript).
La plupart des frameworks de la famille xUnit, permettent la
génération de classes de tests. Cependant, ces frameworks 
ne fournissent que le squelettes des classes. Les tests
doivent donc être écrit par les developpeurs.  




