--- 
title: "Science des données biologiques, UMONS"
author: "Philippe Grosjean & Guyliann Engels"
date: "2019-07-02"
site: bookdown::bookdown_site
output:
  bookdown::gitbook:
    includes:
      after_body: disqus.html
documentclass: book
bibliography: [book.bib, packages.bib]
biblio-style: apalike
link-citations: yes
github-repo: biodatascience-course/sdd-umons
url: 'http\://biodatascience-course.sciviews.org/sdd-umons/'
description: "Tutoriel interactif pour la science des données avec R & SciViews-R."
cover-image: "images/front-cover.png"
---

# Préambule {-}




Cet ouvrage couvrira, à terme, la matière des cinq cours de science des données enseignés aux biologistes de la Faculté des Sciences de l'Université de Mons (Belgique). La matière sera complétée progressivement à partir du premier cours prévu pour l'année académique 2018-2019.

Cet ouvrage est conçu pour être utilisé de manière interactive en ligne. En effet, nous prévoyons d'y adjoindre des capsules (unités d'enseignement ciblant un et un seul concept) sous forme de vidéos, des démonstrations interactives, et des exercices sous forme de questionnaires interactifs également. **Ces différents éléments ne sont, bien évidemment, utilisables qu'en ligne.**

![](images/front-cover.png)


## Vue générale du cours {-}

Le premier cours intitulé **Science des données I: visualisation et inférence** qui est dispensé aux biologistes de second Bachelier en Faculté des Sciences de l'Université de Mons à partir de l'année académique 2018-2019 contient 25h de cours et 50h d'exercices en presentiel. Il nécessitera environ un tiers de ce temps (voir plus, en fonction de votre rythme et de votre technique d'apprentissage) en travail à domicile.

Cette matière est divisée en 12 modules de sessions de 6h chacune en présentiel. **Une première séance de 2h précèdera ces 12 modules afin d'installer les logiciels (SciViews Box, R, RStudio, Github Desktop), et de se familiariser avec eux.**

<!--html_preserve--><div id="htmlwidget-f0468e89fbe2013ca903" style="width:600px;height:600px;" class="grViz html-widget"></div>
<script type="application/json" data-for="htmlwidget-f0468e89fbe2013ca903">{"x":{"diagram":"\ndigraph general_flow {\n  graph [rankdir = \"TB\", overlap = true, compount = true, fontsize = 10]\n  \n  node [shape = box,\n        fontname = Helvetica,\n        style = filled,\n        fillcolor = LightSteelBlue,\n        fixedsize = true,\n        width = 2]\n  \"1 Introduction\"; \"12 Design/critique\"\n  \n  subgraph cluster_0 {\n    style = filled;\n    color = lightgrey;\n    node [style = filled, color = red];\n    \"2 Visualisation I\"->\"3 Visualisation II\"\n    \"2 Visualisation I\"->\"4 Visualisation III\"\n    label = \"Visualisation & description des données\";\n    color = lightgray\n  }\n  \n  subgraph cluster_1 {\n    style = filled;\n    color = lightgrey;\n    node [style = filled, color = blue];\n    \"5 Quantitatif\"->\"6 Qualitatif\"\n    label = \"Importation & transformation des données\";\n    color = lightgray\n  }\n  \n  subgraph cluster_2 {\n    style = filled;\n    color = lightgrey;\n    node [style = filled, color = green];\n    \"7 Probabilités\"->\"8 Test Chi2\"\n    \"7 Probabilités\"->\"9 IC/t-test\"\n    \"8 Test Chi2\"->\"9 IC/t-test\"\n    \"9 IC/t-test\"->\"10 ANOVA\"\n    \"10 ANOVA\"->\"11 Correlation\"\n    label = \"Inférence & hypothèses\";\n    color = lightgray\n  }\n\n  \"1 Introduction\"->\"2 Visualisation I\" [lhead = cluster_0]\n  \"2 Visualisation I\"->\"5 Quantitatif\" [lhead = cluster_1]\n  \"3 Visualisation II\"->\"7 Probabilités\" [lhead = cluster_2]\n  \"4 Visualisation III\"->\"7 Probabilités\" [lhead = cluster_2]\n  \"6 Qualitatif\"->\"7 Probabilités\" [lhead = cluster_2]\n  \"11 Correlation\"->\"12 Design/critique\"\n}\n","config":{"engine":"dot","options":null}},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->


## Matériel pédagogique {-}

Le matériel pédagogique, rassemblé dans ce syllabus interactif est aussi varié que possible. Vous pourrez ainsi piocher dans l'offre en fonction de vos envies et de votre profil d'apprenant pour optimiser votre travail. Vous trouverez:

- le présent ouvrage en ligne,

- des capsules, essentiellement sous forme de vidéos < 10 min qui ciblent chacune un concept particulier (en cours de développement),

- des tutoriaux interactifs (réalisés avec un logiciel appelé `learnr`). Vous pourrez exécuter ces tutoriaux directement sur votre ordinateur, et vous aurez alors accès à des pages Web réactives contenant des explications, des exercices et des quizzs en ligne,

- des slides de présentations,

- des dépôts Github Classroom dans la section `BioDataScience-Course` (vous apprendrez ce que c'est très rapidement dès le premier module) pour réaliser et documenter vos travaux personnels.

- des renvois vers des documents externes en ligne, types vidéos youtube ou vimeo, des ouvrages en ligne en anglais ou en français, des blogs, des tutoriaux, des parties gratuites de cours Datacamp ou équivalents, des questions sur des sites comme "Stackoverflow" ou issues des "mailing lists" R, ...

<div class="info">
<p>Tout ce matériel est accessible à partir du <a href="http://biodatascience-course.sciviews.org">site Web du cours</a>, du présent syllabus interactif (et de Moodle pour les étudiants de l’UMONS). Ces derniers ont aussi accès au dossier <code>SDD</code> sur <code>StudentTemp</code> en Intranet à l’UMONS. Les aspects pratiques seront à réaliser en utilisant la <strong>‘SciViews Box’</strong>, une machine virtuelle préconfigurée que nous installerons ensemble lors du premier cours<a href="#fn1" class="footnote-ref" id="fnref1"><sup>1</sup></a>. Il vous faudra donc avoir accès à un ordinateur (sous Windows, MacOS, ou Linux peu importe, suffisamment puissant et connecté à Internet ou à l’Intranet UMONS). Enfin, vous pourrez poser vos questions par mail à l’adresse <code>sdd@sciviews.org</code>.</p>
<div class="footnotes">
<hr />
<ol>
<li id="fn1"><p>Il est donc très important que vous soyez présent à ce cours, et vous pouvez venir aussi si vous le souhaitez avec votre propre ordinateur portable.<a href="#fnref1" class="footnote-back">↩</a></p></li>
</ol>
</div>
</div>


## Comment apprendre? {-}


```r
fortunes::fortune("brain surgery")
```

```
# 
# I wish to perform brain surgery this afternoon at 4pm and don't know where
# to start. My background is the history of great statistician sports
# legends but I am willing to learn. I know there are courses and numerous
# books on brain surgery but I don't have the time for those. Please direct
# me to the appropriate HowTos, and be on standby for solving any problem I
# may encounter while in the operating room. Some of you might ask for
# specifics of the case, but that would require my following the posting
# guide and spending even more time than I am already taking to write this
# note.
#    -- I. Ben Fooled (aka Frank Harrell)
#       R-help (April 1, 2005)
```

Version courte: **en pratiquant, en faisant des erreurs !**

Version longue: aujourd'hui --et encore plus à l'avenir-- les données sont complexes et ne se manipulent plus simplement avec un tableur comme Microsoft Excel. Vous allez apprendre à maitriser des outils professionnels, ce qui sous-entend qu'ils sont très puissants mais aussi relativement complexes. La méthode d'apprentissage que nous vous proposons a pour objectif prioritaire de vous faciliter la tâche, quelles que soient vos aptitudes au départ. Envisagez votre voyage en science des données comme l'apprentissage d'une nouvelle langue. **C'est en pratiquant, et en pratiquant encore sur le long terme que vous allez progresser.** La formation s'étale sur quatre années, et est répartie en cinq cours de difficulté croissante pour vous aider dans cet apprentissage progressif et sur la durée. N'hésitez pas à expérimenter, tester, essayer des nouvelles idées (même au delà de ce qui sera demandé dans les exercices) et **n'ayez pas peur de faire des erreurs**. Vous en ferez, ... beaucoup ... _nous vous le souhaitons!_ En fait, la meilleure manière d'apprendre, c'est justement en faisant des erreurs, et puis en mettant tout en oeuvre pour les comprendre et les corriger. Donc, si un message d'erreur, ou un "warning" apparait, ne soyez pas intimidé. Prenez une bonne respiration, lisez-le attentivement, essayez de le comprendre, et au besoin faites-vous aider: la solution est sur le Net, 'Google^[Il existe tout de même des outils plus pointus pour obtenir de l'aide sur le logiciel R comme [rseek.org](https://rseek.org), [rdocumentation.org](https://www.rdocumentation.org) ou [rdrr.io](https://rdrr.io). Rien ne sert de chercher 'R' dans Goggle.] est votre ami'!


## Evaluation {-}

L'évaluation sera basée sur une somme de petites contributions qui matérialiseront votre progression sur le long terme. Avec cette évaluation, nous souhaitons vous gratifier chaque fois que vous franchirez des étapes, plutôt que de vous sanctionner lorsque vous bloquez. Donc, pour une note finale sur 20:

<!-- - 2 points pour la progression sur base des exercices que vous réaliserez en classe inversée (donc, chez vous). -->

- 3 points pour la restitution des capsules et votre participation en présentiel. Au début de chaque séance, nous discuterons des notions que vous aurez à préparer par avance, et votre participation sera évaluée.

- 6 points pour un quizz final.

<!-- : vous aurez à répondre à cinq questions au hasard (set différent pour chaque étudiant sur base de 20 questions au total). -->

- 11 points pour l’évaluation d’un des rapports d'analyse de données (choisi au hasard en fin de cours).

- Enfin, vous pourrez éventuellement encore gagner un point bonus pour une participation remarquable, ou tout autre élément à valoriser (site web personnel et/ou blog exceptionnel, aide des autres étudiants, etc.). Ceci étant à l'appréciation des enseignants.

----

_Le matériel dans cet ouvrage est distribué sous licence [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.fr)._

----

##### System information {-}


```r
sessioninfo::session_info()
```

```
# ─ Session info ──────────────────────────────────────────────────────────
#  setting  value                       
#  version  R version 3.4.4 (2018-03-15)
#  os       macOS  10.14.5              
#  system   x86_64, darwin15.6.0        
#  ui       X11                         
#  language (EN)                        
#  collate  en_US.UTF-8                 
#  ctype    en_US.UTF-8                 
#  tz       Europe/Brussels             
#  date     2019-07-02                  
# 
# ─ Packages ──────────────────────────────────────────────────────────────
#  package      * version    date       lib
#  assertthat     0.2.1      2019-03-21 [1]
#  bindr          0.1.1      2018-03-13 [1]
#  bindrcpp       0.2.2      2018-03-29 [1]
#  bookdown       0.10       2019-05-10 [1]
#  brew           1.0-6      2011-04-13 [1]
#  cli            1.1.0      2019-03-19 [1]
#  codetools      0.2-15     2016-10-05 [1]
#  colorspace     1.4-0      2019-01-13 [1]
#  crayon         1.3.4      2017-09-16 [1]
#  DiagrammeR     1.0.0      2018-03-01 [1]
#  digest         0.6.18     2018-10-10 [1]
#  downloader     0.4        2015-07-09 [1]
#  dplyr          0.7.8      2018-11-10 [1]
#  evaluate       0.13       2019-02-12 [1]
#  fortunes       1.5-4      2016-12-29 [1]
#  ggplot2        3.1.1      2019-04-07 [1]
#  glue           1.3.1.9000 2019-05-15 [1]
#  gridExtra      2.3        2017-09-09 [1]
#  gtable         0.2.0      2016-02-26 [1]
#  hms            0.4.2      2018-03-10 [1]
#  htmltools      0.3.6      2017-04-28 [1]
#  htmlwidgets    1.3        2018-09-30 [1]
#  igraph         1.2.2      2018-07-27 [1]
#  influenceR     0.1.0      2015-09-03 [1]
#  jsonlite       1.6        2018-12-07 [1]
#  knitr          1.22       2019-03-08 [1]
#  lazyeval       0.2.1      2017-10-29 [1]
#  magrittr       1.5        2014-11-22 [1]
#  munsell        0.5.0      2018-06-12 [1]
#  pillar         1.3.1      2018-12-15 [1]
#  pkgconfig      2.0.2      2018-08-16 [1]
#  plyr           1.8.4      2016-06-08 [1]
#  purrr          0.2.5      2018-05-29 [1]
#  R6             2.4.0      2019-02-14 [1]
#  RColorBrewer   1.1-2      2014-12-07 [1]
#  Rcpp           1.0.1      2019-03-17 [1]
#  readr          1.2.1      2018-11-22 [1]
#  rgexf          0.15.3     2015-03-24 [1]
#  rlang          0.3.4.9003 2019-05-15 [1]
#  rmarkdown      1.12       2019-03-14 [1]
#  Rook           1.1-1      2014-10-20 [1]
#  rstudioapi     0.9.0      2019-01-22 [1]
#  scales         1.0.0      2018-08-09 [1]
#  sessioninfo    1.1.1      2018-11-05 [1]
#  stringi        1.4.3      2019-03-12 [1]
#  stringr        1.4.0      2019-02-10 [1]
#  tibble         2.0.1      2019-01-12 [1]
#  tidyr          0.8.2      2018-10-28 [1]
#  tidyselect     0.2.5      2018-10-11 [1]
#  viridis        0.5.1      2018-03-29 [1]
#  viridisLite    0.3.0      2018-02-01 [1]
#  visNetwork     2.0.4      2018-06-14 [1]
#  withr          2.1.2      2018-03-15 [1]
#  xfun           0.7        2019-05-14 [1]
#  XML            3.98-1.16  2018-08-19 [1]
#  yaml           2.2.0      2018-07-25 [1]
#  source                             
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.0)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.1)                     
#  CRAN (R 3.4.3)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.0)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.0)                     
#  CRAN (R 3.4.4)                     
#  Github (tidyverse/glue@ea0edcb)    
#  CRAN (R 3.4.1)                     
#  CRAN (R 3.4.0)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.0)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.0)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.2)                     
#  CRAN (R 3.4.0)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.0)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.0)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.0)                     
#  Github (tidyverse/rlang@6a232c0)   
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.0)                     
#  Github (rstudio/rstudioapi@aa6cdb0)
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.3)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
#  CRAN (R 3.4.4)                     
# 
# [1] /Library/Frameworks/R.framework/Versions/3.4/Resources/library
```
