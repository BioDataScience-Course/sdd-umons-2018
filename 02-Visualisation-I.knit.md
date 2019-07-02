# Visualisation I {#visu1}




##### Objectifs {-}

- Découvrir --et vous émerveiller de--  ce que l'on peut faire avec le [logiciel R](http://www.r-project.org) [@R-base]

- Savoir réaliser différentes variantes d'un graphique en nuage de points dans R avec la fonction `chart()`

- Découvrir le format R Markdown [@R-rmarkdown] et la recherche reproductible

- Intégrer ensuite des graphiques dans un rapport et y décrire ce que que vous observez

- Comparer de manière critique un flux de travail "classique" en biologie utilisant Microsoft Excel et Word avec une approche utilisant R et R Markdown\ ; Prendre conscience de l'énorme potentiel de R


##### Prérequis {-}

Si ce n'est déjà fait, vous devez installer et vous familiariser avec la 'SciViews Box', RStudio, Markdown. Vous devez aussi maîtriser les bases de Git et de GitHub (avoir un compte GitHub, savoir cloner un dépôt localement, travailler avec GitHub Desktop pour faire ses "commits", "push" et "pull"). L'ensemble de ces outils a été abordé lors de la création de votre site personnel professionnel du module \@ref(intro).

<iframe src="https://h5p.org/h5p/embed/453026" width="780" height="270" frameborder="0" allowfullscreen="allowfullscreen"></iframe><script src="https://h5p.org/sites/all/modules/h5p/library/js/h5p-resizer.js" charset="UTF-8"></script>

Avant de poursuivre, vous allez devoir découvrir les premiers rudiments de R afin de pouvoir réaliser par la suite vos premiers graphiques. Pour cela, vous aurez à lire attentivement et effectuer tous les exercices de deux tutoriels^[Reportez-vous à l'Appendice \@ref(learnr) pour apprendre à utiliser ces tutoriels.].

\BeginKnitrBlock{bdd}<div class="bdd">Démarrez la SciViews Box et RStudio. Dans la fenêtre **Console** de RStudio, entrez l'instruction suivante suivie de la touche `Entrée` pour ouvrir le tutoriel concernant les bases de R :

    BioDataScience::run("02a_base")

Ensuite, vous pouvez également parcourir le tutoriel qui vous permettra de découvrir R sur base d'une analyse concrète (cliquez dans la fenêtre **Console** de RStudio et appuyez sur la touche `ESC` pour reprendre la main dans R à la fin d'un tutoriel) :

    BioDataScience::run("02b_decouverte")

([BioDataScience](https://github.com/BioDataScience-Course/BioDataScience) est un package R spécialement développé pour ce cours et que vous avez dû installer lors de la configuration de votre SciViews Box, voir Appendice \@ref(install-tuto)).</div>\EndKnitrBlock{bdd}


## Nuage de points

Dès que vous vous sentez familiarisé avec les principes de base de R, vous allez pouvoir réaliser assez rapidement des beaux graphiques. Par exemple, si vous souhaitez représenter une variable numérique en fonction d'une autre variable numérique, vous pouvez exprimer cela sous la forme d'une **formule**^[Dans R, une **formule** permet de spécifier les variables avec lesquelles on souhaite travailler, et leur rôle. Par exemple ici, la variable _x_ sur l'axe des abscisses et la variable _y_ sur l'axe des ordonnées.]

$$y \sim x$$

que l'on peut lire "y en fonction de x". Pour les deux variables numériques _x_ et _y_, la représentation graphique la plus classique est le **nuage de points** (voir Fig. \@ref(fig:first-scatterplot) pour un exemple).


























