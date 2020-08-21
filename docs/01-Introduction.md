# (PART) Cours I: visualisation et inférence {-}

# Introduction {#intro}



##### Objectifs {-}

- Appréhender ce qu'est la science des données et les (bio)statistiques.

- S'initier à des outils de base (SciViews Box, RStudio, Markdown, Git, GitHub).

- Se sensibiliser à l'importance d'une présence web au niveau professionnel.


## Le monde il y a 25 ans {#donnees}

Il y a 25 ans, pas d'internet, pas de smartphone. Essayez d'imaginer ce que serait votre vie aujourd'hui si ces outils qui font partie de votre quotidien n'existaient pas.

- Les révolutions industrielles:
    * 1770 (1756) révolution 1: mécanisation
    * 1870 révolution 2: maîtrise de l'énergie
    * 1970 (1979) révolution 3: informatique
    * 1990 révolution 4: internet (1990 Web, 1992 ISOC = Internet society, 1993 = premier navigateur web)
    * 2000 révolution 5: numérique. GAFA = Google - Apple - Facebook - Amazon + Microsoft = GAFAM aux USA et BATX en Chine = Baidu - Alibaba - Tencent - Xiaomi. Aussi NATU = Netflix - Airbnb - Tesla - Uber.
    * 2010 révolution 6: NBIC = nanotechnologies - biotechnologies - informatique - sciences cognitives.
    * 2020 = date prévue pour que l'ordinateur ait la même puissance de traitement de l'information que le cerveau humain
    * 2030 = trans-humanisme: ordinateur plus puissant que l'homme et le remplacera probablement dans de nombreuses tâches.

- Valeur estimée des données et informations mises à disposition par les utilisateurs du net: 1000 milliards de dollar par an (écrivez ce nombre en chiffres pour vous donner une meilleure idée de ce que cela représente) !

- En 2020, quantité d'information ajoutée sur le net: 1000 milliards de milliards par semaine (écrivez ce nombre en chiffres également).

- Comparaison de puissance de traitement du cerveau humain _versus_ un ordinateur: 89 milliards de neurones, mais travail en multitâche alors qu'un processeur est monotâche => difficile à comparer. Une étude a montré en 2017 que l'un des 5 ordinateurs les plus puissants a été capable de simuler le fonctionnement d'environ 1% du cerveau humain en 1 sec. Il lui a fallu 40 min de calcul pour y arriver. Intel estime que l'évolution permettra d'égaler le cerveau humain en terme de vitesse de traitement vers 2020.

- Consommation électrique du supercalculateur: se mesure en mégawatts, alors que le cerveau humain consomme 12-13W seulement!

- "Le **transhumanisme** est une approche interdisciplinaire qui nous amène à comprendre et à évaluer les avenues qui nous permettrons de surmonter nos limites biologiques par les progrès technologiques. Les trans-humanistes cherchent à développer les possibilités techniques afin que les gens vivent plus longtemps et ..."

Vous pouvez maintenant avoir un aperçu de l'importance d'avoir des outils performants afin d'appréhender les données dont le nombre croit de manière exponentielle. Pour ce cours de sciences des données,  plusieurs outils puissants sont mis à votre disposition (Vous trouverez sur l'hyperlien suivant, un poster présentant la philosophie du cours <https://github.com/BioDataScience-Course/RencontresRRennes2018>)


## Découverte des outils
La science des données est complexe et requiert d'employer des outils performants. Nous avons sélectionné ces outils pour vous.


### Machine virtuelle

La **SciViews Box** est une machine virtuelle (un ordinateur complet, mais totalement indépendant du matériel -le hardware- et qui peut être déployé sur pratiquement n'importe quel ordinateur physique). Cette SciViews Box est complètement configurée et dédiée à la sciences des données biologiques. Elle contient tout ce qu’il faut pour importer et analyser vos données, et ensuite écrire des rapports ou d'autres documents prêts à publication ou à présentation. Elle vous servira également à collaborer avec d'autres chercheurs qui peuvent facilement utiliser exactement la même machine virtuelle (aspect reproductible de vos analyses).

Des explications détaillées se trouvent dans l'annexe \@ref(svbox) dédiée à l'installation et la configuration de la SciViews Box.

<div class="figure" style="text-align: center">
<img src="images/sdd1_01/svBox-256.png" alt="Logo de la SciViews Box" width="256px" />
<p class="caption">(\#fig:unnamed-chunk-1)Logo de la SciViews Box</p>
</div>

<div class="bdd">
<p>Une fois connecté au compte <code>sv</code> dans la machine virtuelle, réalisez l'activité : <strong>Découverte de la machine virtuelle</strong> <a href="https://github.com/BioDataScience-Course/sdd_lesson/blob/master/sdd1_01/presentations/sdd1_01_svbox.pdf" class="uri">https://github.com/BioDataScience-Course/sdd_lesson/blob/master/sdd1_01/presentations/sdd1_01_svbox.pdf</a></p>
<p>Après avoir réalisé l'activité, un document récapitulatif est mis à votre disposition : <a href="https://github.com/BioDataScience-Course/sdd_lesson/blob/master/sdd1_01/exercises/sdd1_01_svbox.Rmd" class="uri">https://github.com/BioDataScience-Course/sdd_lesson/blob/master/sdd1_01/exercises/sdd1_01_svbox.Rmd</a></p>
</div>

Des explications détaillées se trouvent dans l'annexe \@ref(svbox_use) dédiée à l'utilisation de la SciViews Box.


### RStudio

RStudio est l'outil au sein de la SciViews Box que vous allez utiliser le plus fréquemment durant ce cours. 

![](images/sdd1_01/rstudio.gif)

Il fournit un environnement complet et optimisé pour réaliser vos analyses, vos graphiques et vos rapports. RStudio travaille main dans la main avec le logiciel R qui effectue l'ensemble des traitements.

![](images/sdd1_01/rstudio_description_mod.png)

L'interface utilisateur de RStudio est divisée en quatre zones importantes (A-D) avec une barre d'outils générale par dessus : 

A. Une zone d'édition 

B. Plusieurs onglets sont présents comme `Environnement`, `History` ou encore `Connections`. Par exemple, les différents items (on parle d’objets) chargés en mémoire dans R sont visibles dans l'onglet `Environnement` (mais pour l’instant, il n’y a encore rien).

C. La `Console` est l'endroit où vous pouvez entrer des instructions dans R pour manipuler vos données

D. Une zone multiusage où vous pouvez manipuler vos fichiers (`Files`), vos graphiques (`Plots`), les différents "addins" de R (on parle de `Package`s), accéder aux pages d'aide (`Help`) ou encore, visualiser le rendu final de vos rapports (`Viewer`).

Des explications détaillées se trouvent dans l'annexe \@ref(rs) qui présente les bases de l'utilisation de RStudio. Vous avez également à votre disposition un aide-mémoire afin d'appréhender cette interface [RStudio IDE Cheat Sheet](https://github.com/rstudio/cheatsheets/raw/master/rstudio-ide.pdf). 


##### Pour en savoir plus {-}

- [RStudio](https://www.rstudio.com/). Site Web de RStudio comprenant un ensemble de ressources en anglais

- [RStudio, un environnement de développement pour R](https://quanti.hypotheses.org/488/). Brève explication de RStudio en français.

- [RStudio : sa vie, son oeuvre, ses ressources](https://elementr.hypotheses.org/237). Un autre site Web consacré à RStudio en français.


### Markdown

Dans RStudio, les rapports sont rédigés en utilisant le langage **Markdown** dans la zone d'édition. Il permet de baliser le texte pour indiquer le sens des différentes parties (par exemple, pour indiquer les différents niveaux de titres). Il permet de se concentrer sur l'écriture dans un premier temps en dissociant le fond de la mise en forme. En effet, vous vous préoccupez de l'aspect final du document dans un second temps, et même, vous pouvez changer radicalement d'avis pratiquement sans rien changer dans le texte (par exemple, il est possible de passer d'une page Web à un document PDF ou Word, ou même encore à une présentation).

![](images/sdd1_01/markdown.gif)

**Markdown** est relativement simple et intuitif à l'usage, même si un petit effort est nécessaire, naturellement, au début. Quels sont les commandes et instructions indispensables lorsque l'on rédige un rapport ?  Des titres et sous-titres, une mise en évidence (texte en italique ou en gras), des listes,... Il ne faut au final que très peu de commandes pour réaliser un rapport de qualité avec une mise en page sobre et épurée qui caractérise les travaux professionnels. 

Vous avez à votre disposition deux aide-mémoires pour apprendre **Markdown** : [R Markdown Cheat Sheet](https://github.com/rstudio/cheatsheets/raw/master/rmarkdown-2.0.pdf) et [R Markdown Reference Guide](https://www.rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference.pdf) plus détaillé.

Après avoir rédiger votre document, vous devez cliquer sur le bouton `Preview` ou `Knit` (selon le type de document édité) dans la barre d'outils de la zone d'édition pour obtenir la version finale formatée.

<div class="bdd">
<p>Une fois connecté au compte <code>sv</code> dans la machine virtuelle, réalisez l'activité : <strong>Découverte de RStudio et R Markdown</strong> <a href="https://github.com/BioDataScience-Course/sdd_lesson/blob/master/sdd1_01/presentations/sdd1_01_markdown.pdf" class="uri">https://github.com/BioDataScience-Course/sdd_lesson/blob/master/sdd1_01/presentations/sdd1_01_markdown.pdf</a></p>
<p>Après avoir réalisé l'activité, un document récapitulatif est mis à votre disposition : <a href="https://github.com/BioDataScience-Course/sdd_lesson/blob/master/sdd1_01/exercises/sdd1_01_markdown.Rmd" class="uri">https://github.com/BioDataScience-Course/sdd_lesson/blob/master/sdd1_01/exercises/sdd1_01_markdown.Rmd</a></p>
</div>


##### Pour en savoir plus {-}

- [Markdown](https://daringfireball.net/projects/markdown/). Explication en anglais de l'intérêt d'employer Markdown ainsi que la syntaxe à employer.

- [Rédigez en Markdown !](https://openclassrooms.com/fr/courses/1304236-redigez-en-markdown)


- [Un guide pour bien commencer avec Markdown](https://blog.wax-o.com/2014/04/tutoriel-un-guide-pour-bien-commencer-avec-markdown/)

- [Le Markdown comme langage d’écriture universel ?](https://blog.genma.fr/?Le-Markdown-comme-langage-d-ecriture-universel)

- [Comment écrire confortablement et professionnellement ? Le Markdown !](https://dolys.fr/forums/topic/comment-ecrire-confortablement-professionnellement-markdown/). Utilisation de Markdown afin de revenir à l'essence de la rédaction.

- [Écrire tout simplement – Introduction à Markdown](http://www.boiteaoutils.info/2013/02/ecrire-tout-simplement-introduction/). Pourquoi utiliser Markdown ?


### Gestionnaire de version 

Lors de la rédaction de travaux un petit peu conséquents, comme un travail de fin d'étude, une publication scientifique ou un rapport volumineux, on se retrouve rapidement avec plusieurs fichiers correspondant à des états d'avancements du travail : 

- TFE_final
- TFE_final1
- TFE_final2
- TFE_final3
- TFE_final...
- TFE_final99

Lors de différents essais, on va avoir tendance à tout garder dans différents fichiers afin de ne rien supprimer d'important. Cette pratique bien que très courante comporte le gros désavantage de prendre énormément de place sur le disque de votre ordinateur et de n'être pas pratique. Les questions suivantes peuvent se poser\ :

- Que se cache-t-il dans la version TFE_finalX ? Après un mois sans travailler sur le projet, seriez-vous encore capable de faire facilement la différence entre TFE_final2 et le TFE_final3\ ? 

- Cela se complique encore plus lorsque plusieurs personnes collaborent sur un même projet. Ils vont, par exemple, s'échanger par email différentes versions du travail avec chacun qui y place ses commentaires et modifie différentes parties du texte. Cela peut donner quelque chose comme ceci\ : 

- TFE_final
- TFE_final1
- TFE_final1_jacques
- TFE_final1_pierre
- TFE_final2
- TFE_final2_jules
- TFE_final...
- TFE_final99

Dans quel fichier se trouve la dernière version de chaque personne ayant collaboré sur le projet ? Une petit peu dans différents fichiers, sans doute. 

Différents outils informatiques existent pour faciliter le travail collaboratif comme :

- Le partage de fichiers en ligne ([Dropbox](https://www.dropbox.com/business/landing-t68fl?_tk=sem_b_goog&_camp=sem-b-goog-emea-be-fre-exact-restructure&_kw=dropbox|e&_ad=244691468861|1t1|c&gclid=CjwKCAjwzenbBRB3EiwAItS-u3vb9iSK6F4MFnw3oWaEq0gwxQk74_ekOASIah0P-9u_pYFis8hxFxoCdOIQAvD_BwE), [Google Drive](https://www.google.com/drive/), [One Drive](https://onedrive.live.com/about/fr-be/)). Ces espaces de stockage sur le "cloud" ne règlent toujours pas le problème de collaboration sur le même fichier.

- L'utilisation d'un programme d'édition collaboratif en temps réel ([Etherpad](http://etherpad.org/), [Google Drive - Docs](https://www.google.com/intl/fr_be/docs/about/), [Gobby](https://gobby.github.io/)). Il est possible de travailler en même temps sur un même fichier. Cette option ne règle pas le problème du retour vers une ancienne version. Lorsqu'une modification a été réalisée l'ancienne version est tout simplement écrasée.

- La meilleure combinaison pour gérer ses versions *et* collaborer : [Git](https://git-scm.com/) et [GitHub](https://github.com/). Ces outils sont plutôt considérés comme écrits par et pour des geeks. Cependant, ils permettent de gérer et collaborer de manière efficace sur un même projet contenant du code ou non, et des interfaces facilitant leur utilisation apparaissent comme [GitHub Desktop](https://desktop.github.com), ou même, les [outils Git intégrés dans RStudio](https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN).


#### Git

La gestion de versions est gérée par *Git*. Cet outil va remplacer les nombreuses copies d'un même fichier par une sorte d'arbre que l'on peut représenter schématiquement comme ci-dessous :

![Représentation de la gestion de fichiers via Git](images/sdd1_01/git1.png)

Comme vous pouvez le voir ci-dessus, on peut suivre la progression de notre projet via un nombre d'étapes successives représentées sur le schéma par des boules bleues. Chaque étape capture l'état de notre projet au moment où nous avons décidé de l'enregistrer. Pour enregistrer une nouvelle version de votre projet, vous réalisez un **commit** qui sera accompagné d'un message spécifiant les modifications apportées. Git comprend de nombreux outils très intéressant pour la gestion de versions que vous utiliserez par la suite.


#### GitHub

Un réseau social a été conçu autour de Git pour sauvegarder vos projets sur le "cloud", les partager et collaborer avec d'autres personnes. Ce système se nomme [GitHub](https://github.com) (tout comme Facebook ou LinkedIn). GitHub rassemble donc "Git", la gestion de version et "Hub" relatif au réseau. D'autres réseaux équivalents existent comme [Gitlab](https://about.gitlab.com) ou [Bitbucket](https://bitbucket.org), mais dans ce cours, nous utiliserons GitHub ensemble, sachant que les notions apprises ici seront réutilisables ailleurs.

Lorsque l'on travaille seul tout en utilisant GitHub, l'évolution de notre projet va ressembler à l'arbre ci-dessous : 

![Représentation des versions successives d'un projet avec GitHub.](images/sdd1_01/github.png)

On réalise un envoi (**push**) lorsque l'on souhaite synchroniser nos changements locaux avec la version sur le "cloud". Plusieurs **commit**s peuvent être envoyés avec un seul **push** sur le réseau, et c'est d'ailleurs généralement comme cela que l'on procède. L'inverse (rapatrier localement les changements que d'autres collaborateurs ont envoyé sur la version réseau de notre projet) s'appelle faire un "**pull**".

L'avantage principal de **GitHub** ne réside pas vraiment dans la possibilité de réaliser une sauvegarde en ligne mais plutôt dans la possibilité de collaborer avec d'autres personnes présentes sur ce réseau comme l'illustre la figure ci-dessous. Deux scientifiques (les versions représentées par des boules bleues et des boules vertes) collaborent sur un même projet que l'on appelle un **dépôt** (**repository** en anglais) lorsqu'il est en ligne. Le premier chercheur (boules bleues) va initier le dépôt et réaliser un "push"" pour rendre son travail accessible sur le réseau (boules oranges). Son collaborateur (boules vertes) va **clôner** (**clone** en anglais) le dépôt sur son ordinateur afin d'y travailler également en local sur son PC. Après avoir fait des changements, il réalise également un **push** sur le réseau. Le premier scientifique, avant de travailler à nouveau sur le projet, va donc réaliser un **pull** afin d'obtenir en local l'ensemble des modifications fournies par son ou ses collaborateurs, et ensuite après modifications en local il effectuera à nouveau un "pus". 

![Différentes versions d'un projet sur GitHub lorsque deux personnes différentes collaborent sur le même dépôt.](images/sdd1_01/github1.png)

Vous venez d'apprendre le B-A-BA de la terminologie nécessaire à la bonne compréhension de Git et GitHub\ :

- **repository**\ : espace de stockage sous gestion de version Git.

- **commit**\ : enregistrer une version du projet.

- **clone**\ : créer un double local d'un dépôt GitHub.

- **push**\ : envoyer ses modifications locales vers le dépôt GitHub.

- **pull**\ : rapatrier les modifications que les autres utilisateurs ont appliqué dans le dépôt GitHub vers sa propre version locale.

Ceci n'est qu'une explication très succincte. Vous trouverez plus de détails dans les liens ci-dessous et dans les Appendices. Il est, par exemple, possible de travailler sur une version en parallèle d'un dépôt original pour lequel on n'a pas de droits en écriture. Dans ce cas, il faudra faire une copie dans notre propre compte GitHub du dépôt. Cela s'appelle faire un **fork**. Il n'est pas possible de faire un **push** vers le dépôt d'origine puisqu'on n'a pas les droits en écriture. Dans ce cas, on fera un **pull request**, suggérant ainsi à l'auteur d'origine que nous avons fait des modifications qui pourraient l'intéresser. Si c'est effectivement le cas, il pourra accepter notre "pull request" et intégrer nos suggestions dans le dépôt d'origine. Vous serez amenés à "forker" des dépôts GitHub pour vos exercices, et vous effectuerez également un "pull request" lorsque vous serez suffisamment aguerris avec les autres techniques de gestion de vos projets sous Git et GitHub.


##### Pour en savoir plus {-}

- [Gérez vos codes sources avec Git](https://openclassrooms.com/fr/courses/1233741-gerez-vos-codes-source-avec-git). Explication en français sur l'utilisation de Git. 

- [Quel logiciel de gestion de versions devriez-vous utiliser ?](https://www.codebuilder.fr/blog/developpement-collaboratif-logiciels-gestion-versions/). Explication en français sur l'utilisation des logiciels de gestion de versions.

- [Git : comprendre la gestion de versions](https://blog.axopen.com/2017/02/git-comprendre-la-gestion-de-versions/). Explication en français sur ce qu'est Git et comment cela s'utilise en pratique.

- Introduction en anglais de GitHub dans RStudio à l'aide d'une [vidéo](https://www.rstudio.com/resources/webinars/rstudio-essentials-webinar-series-managing-part-2/).

- [Happy Git and GitHub for the useR](http://happygitwithr.com). Complet, mais un peu technique et en anglais.

- Installation et première utilisation de [Git et GitHub](http://r-pkgs.had.co.nz/git.html) dans R. En anglais.

- [Git](https://git-scm.com/). Site en anglais comprenant toute la documentation de Git.

- [GitHub pour les nuls : pas de panique, lancez-vous !](https://www.christopheducamp.com/2013/12/15/github-pour-nuls-partie-1/).


#### GitHub Classroom {#classroom}

**GitHub Classroom** est une extension de GitHub qui facilite le travail avec GitHub dans le contexte d'exercices à réaliser dans le cadre d'un cours. Vous serez amené à cloner et modifier des dépôts issus de GitHub Classroom pour réaliser vos exercices. **Ces dépôts seront privés**. Cela signifie que, seuls vous-mêmes et vos enseignants auront accès à ces dépôts. A la fin de la formation, tous ces dépôts seront détruits. **Donc, si vous voulez les conserver, il faudra les "forker" sur votre propre compte.** Rassurez-vous : nous vous préviendrons avant de faire le ménage ! 

*Maintenant que vous comprenez mieux avec quels outils informatiques nous allons travaillez, vous pouvez passer à votre premier exercice pour découvrir la SciViews Box, RStudio, Markdown, Git et GitHub : vous allez réaliser un site web professionnel en ligne...*


## Site web professionnel {#site}

De nos jours, un nombre important de données sont collectées via notre activité sur le web. A la fin de vos études, vous serez amenés à rechercher un travail (dans le milieu de la recherche universitaire, dans la recherche en entreprise, dans les métiers de l'éco-conseils, dans l'industrie, etc.). Tous les recruteurs utilisent actuellement les données que l'on a semé sur le net afin de réaliser un profil détaillé sur nous. Il est donc de votre intérêt d'avoir le meilleur profil possible sur Internet... et qu'il apparaisse comme à la fois sérieux, dynamique et professionnel. *Nous allons vous y aider !*

Les réseaux sociaux sont une mine d'or sur nos habitudes de vie comme Facebook, Twitter ou encore Instagram. On peut parler de l'image numérique d'une personne. Afin de mettre l'accent sur les compétences professionnelles, de plus en plus de personnes utilisent des réseaux dédiés comme [LinkedIn](https://www.linkedin.com) ou encore, ont recours à un **site web personnel professionel** (par exemple : <http://phgrosjean.sciviews.org/>, <http://www.guyliann.be/>).

Dans le cadre de ce premier module, vous allez réaliser votre premier site web professionnel (contenant également une section "blog" que vous pourrez alimenter, entre autres, avec vos considérations concernant vos cours, les analyse de données, et autres, ...). Ce site sera immédiatement disponible sur le web et ce, de manière entièrement gratuite ! Afin de mener à bien ce premier projet, divers outils vous seront nécessaires. Ces outils seront complétés plus tard par d'autres pour que vous ayez une boite à outils complète pour vos futures analyses de données dans un contexte professionnel.


##### A vous de jouer {-}

<div class="bdd">
<p>Maintenant que vous avez appréhendé les différents outils, lancez vous dans la création de votre site web professionnel via l’adresse suivante : <a href="https://github.com/BioDataScience-Course/blogdown.source" class="uri">https://github.com/BioDataScience-Course/blogdown.source</a>. Les instructions détaillées sont dans le fichier <code>README.md</code> sur ce dépôt.</p>
</div>

Lorsque vous éditez votre site blogdown, faites attention à ceci :

- Hugo (le logiciel qui compile le site Web) n'est pas très tolérant. Vous **devez** respecter la syntaxe qu'il impose. Faites attention aux détails, comme les **virgules** indispensables pour séparer les items dans une liste. Par exemple, dans la liste `[interests]` qui apparaît dans `content/home/about.md`, si vous ajoutez des items comme ceci, Hugo ne compilera plus le site correctement.
    ```
      interests = [
        "Biology",
        "Ecology"
        "Movies"
      ]
    ```
    Tous les items doivent être séparés par une virgule, ce qui n'est pas le cas de `"Ecology"` et `"Movies"`. La forme correcte est présentée ci-dessous :
    ```
      interests = [
        "Biology",
        "Ecology",
        "Movies"
      ]
    ```

- **Ne cliquez pas sur le bouton `Preview`** lorsque vous éditez un fichier `.md`. Normalement dans RStudio, c'est effectivement avec ce bouton qu'on obtient une visualisation du rendu final du document. Mais avec blogdown, il *faut* passer par `Addins -> BLOGDOWN -> Serve Site`. De plus, si vous avez cliqué sur `Preview`, le fichier `.html` généré peut empêcher la bonne construction du site. Donc, **effacez tous les fichiers `.html` correspondant aux `.md` présents dans un sous-dossier de `content`**.

- S'il vous semble que la compilation du site est bloquée, redémarrez R. Dans le menu de RStudio, faites `Session -> Restart R`, ensuite relancez la compilation du site avec `Addins -> BLOGDOWN -> Serve Site`. Traquez un message d'erreur éventuel qui apparaîtrait dans l'onglet `Console`, et sinon, vérifiez la syntaxe dans `config.toml`, les entêtes de tous les fichiers `.md`, ainsi que l'absence de fichiers `.html`associés.

- N'oubliez pas de "commiter" vos changements à partir de l'onglet `Git` dans RStudio. A ce stade, vous avez mis à jour les **sources** de votre site, mais pas votre site lui-même. Pour mettre à jour votre site en ligne, il faut aussi "commiter" les changements dans `<your_login>.github.io`. Ouvrez ce dernier dépôt dans `Github Desktop` et effectuez-y un "commit". Ensuite, naviguez vers `http://<your_login>.github.io` pour vérifier ce qui apparaît en ligne. Attention, il se peut que le cache du navigateur ou d'un routeur vous renvoie encore une ancienne version. Rafraîchissez la page deux ou trois fois pour voir apparaître la dernière version de votre oeuvre.


##### Pour en savoir plus {-}

- Le [manuel de blogdown](https://bookdown.org/yihui/blogdown/) (en anglais).

- Des [exemples de sites web](https://awesome-blogdown.com) réalisés avec blogdown.
