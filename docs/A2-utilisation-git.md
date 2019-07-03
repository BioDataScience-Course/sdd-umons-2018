# Prise en main {#prise}

Cette annexe comprend une description détaillée des différents outils utilisés dans la cadre de cette formation. 

Passez à la section suivante pour découvrir les outils. (ex: B.1 RStudio).


## RStudio {#rs}

Sélectionnez l'icône **RStudio** dans le dock (cercle bleu avec un R blanc au centre). Un login vers RStudio apparaît. Il faut y entrer les informations suivantes :

- Username : **sv**
- Password : **sv**
- Cochez éventuellement **Stay signed in** pour éviter de devoir réentrer ces informations continuellement : 

![](images/annexe_a2/rstudio1.png)

RStudio s'ouvre. C'est votre interface de travail à partir de laquelle vous allez piloter **R**. La fenêtre principale comporte différents éléments :

![](images/annexe_a2/rstudio2.png)

- Une barre de menu et une barre d'outils générale en haut 
- Un panneau à gauche intitulé **Console** où vous pouvez entrer des instructions dans **R** pour manipuler vos données
- Un panneau à droite en haut qui comprend plusieurs onglets, dont **Environnement** qui vous indique les différents items (on parle d'**objets**) chargés en mémoire dans **R** (mais pour l’instant, il n'y a encore rien).
- Un panneau en bas à droite comportant lui aussi plusieurs onglets. Vous devriez voir le contenu de **Files** au démarrage, un explorateur de fichiers simplifié relatif au contexte de travail actuel dans RStudio.

Pour l'instant, aucun document de travail n'est encore ouvert. Pour en créer un, ou ouvrir un document existant, vous utilisez le menu **Files**, ou encore, le premier bouton de la barre d'outils générale :

![](images/annexe_a2/rstudio3.png)

Le menu **Session** permet d'interagir directement avec **R** qui est lancé automatiquement en arrière plan dès que RStudio est ouvert. Par exemple, il est possible de relancer **R** à partir d'une entrée dans ce menu :

![](images/annexe_a2/rstudio4.png)

Le menu **Help** propose différentes possibilités pour accéder à la documentation de **R** ou de **RStudio**. Les **aide-mémoires** ("cheatsheets" en anglais) sont très pratiques lors de l'apprentissage. Nous conseillons de les imprimer et de les consulter régulièrement.

![](images/annexe_a2/rstudio5.png)

Le dernier bouton de la barre d'outils générale, intitulé **Project** permet d'ouvrir, fermer, et gérer les projets RStudio.

![](images/annexe_a2/rstudio6.png)

Vous avez maintenant repéré les éléments fondamentaux de l'interface de RStudio.

_A ce stade vous pouvez vous familiariser avec l'aide-mémoire relatif à l'IDE RStudio. Vous verrez qu'il y a beaucoup de fonctionnalités accessibles à partir de la fenêtre principale de RStudio. Ne vous laissez pas intimider : vous les apprendrez progressivement au fur et à mesure de l'utilisation du logiciel._


### Projet dans RStudio {#rs-projet} 

Un projet sert, dans RStudio, à organiser son travail. Un projet va regrouper l'ensemble des **jeux de données**, des **rapports**, des **présentations**, des **scripts** d'une **analyse** généralement en relation avec une ou plusieurs expériences ou observations réalisés sur le terrain ou en laboratoire. Voici à quoi ressemble l'interface de RStudio lorsque vous ouvrez un projet :

![](images/annexe_a2/project1.png)

Notez que le nom du projet est mentionné en haut à droite. Notez également, que le répertoire de base de votre projet est le répertoire actif dans l'onglet **Console** (`~/shared/projects/mon_premier_projet/` dans l'exemple), et que l'onglet **Files** affiche son contenu. Un fichier `mon_premier_projet.Rproj` y  est placé automatiquement par RStudio. Ce fichier contient les paramètres de configuration propres à ce projet^[N'éditer **jamais** à la main un fichier `.Rproj`. Laisser RStudio s'en occuper tout seul.]. C'est aussi une excellente façon de repérer qu'un répertoire est la base d'un projet RStudio, en repérant ce fameux fichier `.Rproj`.


#### Création d'un projet

Créez votre premier projet en suivant les quatre étapes suivantes :

- **Étape 1.**  Dans RStudio, Sélectionnez le bouton tout à droite dans la barre d'outils générale de RStudio qui ouvre un menu contextuel relatif aux projets. Sélectionnez y l'entrée `New Project...`.

- **Étape 2.** Une boite de dialogue s'ouvre. Sélectionnez `New Directory` pour créer votre projet dans un nouveau dossier. Il est également possible d'employer un dossier existant comme point de départ `Existing Directory`).

- **Étape 3.** Sélectionnez `New Project` tout en haut dans l'écran suivant qui vous propose également des projets particuliers (que nous n'utiliserons pas pour l'instant).

- **Étape 4.** Ensuite, RStudio vous demander quelques informations pour préconfigurer votre projet. 
    + Nommez le projet : `Directory name`. Indiquez ici `project_test`
    + Indiquez où vous voulez le placer : `Create project as subdirectory of`. Sélectionnez le sous-dossier `projects` dans le dossier `shared` partagé entre la SciViews Box et la machine hôte.
    + Sélectionnez `Create a git repository`
    + Désélectionnez `Use packrat with this project`(**il est important de ne pas sélectionner packrat, sous peine de dupliquer de nombreux packages R dans votre projet**)

Vous utilisez aussi le menu spécial projet pour créer un nouveau projet (`New Project...`), ouvrir un projet existant (`Open Project...`) ou encore fermer un projet (`Close Project`). Vous remarquez également que les derniers projets employés sont placés sous les trois options citées ci-dessus afin d'y accéder plus rapidement.


![](images/annexe_a2/project.png)

\BeginKnitrBlock{warning}<div class="warning">**Un projet ne doit bien sûr être créé qu'une seule fois !** Une fois les étapes ci-dessus effectuées, vous retournez simplement à votre projet en ouvrant le menu contextuel projets et en sélectionnant votre projet dans la liste. S'il n'y apparait pas, choisissez `Open Project...` et sélectionnez le fichier `.Rproj` relatif à votre projet. Ne créez bien évidemment **jamais** de projet à l'intérieur des dossiers d'un autre projet, surtout si vous utilisez Git. Sinon, RStudio va s'emméler les pinceaux !</div>\EndKnitrBlock{warning}


#### Organisation d'un projet

Le répertoire `projects` contient maintenant un projet RStudio intitulé `project_test`. Depuis la SciViews Box, il se situe dans :

```
/home
  /sv
    /shared
      /projects
        /project_test          # Le répertoire de base du projet
          project_test.Rproj   # Fichier de configuration du projet créé par RStudio
          .gitignore           # Fichier relatif à la gestion de version 
```

Vous devez maintenant structurer votre projet afin d'avoir différents sous-répertoires pour organiser au mieux le travail. Ceci concerne à la fois les données et les rapports d'analyse en lien avec ce projet.

Cliquez sur le bouton `New Folder` dans la barre d'outils de l'onglet **`Files`** et appelez ce nouveau dossier `data`. Ajoutez également les dossiers `analysis` et `R`. Vous pouvez faire cela depuis RStudio, mais aussi depuis le système hôte si c'est plus confortable pour vous.

```
/home
  /sv
    /shared
      /projects
        /project_test           # Le répertoire de base du projet
           analysis             # Le dossier qui comprend toutes les analyses (rapport, présentation,...)
           data                 # Le dossier qui comprend toutes les données
           project_test.Rproj  # Fichier de configuration du projet créé par RStudio
           .gitignore           # Fichier relatif à la gestion de version
           R                    # Le dossier qui comprend tous les scripts d'analyse
```

Vous obtenez donc un projet configuré de la manière suivante :

![](images/annexe_a2/project_orga.png)

L'organisation cohérente d'un projet est indispensable pour le bon fonctionnement et la clarté de vos analyses de données.


#### Chemins relatifs dans un projet

L'utilisation d'un projet permet de structurer de manière cohérente son travail. Vous allez maintenant devoir rendre votre projet **portable**.

Un projet RStudio pourra être qualifié de portable s'il est possible de déplacer son répertoire de base et tout ce qu'il contient (ou le renommer) sans que les analyses qu'il contient n'en soient affectées. Ceci est utile pour copier, par exemple, le projet d'un PC à un autre, ou si vous décidez de restructurer vos fichiers sur le disque dur.

- La première règle est de placer tous les fichiers nécessaires dans le dossier du projet ou dans un sous-dossier. C'est ce que nous venons de faire plus haut.

- La seconde règle est de référencer les différents fichiers au sein du projet avec des **chemins relatifs**. Nous allons maintenant apprendre à faire cela.

```
/home
  /sv
    /shared
      /projects
        /project_test             # Le répertoire de base du projet
           analysis               # Le dossier qui comprend toutes les analyses (rapport, présentation,...)
                rapport_test.rmd  # Rapport d'analyse
           data                   # Le dossier qui comprend toutes les données
                dataset.csv       # jeu de données exemple
           project_test.Rproj     # Fichier de configuration du projet créé par RStudio
           .gitignore             # Fichier relatif à la gestion de version
           R                      # Le dossier qui comprend tous les scripts d'analyse
```

Les différents systèmes d'exploitations (Windows, MacOS, Linux) utilisent des conventions différentes pour les chemins d'accès aux fichiers. Dans notre cas, la machine virtuelle utilise un système d'exploitation **Linux**. La barre oblique (`/` dite "slash" en anglais) sépare les différents dossiers imbriqués sous Linux et sous MacOS. Le système d'exploitation Windows utilise pour sa part, la barre oblique inversée (`\`, dite  "backslash" en anglais, mais dans R et RStudio, vous pourrez également utiliser le slash `/`, ce que nous vous conseillons de faire toujours pour un maximum de compatibilité entre systèmes). Par exemple, votre fichier `dataset.csv` se référence comme suit dans la SciViews Box, donc sous Linux :

```
/home/sv/shared/projects/project_test/data/dataset.csv 
```

Ce chemin d'accès est le plus détaillé. Il est dit **chemin d'accès absolu** au fichier. Vous noterez qu'il est totalement dépendant de la structure actuelle des dossiers sur le disque. Si vous renommez `project_test` ou si vous le déplacez ailleurs, la référence au fichier sera cassée ! Ainsi, si vous partagez votre projet avec un collaborateur qui le place ailleurs sur son disque dur, le chemin d'accès devra être adapté sans quoi l'analyse ne pourra plus s'exécuter correctement.

Décodons ce chemin d'accès :

- `/`, racine du système
- `/home/sv/`, notre dossier personnel comme utilisateur `sv`
- `/home/sv/shared/`, le dossier partagé entre la SciViews Box et notre PC hôte
- `/home/sv/shared/projects/project_test/`, le dossier de base de notre projet
- `/home/sv/shared/projects/project_test/data/`, le répertoire qui contient le fichier `dataset.csv`.

Le répertoire utilisateur `/home/<user>` est différent sous MacOS (il s'appelle `/Users/<user>`) et sous Windows (il se nomme généralement `C:\Users\<user>`). Comme c'est un répertoire clé, et qu'il est impossible d'écrire un chemin absolu qui soit le même partout, il existe un raccourcis : le "tilde" (`~`) qui signifie "mon répertoire utilisateur". Ainsi, vous pouvez aussi accéder à votre jeu de données `dataset.csv` comme ceci :

```
~/shared/projects/project_test/data/datasets.csv
```

Ce chemin d'accès est déjà plus "portable" d'un système à l'autre et d'un utilisateur à l'autre. Il est donc à préférer. Notez que sous R, vous devez doubler les backslashs sous Windows (`~\\Documents\\...`). Ce n'est ni très esthétique, ni compatible avec les deux autres systèmes. Heureusement, R comprend aussi le slash comme séparateur sous Windows, de sorte que la même syntaxe peut être utilisée partout ! **Nous vous conseillons donc d'utiliser aussi systématiquement les slashs sous Windows dans R ou RStudio.** Si cette façon d'écrire le chemin d'accès est compatible entre les trois systèmes d'exploitation, elle ne permet toujours pas de déplacer ou de renommer notre projet.

L'utilisation d'un **chemin relatif** permet de définir la position d'un fichier par rapport à un autre dossier qui est dit le **répertoire actif**. A titre d'exemple, nous voulons faire référence au jeu de données `dataset.csv` depuis notre rapport `rapport_test.Rmd`.

Demandez-vous d'abord quel est le **répertoire actif**. Pour un fichier R Markdown ou R Notebook, c'est facile, c'est le dossier qui contient ce fichier. Dans la console R, cela peut varier selon le contexte. Si vous avez ouvert un projet, c'est le répertoire de base du projet par défaut, mais cela peut être modifié. **Le répertoire actif pour R est toujours indiqué en gris à côté de l'onglet Console dans RStudio.** Vous pouvez aussi interroger R à l'aide de l'instruction `getwd()`:


```r
getwd()
```

Vous pouvez réaliser cela dans un chunk R dans votre document R Notebook par exemple : 

![](images/annexe_a2/chemin_relatif.png)

Une fois que vous connaissez le répertoire actif, vous naviguez _à partir de_ celui-ci. Il existe une convention pour reculer d'un dossier dans la hiérarchie : pour cela vous indiquez `..` à la place d'un nom de dossier. Voici ce que cela donne :

```
../data/dataset.csv
```

Comment lit-on ceci? Tout d'abord, notez (c'est très important) que le chemin d'accès ne commence pas par `/` (Linux ou MacOS), ou `C:/` (ou toute autre lettre, sous Windows). C'est le signe que l'on ne part pas de la racine du système de fichier, mais du **répertoire actif**. Ensuite, les différents éléments se décryptent comme suit :

- `~/shared/projects/project_test/analysis`, répertoire actif au départ pour le document R Notebook
- `..`, retour en arrière d'un niveau. On est donc dans `~/shared/projects/project_test`
- `/data`, naviguer dans le sous-dossier `data`. On est donc maintenant dans `~/shared/projects/project_test/data`. C'est le répertoire qui contient le fichier qui nous intéresse
- `/datasets.csv`, le nom du fichier référencé.

_A noter que si le fichier se trouve déjà dans le répertoire actif, le chemin relatif se résume au nom du fichier directement !_

Nulle part dans ce chemin relatif n’apparaît le nom du répertoire de projet, ni d'aucun autre répertoire parent. Ainsi, il est possible de renommer ou déplacer le projet sans casser la référence relative à n'importe quel fichier à l'intérieur de ce projet. Donc, en utilisant uniquement des références relatives, **le projet reste parfaitement portable**.


### Scripts R dans RStudio {#script}

Un script R est une suite d'instructions qui peuvent être interprétées pour effectuer nos analyses. Ce script est stocké dans un fichier dont l'extension est `.R`, et que l'on placera de préférence dans le sous-dossier `R` de notre projet.

![](images/annexe_a2/rscript.png)

Un script R s'ouvre dans la fenêtre d'édition de RStudio. Les parties de texte précédées d'un dièse (`#`) sont des commentaires. Ils ne sont jamais exécutés, mais ils permettent de structurer et d'expliquer le contenu du document (ou bien d'empêcher temporairement l'exécution d'instructions).

![](images/annexe_a2/rscript1.png)

Afin de bien documenter vos scripts, Commencez-les toujours par quelques lignes de commentaires qui contiennent un titre, le nom du ou des auteurs, la date, un copyright éventuel, ... L'utilisation de sections comme à la ligne 6 ci-dessus est vivement conseillée. Ces sections sont créée à l'aide de l'entrée de menu `Code` -> `Insert Section...` dans RStudio. Elles sont reprises dans le bas de la fenêtre édition pour une navigation rapide dans le script.


#### Création d'un script R

Vous avez à votre disposition plusieurs méthodes pour ouvrir un nouveau script R dans RStudio, dont deux vous sont montrées dans l'animation ci-dessous. 

![](images/annexe_a2/rscript1.gif)


#### Utilisation d'un script R

Un script R est un document natif de R. Ce dernier va interpréter les intructions qui compose le script et qui ne sont pas précédées d'un dièse (cliquez sur `Run` dans la barre d'outils de la fenêtre d'édition, ou utilisez le raccourci clavier `Ctrl+Enter` ou `Cmd+Enter` sur MacOS pour exécuter des instructions).

![](images/annexe_a2/rscript.gif)

Un script R doit être organisé de manière cohérente afin d'être exécutable de haut en bas. Dans l'exemple ci-dessus, on commence par :

- **Étape 1.** Importer les principaux outils avec l'instruction `SciViews::R`.

- **Étape 2.** Utiliser l'instruction `urchin <- read("urchin_bio", package = "data.io")` pour importer le jeu de données `urchin_bio` provenant du package `data.io` et l'assigner à `urchin`. On retrouve à présent `urchin` dans l'environnement global (`Global environment` dans l'onglet `Environnement` dans le fenêtre en haut à droite) de RStudio. 

- **Étape 3.** `.?urchin` et `View(urchin)` donnent des renseignements sur le jeu de données en renvoyant vers la page d'aide du jeu de données et en ouvrant ce jeu de données dans une fenêtre de visualisation.

- **Étape 4.** Réaliser des graphiques avec la fonction `chart()`.

Notez que les instructions exécutées dans le script sont envoyées dans la fenêtre `Console` en bas à gauche.


### R Markdown/R Notebook {#Rmd}

Un document R Markdown est un fichier dont l'extension est `.Rmd`. Il combine à la fois des instructions R (pour les analyses) et le langage Markdown (pour le texte). le R Markdown ne vous permet pas de visualiser directement le résultat final d'un rapport d'analyse^[Les systèmes d'édition professionnels dissocient en effet le fond de la forme : vous rédiger d'abord le contenu, et ensuite, vous indiquer le style à lui appliquer.]

![](images/annexe_a2/rmd.gif)

Tout comme dans un script R, les intructions doivent être également exécutées lors de la réalisation du rapport. Une forme spéciale de document R Markdown est le **R Notebook**. Ce dernier est un peu un intermédiaire entre un script R et un R Markdown. Il se présente de manière très similaire à ce dernier, mais vous pouvez également exécuter le code qu'il contient ligne par ligne comme dans un script.

Un document R Markdown / R Notebook se structure de la manière suivante :

- Un préambule
- Des zones d'édition
    + Le language employé est le Markdown
- Des zones de code R
    + Ces zones de codes sont appelée des **chunk**s

![](images/annexe_a2/rmd1.png)

Le **préambule** est nécessairement situé au tout début du document et est balisé à l'aide de trois tirets `---` sans rien d'autre sur une ligne au début et à la fin. Le préambule comporte un ensemble d'entrées de type `nom: valeur` qui configurent le document ou la façon dont il sera compilé en rapport final. Nous pouvons y indiquer le titre principal, le ou les auteurs, la date, ...

Le reste du document R Markdown est subdivisé en zones successives de texte et de code R (les fameux "chunks") contrastés sur des fond de couleurs différentes dans RStudio.

- Les zones de texte des parties Markdown où vous pouvez écrire votre prose.
- Les **chunks** contiennent des instructions qui vont être interprétées pour réaliser un calcul, un graphique, un tableau, etc. Le résultat de ce traitement sera placé à cet endroit dans le rapport final. Ces chunks sont balisés en entrée par trois apostrophes inverses suivies d'accolades contenant des instructions relatives au programme à utiliser, par exemple, ```` ```{r} ```` pour des chunks faisant appel au logiciel **R**, et sont terminés par trois apostrophes inverses (```` ``` ````).

Dans les zones Markdown, vous pouvez ajouter des balises qui permettront de formater votre texte dans la version finale de votre rapport. Par exemple, un ou plusieurs dièses (plus communément connu par sont appellation en anglais : "hastag") en début de ligne suivi d'un espace indique que la suite correspond à un titre. Titre de niveau 1 avec un seul dièse, de niveau 2 avec deux dièses, et ainsi de suite jusqu'à 6 niveaux possibles. Dans la capture d'écran ci-dessous, nous avons remplacé tout le contenu par défaut d'un R Notebook (à part le préambule) par une série de titres de niveau 1 correspondant à la structure générale d'un rapport scientifique : 

- Introduction
- Objectif
- Matériel et méthodes
- Résultats
- Discussion
- Conclusions


#### Création d'un R Markdown/Notebook

Vous avez à votre disposition deux méthodes pour ouvrir un nouveau R Notebook dans RStudio. Voyez l'animation ci-dessous. 

![](images/annexe_a2/rmd2.gif)


#### Utilisation d'un R Markdown/Notebook

**Afin de visualiser les résultats des chunks dans votre rapport final, Vous devez veiller à exécuter chaque chunks dans l'ordre dans un R Notebook**. Ceci n'est pas nécessaire dans un R Markdown, mais dans ce cas, tous les chunks sont systématiquement recompilés à chaque génération de rapport, ce qui peut être pénible si les calculs sont longs.

Pour exécuter un chunk, vous pouvez :

- cliquer sur le bouton "play", sous forme d'une flèche verte pointant vers la droite, situé en haut à droite du chunk
- cliquer sur `Run` et sélectionner `Run Current Chunk` dans le menu déroulant qui apparait
- Employer le raccourci clavier `Ctrl+Shift+Enter`

![](images/annexe_a2/rmd3.gif)

Le bouton `Run` propose plusieurs actions intéressantes :

- Exécuter la/les ligne(s) d'instruction sélectionnée(s) : `Run Selected Line(s)`
- Exécuter le chunk en entier : `Run Current Chunk`
- Exécuter tous les chunk précédents : `Run All Chunk Above` 
- Redémarer la console R et exécuter tous les chunks: `Restart R and Run All Chunks`. **Cette action est particulière intéressante pour s'assurer que le document est réellement reproductible !**
- ...

![](images/annexe_a2/rmd4.png)

Aprés la phase d'édition du texte (et des intructions dans les chunks pour un document R Notebook), vous pouvez visualiser votre rapport final en cliquant sur le bouton `Preview` (Notebook) ou `Knit` (Markdown).

![](images/annexe_a2/rmd5.png)

Le rapport est rapidement généré avec un rendu simple et professionnel. Par défaut, ce rapport présente le texte que vous avez écrit, avec les résultats que vous avez choisi de générer via R, mais également les instructions que vous avez employée pour obtenir ces résultats. Ceci permet de mieux comprendre, directement dans le rapport, comment tout cela a été calculé. Il est possible de cacher le code (dans un document généré depuis un Notebook R), ou d'indiquer une directive de compilation dans les chunks pour éviter que le code ne s'imprime dans le rapport final. Voyez les options en cliquant sur le petit engrenage à côté de la flèche verte en haut à droite du chunk. Consultez l'aide-mémoire de R Markdown accessible à partir du menu RStudio `Help` -> `Cheatsheets` -> `R Markdown Reference Guide`, voir **chunk options** p.2-3 pour plus d'informations sur les nombreuses options disponibles.

Par exemple, en ajoutant la directive `echo=FALSE` dans la balise d'entrée d'un chunk (```` ```{r, echo=FALSE} ````), on empèche d'imprimer le code de ce chunk dans le rapport.

![](images/annexe_a2/rmd7.gif)

Notez que sur la droite du bouton `Preview` ou `Knit`, vous avez un autre bouton représenté par un petit engrenage. Il donne accès à un menu déroulant qui vous donne la possibilité de modifier la façon de générer vos rapports. L'entrée tout en bas `Output Options...` permet de paramétrer la présentation du rapport.

Si vous cliquez sur la petite flèche noire pointant vrs le bas juste après `Preview` ou `Knit`, vous avez un autre menu déroulant qui donne accès aux différents formats possibles : HTML, PDF, Word, etc. Essayez les différentes options pour visualiser comment votre rapport se présente dans les différents formats.

![](images/annexe_a2/rmd6.png)


## GitHub 

TODO


## GitHub Classroom

TODO
