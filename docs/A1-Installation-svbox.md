# (APPENDIX) Appendices {-}


# Installation de la SciViews Box {#svbox}

<img src="images/sdd1_01/svBox-256.png" width="256px" style="display: block; margin: auto 0 auto auto;" />

La SciViews Box est une machine virtuelle (c'est-à-dire, l'équivalent d'un ordinateur complet, mais "dématérialisé" et utilisable à l'intérieur de n'importe quel autre ordinateur physique). Elle est spécialement configurée pour analyser des données et rédiger des documents scientifiques de manière professionnelle.

<iframe width="770" height="433" src="http://www.youtube.com/embed/yIVXjl4SwVo?rel=0" frameborder="0" allowfullscreen></iframe>

Dans notre cas, le logiciel de gestion de la machine virtuelle, l'hyperviseur, est **VirtualBox**. C'est un logiciel gratuit qui existe pour Windows, MacOS et la plupart des systèmes Linux. L'avantage d'utiliser une machine virtuelle dans le contexte qui nous concerne ici est double :

1) Elle est **complètement pré-configurée et pré-testée**.

2) Comme tout le monde utilise la même machine virtuelle, les résultats obtenus chez l'un sont parfaitement **reproductibles** chez d'autres.

L'installation est simple, mais il y a quand même quelques pièges. Suivez le guide...


## Prérequis

> Avant d'installer la SciViews Box 2018, vérifiez que votre ordinateur répond aux conditions requises et qu'il est correctement configuré.


### Ordinateur {#ordi}

La SciViews Box 2018, et la Science des Données en général, nécessitent un ordinateur ayant une puissance de calcul suffisante. Les tablettes et autres chromebooks sont donc exclus (sauf à être utilisés comme simples browsers web avec les calculs déportés sur un serveur, voir par exemple [Chromebook Data Science](https://simplystatistics.org/2018/10/01/chromebook-data-science-an-online-data-science-program-for-anyone-with-a-web-browser/)). Si l'utilisation d'un serveur est une bonne idée pour l'apprentissage, ce n'est pas une solution sur le long terme pour tout le monde. En effet, vous êtes et restez dépendant du serveur que l'on a bien voulu configurer et partager avec vous (sera-t-il encore disponible après votre cours, par exemple ?). La solution proposée avec la SciViews Box vous rend complètement **autonome** dès le départ. Le choix d'un ordinateur ayant une capacité de calcul suffisante n'est pas aisé et les disparités en matière de performances sont énormes, voir [NovaBench CPU score](https://novabench.com/parts/cpu?all=true).

<div class="info">
<p>La <strong>configuration de référence</strong> est la suivante, avec un <a href="https://novabench.com/results">score global Novabench</a> d’environ 1000 :</p>
<ul>
<li>Processeur : à 2 ou 4 coeurs / 4 threads d’une vitesse de calcul suffisante (<a href="https://novabench.com/parts/cpu?all=true">score CPU Novabench</a> d’environ 500).</li>
<li>Mémoire vive : 8Go avec un score RAM Novabench d’environ 200.</li>
<li>Disque dur : disque rapide SSD de 256Go (<a href="https://novabench.com/parts/storage">score disque Novabench</a> d’environ 75 avec vitesse d’écriture &gt;= 300Mo/s et vitesse de lecture &gt;= 400Mo/s).</li>
<li>Affichage : 1920x1080 ou mieux. La plupart des cartes graphiques ou des coprocesseurs graphiques intégrés conviennent (pas besoin d’une bête de course si vos calculs ne nécessitent pas des instructions GPU, en tous cas). Comme base, nous considèrerons un <a href="https://novabench.com/parts/gpu?all=true">score GPU NovaBench</a> d’environ 200 qui correspond au processeur graphique intégré Intel HD 620.</li>
<li>Réseau : Wifi à la norme 802.11ac.</li>
<li>Connectique : USB 3.0 ou C pour ajouter des périphériques, HDMI ou DisplayPort pour connecter un écran externe, et une prise casque pour visionner des vidéos sans déranger les voisins.</li>
<li>Portabilité et autonomie : 13 pouces pour un poids &lt; 1,5kg pour un ordinateur à enmener partout, sinon 15 pouces et un poids &lt;= 2kg. Autonomie d’au moins 5 à 6h.</li>
<li>Système d’exploitation : récent et si possible 64-bit. Windows 7 ou plus convient (mais pensez à mettre-à-jour vers Windows 10), MacOS 10.10 Yosemite ou plus, ou un Linux tel Debian 8 (Jessie) ou 9 (Stretch), Ubuntu 16.04 Xenial ou supérieur, …</li>
<li>Une configuration “standard” avec au moins 20Go de libre pour la SciViews Box (nécessairement sur le disque <strong>C:</strong> sous Windows), et une configuration non bidouillée (répertoire utilisateur et programmes standards, entre autres).</li>
</ul>
</div>

Pour une **configuration de base**, vous pouvez aller jusqu'à diviser les scores Novabench et les valeurs (nombre de coeurs CPU, taille de la mémoire vive et du disque) par deux, et pour une **configuration performante**, multipliez-les par deux, et ajoutez-y éventuellement une carte graphique Nvidia performante pour des calculs GPU et un second disque de 1To pour stocker des gros jeux de données. Un "laptop" (ordinateur portable) est mieux, mais si vous n'avez pas besoin d'une solution nomade, un "desktop" convient aussi et est plus modulable. Pour tester votre système, nous vous proposons donc d'utiliser le logiciel gratuit pour un usage personnel [Novabench](https://novabench.com/download#personal). Vous obtiendrez un rapport, voir ci-dessous un résultat pour un PC en configuration de référence ([Asus Zenbook UX330U](https://www.lesnumeriques.com/ordinateur-portable/asus-zenbook-ux303ua-r4098t-p30911/test.html)) et un Mac en configuration optimale [MacBook Pro 15 pouces mid-2015](https://www.lesnumeriques.com/ordinateur-portable/macbook-pro-retina-15-2-5-ghz-2015-p26477/test.html). Vous pourrez comparer à la configuration de référence :

![](images/annexe_a1/Asus_Zenbook_UX330U_novabench.png)

![](images/annexe_a1/novabench.png)


### Activation de la virtualisation

La virtualisation fait appel à un jeu d'instructions disponible sur pratiquement tous les processeurs modernes (Intel VT-x ou AMD-v). Malheureusement, elle est désactivée par défaut sur quasi tous les PC (mais les Macs sont, eux, configurés correctement en sortie d'usine). Tant que ces instructions de virtualisation ne seront pas activées, le programme d'installation de la SciViews Box va bloquer avec le message suivant:

<center>

![](images/annexe1/msg_no-virtualization.png)

</center>

Même si vous arriviez à l'installer quand même, vous ne pourriez pas la démarrer, et verriez juste le message suivant (issu de la version précédente de la SciViews Box):

<center>

![](images/annexe1/msg_no-virtualization2.png)

</center>

Pour activer ce jeu d'instructions, il faut aller dans le **BIOS**, c'est-à-dire, le petit programme qui démarre votre ordinateur. Il n'y a malheureusement pas de recette unique car chaque constructeur a sa propre façon de faire. De plus, l'endroit où il faut aller dans les menus de configuration du BIOS diffère aussi d'un ordinateur à l'autre. Cependant, la procédure générale est la suivante:

- Redémarrer l'ordinateur,
- Au tout début du démarrage, il faut appuyer sur une touche ou une combinaison de touches (par exemple, `DEL`, `F2`, ...). Restez à l'affût d'un message furtif qui l'indique à l'écran,
- Une fois entré dans le BIOS, repérez l'entrée correspondant au jeu d'instructions de virtualisation. Vous aurez plus de chances en regardant dans le menu relatif au processeur, ou dans les options avancées. Recherchez une entrée de type "Virtualisation", "Intel Virtual Technology", ou "Instructions AMD-v". Activez cette option (cela n'aura aucun effet sur les logiciels que vous avez installés jusqu'ici et qui n'utilisent pas cette fonction),
- Sortez du BIOS en sauvegardant les modifications (suivez les instructions à l'écran),
- Redémarrez l'ordinateur.

![](images/annexe1/bios-virtualisation.jpg)

Si vous n'arrivez pas à entrer dans le BIOS, ou à trouver l'entrée correspondante dans celui-ci, rechercher "BIOS Virtualization" accompagné de la marque et du modèle de votre ordinateur dans votre moteur de recherche internet favori. Vous y trouverez certainement des instructions plus précises relatives à votre ordinateur. [Ce site](https://www.tactig.com/enable-intel-vt-x-amd-virtualization-pc-vmware-virtualbox/) liste quelques uns de raccourcis claviers à utiliser en fonction de la marque des ordinateurs pour entrer dans le BIOS.

<div class="info">
<p>Dans le cas où vous n’arrivez pas à activer la virtualisation sur votre PC, vous pouvez toujours installer une version 32-bit de la SciViews Box en mode d’émulation logicielle de VirtualBox. Dans ce cas, votre box tournera plus lentement et vous n’aurez pas la possibilité d’utiliser plus d’un seul coeur processeur, mais au moins, vous pourrez quand même l’utiliser. La version 64-bit “complète” se nomme <code>svbox2018a</code>. La version 32-bit est <code>svbox2018b</code>. Si vous optez pour cette dernière, adaptez l’intitulé de la machine ou des fichiers (<code>a</code>-&gt; <code>b</code>) dans la suite de ce tutoriel.</p>
</div>

**Si votre ordinateur est conforme aux spécifications ci-dessus, et si la virtualisation est activée, vous êtes maintenant prêt à installer votre SciViews Box!** Dans ce cas, passez directement à la section \@ref(install). Si vous n'avez pas encore d'ordinateur et souhaitez en acheter un, voyez quelques conseils utiles ci-dessous pour faire le bon choix.


### Conseils pour acheter un PC {#achat_pc}

<div class="note">
<p>Pour les étudiants de l’UMONS, vous ne <em>devez pas</em> posséder votre propre ordinateur pour suivre le cours de science des données biologiques. Des ordinateurs en configuration de référence (voir <a href="#ordi">ordinateur</a>) vous sont accessibles au cours et aux travaux pratiques, et en dehors des heures à la salle “Escher” (demander un accès au secrétariat des sciences). Toutefois, si vous pouvez acquérir un ordinateur personnel, cela vous apportera un confort et une flexibilité indéniable, <strong>à condition de bien le choisir !</strong></p>
</div>

Si vous suivez les directives ci-dessus, vous ne pourrez pas vous tromper. Mais comme vous n'aurez probablement pas la possibilité de tester les ordinateurs avec Novabench avant l'achat, voici quelques exemples de configurations types et leur coûts approximatifs.

> Attention : cette analyse est réalisée en octobre 2018. Le matériel informatique et les prix changent constamment, et les informations seront rapidement obsolètes. Les lignes directrices devraient, cependant rester valables à l'avenir pour utiliser la SciViews Box 2018.

L'élément le plus important étant la vitesse de calcul du processeur, obtenez la référence du processeur de l'ordinateur que vous convoitez et recherchez-le [ici](https://novabench.com/parts/cpu?all=true). Comparer alors son score à notre configuration de référence, et faites-en de même pour les autres caractéristiques (mémoire vive, type et taille du disque dur, etc.)

Prenez aussi comme référence les ordinateurs de votre salle de travaux pratiques. A l'UMONS, dans la salle "Pentagone", les ordinateurs sont équipés d'Intel Core i5-6400T @ 2.20Ghz. Ce sont des processeurs 4 coeurs/4 threads avec un score CPU Novabench de 511. Ils possèdent également 8Go de mémoire vive, un disque dur SDD avec 190Go dédiés à Windows 10 64-bit, et un processeur graphique intégré qui affiche 1920x1080 pixels à l'écran. Aux salles "Escher" et "Turing", ce sont des processeurs Intel Core i5-4590 @ 3.30Ghz, également 4 coeurs/4 threads affichant un score CPU Novabench de 515. Le reste de leurs configurations est similaire à celle des ordinateurs "Pentagone". **Vous pouvez également vous baser sur d'autres tests, les CPUMarks et comparer le processeur de l'ordinateur que vous voulez acheter avec les scores de vos machines des salles de travaux pratiques à partir de [cette page](https://www.cpubenchmark.net/compare/Intel-i5-4590-vs-Intel-i5-6400T/2234vs2668).**

Dans le choix de votre ordinateur, il faut tout d'abord vous demander si vous voulez un ordinateur pour **apprendre** à traiter des données sur des petits tableaux, et que vous prévoyez changer dans 1 ou 2 ans (dans ce cas, une configuration de base convient), ou si vous voulez investir sur plus long terme. Visez alors plus haut. Naturellement, le prix sera un critère fondamental, également^[Renseignez-vous au niveau des services étudiants à l'UMONS et à l'AGE : des aides existent pour les étudiants boursiers qui souhaitent acquérir un ordinateur dans le cadre de leurs études.].

Justification des besoins :

- **Processeur :** l'élément le plus important. Un processeur puissant et multitâche est indispensable. Il vous faut au moins 2 coeurs et 4 threads (selon les modèles, chaque coeur peut gérer une seule tâche -ou "thread" en anglais- ou deux). Un processeur 4 coeurs/4 threads est encore mieux, et à partir de 4 coeurs/8 threads, c'est parfait. Pour la vitesse de calcul, comme indiqué plus haut, un score CPU Novabench de 500 ou mieux, ou un CPUMark de 5000 ou mieux doit être visé pour une configuration de référence ou performante. Avec un score moitié moindre, c'est encore un processeur utilisable, mais ne descendez pas en dessous pour une configuration de base.

- **Mémoire vive :** il vous faut suffisamment de mémoire pour la partager entre la machine hôte et la machine virtuelle, et garder assez de resources pour ouvrir des tableaux (moyennement) volumineux. Donc, **visez 8Go de mémoire vive** si possible. Pas moins de 4Go, et plus vous en avez, mieux c'est. Il existe des configurations laptops à 16Go. C'est utile !

- **Disque dur :** ici, vous devrez peut-être faire un choix entre espace de stockage et vitesse du disque. En effet, les disques mécaniques classiques font maintenant facilement 1To, ce qui est confortable. Par contre, ils sont plus lents que les disques SSD qui sont à privilégier. Mais ces derniers sont de capacité moindre (dans des gammes de prix raisonnables), généralement 128Go ou 256Go. Des configurations plus haut de gamme combinent deux disques : un SSD rapide pour le système et un disque de 1To classique pour les données. **C'est l'idéal.** Si vous investissez dans un ordinateur ayant un disque dur SSD rapide mais pas assez gros pour contenir vos nombreux fichiers, photos, vidéos, morceaux de musique, etc., vous pourrez toujours compléter votre configuration avec un **disque dur de 1To externe** USB 3.0 pour une cinquantaine d'euros. Pensez aussi à investir dans une **clé USB de 8 ou 16Gb** pour transférer vos données. Faites attention de bien choisir un **modèle USB 3.0** reconnaissable à son connecteur bleu, infiniment plus rapide qu'un modèle USB 2.0. Il vous en coutera une dizaine d'euros.

- **Carte graphique et écran :** la qualité de la carte graphique est moins importante ici. La plupart des configurations actuelles conviennent. Voyez plutôt la taille (et donc, le poids) qui est un critère important pour un ordinateur portable. Voulez-vous un PC de 13 ou 14 pouces plus compact et transportable, ou un 15 à 17 pouces plus confortable, mais plus lourd? Pour la résolution d'écran, ne descendez pas en dessous de 1400x900 pixels pour un travail confortable (RStudio affiche plusieurs fenêtres côte-à-côte), et vérifiez visuellement si la qualité de l'écran vous convient.

- **Wifi et accessoires:** une bonne connexion Wifi sera nécessaire pour vous connecter à Internet. La norme WiFi 802.11ac est idéale. Enfin, vérifiez les connexions proposées : USB rapide (3.0, 3.1 ou C), Thunderbold, DisplayPort, HDMI, etc. pour connecter des périphériques et des écrans externes, lecteur de cartes éventuel, etc.

**D'autres critères comme la qualité de construction, la robustesse, la qualité du clavier et du trackpad éventuel, l'autonomie pour un portable, ... sont importants.** Pensez à consulter les tests détaillés effectués par des pros avant de vous décider, par exemple, [les numériques](https://www.lesnumeriques.com) en français, [PCMag](https://www.pcmag.com/article2/0,2817,1623917,00.asp) ou [techradar](https://www.techradar.com) en anglais.

Voici quelques configurations types qui conviennent, volontairement choisies chez différents constructeurs pour ne privilégier personne. Dans le cadre de vos études, vous allez certainement vouloir emporter votre ordinateur avec vous partout. Nous vous présentons donc des ordinateurs portables de moins de 2kg, plus adaptés à cet usage.


#### Configurations de base

Evitez autant que possible de descendre en dessous de celles-ci. Dites-vous bien que ces machines sont estampillées "bureautique", et sont trop juste pour analyser des gros jeux de données, mais elles peuvent convenir parfaitement dans le cadre du cours de science des données biologiques. Si vous possédez déjà un PC, faites un bilan avec [Novabench](https://novabench.com/download#personal) et décidez par vous-même si vous pouvez ou non l'utiliser de manière confortable, éventuellement en installant la SciViews Box 2018 et en testant ainsi directement. Les options existent aussi pour "booster" un ordinateur un peu juste : ajout de mémoire vive et/ou remplacement du disque dur par un disque SSD rapide.

| Modèle                      | Processeur [c/t] (nova/cpu) | Mémoire | Disque     | Graphique    | Ecran            | Poids  | Prix |
|-----------------------------|--------------------------|---------|------------|--------------|------------------|--------|------|
| [Lenovo IdeaPad 320S-14IKB](https://www.lesnumeriques.com/ordinateur-portable/lenovo-ideapad-320s-14ikbr-p44207/test.html)   | Core i3-7100U [2/4] (406/3798) | 8Go     | SSD 128Go  | Intel HD620  | 14'' (1920x1080) | 1.7kg  | 500€ |
| [Acer Swift 3](https://www.lesnumeriques.com/ordinateur-portable/acer-swift-3-sf314-51-357v-p37401/test.html)  | Core i3-8130U [2/4] (579/5061) | 4Go     | SSD 256Go  | Intel HD620  | 14'' (1920x1080) | 1.45kg | 600€ |
| [MacBook Air](https://www.lesnumeriques.com/ordinateur-portable/apple-macbook-air-13-3-2016-p40639/test.html)  | Core i5-5350U [2/4] (363/3358) | 8Go     | SSD 128Go  | Intel HD6000  | 13.3'' (1440x900) | 1.35kg | 1000€ |

Avec un budget de 500€-600€, des concessions sont nécessaires. A titre d'exemple, nous reprenons deux configurations sous Windows ici. Le Lenovo choisi a 8Go de mémoire vive, mais un disque SDD de faible capacité (128Go) et un processeur un peu moins puissant. L'Acer a un plus gros disque et un meilleur processeur (toujours i3, cependant), mais n'a que 4Go de mémoire vive. Toutefois, un seul disque dur de seulement 128Go, c'est quand même fort juste sous Windows 10 qui est déjà très gourmand en espace disque à la base. Donc votre préférence ira si possible plutôt vers une configuration du type Acer Swift 3 ci-dessus^[Ce ne sont que des exemples. Recherchez des configurations équivalentes chez d'autres constructeurs aussi !]. Des versions avec processeur Core i5 et 8Go de mémoire existent. Elles sont parfaites, ... mais le prix les alignent presque avec nos configurations de référence ci-dessous. Vous verrez aussi dans les tests que ces machines ne sont pas irréprochables, mais il faut mettre les "défauts" relevés en regard du prix très contenu, et relativiser. Pour la science des données, nous privilégierons des ordinateurs plus rapides, quitte a être un peu moins bien cotés dans les tests sur la qualité de l'écran (comme l'Acer, par exemple).

Du côté Mac portables, nous avons le MacBook 12'' et le MacBook Air, présenté ici. Ils sont beaucoup plus chers, mais ce sont des ordinateurs durables et bien finis qui se revendent très bien. Dans les deux cas, le processeur (même si Core i5, ou i7) est fort juste et est plus à l'aise en bureautique. Pour analyser des petits jeux de données, ça fonctionne quand même bien. Ici aussi, des concessions sont nécessaires sur la capacité du disque dur pour tirer le prix à ... 1000€ tout de même ! Mais comme le MacBook Air existe depuis 2015 quasiment inchangé, vous pouvez trouver en occasion des modèles à prix équivalent aux deux autres machines, **mais faites attention à éviter les modèles anciens à processeurs lents qui se vendent encore, et qui ne sont pas assez puissants !** Un modèle avec un disque de 256Go existe aussi. Attention aussi : même si ce modèle vieilli bien, il est quand même en fin de vie. Ca a un impact sur la revente.


#### Configurations de référence

Avec un budget un peu plus élevé, vous êtes nettement plus confortable : processeur assez rapide **et** 8Go de mémoire vive **et** disque SSD de 256Go. Ces laptops sont parfaits pour le cours de science des données biologiques et pour bien d'autres tâches dans le cadre de vos études.

| Modèle                      | Processeur [c/t] (nova/cpu)   | Mémoire | Disque              | Graphique      | Ecran              | Poids  | Prix  |
|-----------------------------|----------------------------|---------|---------------------|----------------|--------------------|--------|-------|
| [HP Pavilion X360](https://www.lesnumeriques.com/ordinateur-portable/hp-pavilion-x360-2017-p38655/test.html)                | Core i5-8250U [2/4] (801/7667)   | 8Go     | SSD 256Go | GeForce MX130  | 14'' (1920x1080) | 1.6kg    | 900€  |
| [Acer Swift 5](https://www.lesnumeriques.com/ordinateur-portable/acer-swift-5-p40705/test.html)   | Core i5-8250U [2/4] (801/7667) | 8Go    | SSD 256Go   | Intel HD620  | 14'' (1920x1080) | 0.97kg  | 900€  |
| [MacBook Pro 13''](https://www.lesnumeriques.com/ordinateur-portable/apple-macbook-pro-13-pouces-2017-avec-touch-bar-p44179/test.html)            | Core i5-8259U [2/4] (???/10938)  | 8Go     | SSD 256Go           | Intel Iris+640 | 13'' (2560x1600)   | 1.4kg  | 1600€ |

Le HP Pavilion est un portable à écran tactile représentatif de ce créneau (pour les modèles les plus puissants de la gamme en tous cas). Vous combinez un bon processeur, 8Go RAM, un disque dur rapide de 256Go, une carte graphique accélérée et un écran correct pour l'usage prévu pour un poids raisonnable. L'Acer Swift 5 est repris ici pour son poids plume et ses résultats excellents aux tests, mais sa carte graphique est en retrait par rapport au HP (élément secondaire). Un autre très bon exemple de machine portable qui convient parfaitement pour la science des données. Vivement conseillé, donc.

Nous avons aussi inclu le premier MacBook Pro en version disque de 256Go à titre de comparaison (testé en version 2017) : il est plus cher mais à ce prix, vous avez tout de même un écran incomparablement meilleur, un processeur très rapide et une valeur à la revente bien plus haute. Chez Apple, restez dans la gamme MacBook Pro en laptops. Les processeurs des autres modèles les font tous entrer dans la catégorie de base. Attention aussi au prix des adaptateurs supplémentaires souvent indispensables pour les produits Apple ! **N'oubliez pas de demander votre remise "éducation", sur présentation de votre carte d'étudiant** (le tarif indiqué tient compte de cette remise).


#### Configurations performantes

Un budget plus large permet d'acquérir un laptop de course qui sera utile pendant des années, et même pour un travail lourd plus tard... Dans ces configurations, pas de concessions. On veut un processeur i7 à 4 ou 6 coeurs ou équivalent, 16Go de RAM, un disque SSD d'au moins 512Go, ou mieux deux disques, une carte graphique rapide (sauf sur les ultra-portables) et un excellent écran.

| Modèle                      | Processeur [c/t] (nova/cpu)   | Mémoire | Disque              | Graphique         | Ecran              | Poids  | Prix  |
|-----------------------------|----------------------------|---------|---------------------|-------------------|--------------------|--------|-------|
| [MSI GF63](https://www.lesnumeriques.com/ordinateur-portable/msi-gf63-p44711/test.html)          | Core i7-8750H [6/12] (1400/12548) | 16Go    | SSD 256Go + HDD 1To | GeForce GTX1050Ti | 15.6'' (1920x1080) | 1.86kg | 1300€ |
| [Dell XPS 13 9370](https://www.lesnumeriques.com/ordinateur-portable/xps-13-2018-p42431/test.html)            | Core i7-8550U [4/8] (837/8327) | 16Go    | SSD 512Go           | Intel HD620   | 13.3'' (1920x1080) | 1.1kg | 1400€ |
| [Asus ZenBook Flip](https://www.lesnumeriques.com/ordinateur-portable/asus-zenbook-flip-ux561u-p43837/test.html)            | Core i7-8550U [4/8] (837/8327) | 16Go    | SSD 512Go           | Intel HD400   | 13.3'' (1920x1080) | 1.1kg | 1600€ |
| [MacBook Pro 15''](https://www.lesnumeriques.com/ordinateur-portable/macbook-pro-15-2017-p39735/test.html)            | Core i7-8750H [6/12] (1400/12548) | 16Go    | SSD 512Go           | Radeon Pro 555X   | 15.4'' (2880x1800) | 1.83kg | 2700€ |

Le MSI est un PC dit "gamer". Tous les laptops dans cette catégorie sont très rapides... et conviennent parfaitement bien pour la science des données, **y compris pour les calculs GPU**. Chez MSI, un modèle comme le GS65 Stealth obtient le label de meilleur "gamer laptop 2018" (chez [techradar](https://www.techradar.com/news/mobile-computing/laptops/best-laptops-1304361)) et des modèles similaires sont très bien placés ailleurs. Mais nous préférons le GF63 moins cher car équipé d'une carte graphique un cran en dessous, et du coup, mieux positionné en rapport qualité/prix pour les sciences des données. Il est aussi nettement moins lourd. Chez Asus (ROG) et Lenovo entre autres, des machines quasi-équivalentes existent aussi. Attention : d'autres configurations de "laptops gamers" sont lourdes et elles chauffent beaucoup.

Dans la catégorie **ultraportable**, on trouve aussi diverses machines plus puissantes. Le **Dell XPS 13** de 13'' est l'un des mieux classés systématiquement dans les tests un peu partout et représentatif de ce type d'ordinateurs ultra-compacts, légers, mais très performants. Poids plume oblige, on a un processeur moins puissant que sur un PC gamer (vérifiez qu'il soit suffisamment performant sur le modèle choisi, en effet, il existe plusieurs processeurs i5 et même i7 trop lents) et une carte graphique plus basique (pas grave). Choisissez un modèle avec 16Go de RAM et au moins 256Go de disque dur. Le nouveau **[Huawei Matebook X Pro](https://consumer.huawei.com/en/laptops/matebook-x-pro/)** est une splendide machine ultraportable avec un magnifique écran de 3000x2000 pixels (excusez du peu !), mais il n'est pas repris ici, car [pas commercialisé en Belgique](http://geeko.lesoir.be/2017/12/29/huawei-ne-commercialisera-pas-ses-ordinateurs-en-belgique/). Il est toutefois [commercialisé en France](https://www.lesnumeriques.com/ordinateur-portable/huawei-matebook-x-pro-p43303/l-ultraportable-matebook-x-pro-huawei-arrive-en-france-n78557.htmlhuawei matebook x pro )... si vous acceptez d'utiliser un clavier français légèrement différent du clavier belge. Un [test complet](https://www.lesnumeriques.com/ordinateur-portable/huawei-matebook-x-pro-p43303/test.html) est aussi disponible. Ici, vous choisirez la version i5 avec processeur Core i5-8550U, 8Go de RAM et un disque SSD de 256Go pour une configuration de référence à 1500€, mais pourrez opter pour le i7 avec un Core i7-8250U, 16Go de RAM et un disque SDD de 512Go pour une configuration optimale pour environ 2000€. **C'est l'un des meilleurs ordinateurs du moment !**

Toujours dans les ultraportables, vous trouverez aussi les **convertibles**. Ceux équipés d'un écran tactile et qui peuvent se "retourner" pour s'utiliser comme une tablette haut de gamme. Les ordinateurs de type **Microsoft Surface** en sont les représentants emblématiques, mais les tests nous conduisent aussi vers l'**Asus Zenbook Flip** comme l'un des meilleurs (et assurément, un excellent rapport qualité/prix). Ici, on trouve des versions en 13'' et en 15'' mais toujours très portables et puissantes. De très bonnes machines pour analyser ses données !

A titre de comparaison, l'équivalent chez Apple est également présenté (le MacBook Pro 15'', avec option disque de 512Go et remise "éducation"). Ce dernier est à nouveau beaucoup plus cher. Mais son écran est incomparable, sa finition est impeccable, et il tourne sous MacOS naturellement pour les afficionados ! Le modèle 2018 à 6 coeurs n'a pas encore été testé chez "les numériques", mais [voici le test du modèle 2017](https://www.lesnumeriques.com/ordinateur-portable/macbook-pro-15-2017-p39735/test.html). **C'est une excellente machine. Malheureusement, la tendance est au minimalisme pour la connectique : du USB-C et c'est tout. Cela oblige à acheter et à transporter des connecteurs supplémentaires.** Les anciennes générations de MacBook Pro, "pré touch bar" se trouvent encore dans le marché de l'occasion à des prix proches de PC équivalents sous Windows. Ils sont un peu moins performants que les nouveaux, mais restent excellents, ... et possèdent beaucoup plus de connecteurs intégrés (de bonnes affaires, donc).

**Voilà ! En espérant que ceci pourra vous aider au mieux dans le choix de votre outil informatique.**


## Installation {#install}

<div class="note">
<p>Vous allez devoir d’abord installer <strong><a href="http://www.virtualbox.org">VirtualBox</a></strong>, un logiciel gratuit et libre qui se chargera de gérer votre machine virtuelle. Ensuite, vous installerez la <strong>SciViews Box</strong> en elle-même. Pour finir, vous aurez aussi besoin de <strong><a href="https://desktop.github.com">Github Desktop</a></strong>.</p>
</div>


<img src="images/annexe1/virtualbox.png" width="128px" style="display: block; margin: auto 0 auto auto;" />

### VirtualBox

Récupérez l'installateur correspondant à votre système [ici](https://www.virtualbox.org/wiki/Downloads). L'installation avec tous les paramètres par défaut convient. Il se peut que vous voyiez un message vous indiquant que VirtualBox doit réinitialiser le réseau ou une autre ressource. Vérifiez que tous les documents en cours éventuels sont sauvegardés, et ensuite, vous pourrez continuer l'installation sans risques.

<center>

![](images/annexe1/virtualbox_install_warning.png)

</center>

<br/>

\BeginKnitrBlock{win}<div class="win">De même, sous Windows, l'installateur de VirtualBox vous préviendra peut-être qu'il doit installer l'un ou l'autre périphérique. Vous pouvez également continuer sans craintes (précaution prise par Microsoft, mais ces périphériques fonctionnent bien).

![](images/annexe1/virtualbox_install_device.png)
</div>\EndKnitrBlock{win}

### SciViews Box

![](images/annexe1/svbox_screenshot.png)

La procédure d'installation de la SciViews Box diffère selon le système d'exploitation. Reportez-vous à la sous-section correspondante pour **Windows**, **MacOS** ou **Linux**.


<img src="images/block-win.png" width="128px" style="display: block; margin: auto 0 auto auto;" />

#### Installation sous Windows

Chargez l'installateur [ici](http://go.sciviews.org/svbox2018a-win) ou, pour les étudiants de l'UMONS, récupérez-le depuis le disque `StudentTemp` de la salle informatique (sous-répertoire ` SDD\Software\SciViews Box 2018`). Pensez aussi à placer le fichier `svbox2018a.vdi.xz` dans le même répertoire que l'installateur `svbox2018a_win_setup.exe`. Sinon vous devrez le télécharger lors de l'installation (il pèse tout de même 2,9Gb)! Lancez l'installation. Vous verrez l'écran suivant (probablement en version française sur votre ordinateur). Vous pouvez cliquer 'Yes'/'Oui'. Il s'agit seulement d'une précaution de Microsoft lorsqu'il ne connait pas l'éditeur du programme à installer, comme c'est le cas ici.

<center>

![](images/annexe1/svbox_install_warning.png)

</center>

Si le fichier `svbox2018a.vdi.xz` n'est pas présent dans le même répertoire que le programme d'installation, il est à présent téléchargé (cliquez sur "Details" pour suivre l'opération):

<center>

![](images/annexe1/svbox_install_download.png)

</center>

Une fois le téléchargement terminé, l'installation se poursuit. Vous verrez ensuite qu'il y a encore une opération obligatoire à lancer: la décompression du disque virtuel de la SciViews Box (`svbox2018a.vdi`) via '7z'.

<center>

![](images/annexe1/svbox_install_done.png)

</center>

En cliquant 'Finish', cette décompression démarre toute seule.

<center>

![](images/annexe1/svbox_install_uncompress.png)

</center>

<br/>

<div class="warning">
<p>N’interrompez surtout pas la décompression du disque virtuel! Sinon, votre SciViews Box ne pourra pas démarrer et vous devrez tout recommencer à zéro en désinstallant et réinstallant complètement l’application.</p>
</div>

Losque tout est installé, vous avez une nouvelle icône sur votre bureau. Poursuivez à la section suivante pour démarrer et paramétrer votre SciViews Box.

<center>

![](images/annexe1/svbox_install_desktop_icon.png)

</center>

En option, vous pouvez épingler le nouveau programme dans la barre des tâches. Il sera plus facilement accessible (voir ci-dessous).

<center>

![](images/annexe1/pin-in-taskbar.gif)

</center>


<img src="images/block-mac.png" width="128px" style="display: block; margin: auto 0 auto auto;" />


#### Installation sous MacOS

Chargez l'installateur [ici](http://go.sciviews.org/svbox2018a-mac) ou, pour les étudiants de l'UMONS, récupérez-le depuis le disque `StudentTemp` de la salle informatique (sous-répertoire ` SDD/Software/SciViews Box 2018`). Si vous le pouvez, placez le fichier `svbox2018a.vdi.xz` dans le dossier de téléchargements (`Téléchargements` ou `Downloads` selon la version de votre MacOS), sinon, ce fichier sera téléchargé au même emplacement (il pèse 2,9Gb)! Double-cliquez sur `svbox2018a_macos_setup.dmg`. Suivez simplement les instructions. 

<center>

![](images/annexe1/svbox_mac-install.gif)

</center>

- Déplacez à la souris 'SciViews Box 2018a' vers le dossier 'Applications' dans la fenêtre de l'installeur (cette partie de l'installation est très rapide, donc, vous n'aurez peut-être pas l'impression que quelque chose se passe),
- Ensuite, toujours dans cette fenêtre, double-cliquez sur le dossier 'Applications' et recherchez l'entrée 'SciViews Box 2018a'. Double-cliquez dessus,
- Si vous avez chargé l'installateur depuis Internet, il se peut que votre Mac indique un message et vous empêche de l'ouvrir. Dans ce cas, il faut cliquer avec le bouton droit de la souris et selectionner "Ouvrir" dans le menu contextuel **tout en maintenant la touche `ALT` enfoncée**, et ensuite cliquer "Ouvrir" dans la boite qui s'affiche.

Laissez l'installation se terminer. Cela peut prendre plusieurs minutes. En option, vous pouvez aussi accrocher le programme de manière permanente dans le "Dock" pour le lancer facilement depuis cet endroit. Cliquez bouton droit et dans le menu "Options", sélectionnez l'entrée "Garder dans le Dock".

<center>

![](images/annexe1/svbox_mac-keep-in-dock.gif)

</center>


<img src="images/block-linux.png" width="128px" style="display: block; margin: auto 0 auto auto;" />


#### Installation sous Linux

Il est parfaitement possible d'installer la SciViews Box sous Linux. Cependant, un programme d'installation simplifié n'a pas encore été développé pour ce système. _Voyez au cas par cas avec vos enseignants pour qu'ils vous expliquent comment installer la SciViews Box manuellement sous Linux._


#### Migration et désinstallation

Le disque dur virtuel de la SciViews Box est un fichier volumineux de plus de 10Go. L'installeur fait en sorte qu'il soit partagé entre plusieurs utilisateurs de l'ordinateur, et qu'il reste inchangé au cours de son utilisation. Ainsi, VirtualBox enregistrera dans vos dossiers personnels un fichier qui stocke les différences par rapport à l'état de départ de la Box. Il est donc possible de **désinstaller partiellement** la SciViews Box 2018 sans rien perdre. Pour cela, il suffit de désinstaller l'application (sous Windows, allez dans le panneau de configuration -> Applications -> SciViews Box 2018 -> Désinstaller ; sous MacOS déplacez simplement l'application `SciViews box 2018a` depuis le dossier `Applications` vers la corbeille). Vous récupèrerez immédiatement près de 11Go d'espace disque. VirtualBox ne pourra plus démarrer la Box, naturellement, mais _conservera vos données_. Si besoin, vous pourrez réinstaller simplement l'application `SciViews Box 2018a` pour retrouver votre Box en l'état.

Une désinstallation complète nécessite d'aller **d'abord** supprimer la machine virtuelle dans VirtualBox (clic bouton droit et sélection de `Supprimer...`) pour _tous_ les utilisateurs qui ont créé une Box _avant_ de désinstaller l'application principale comme ci-dessus.

Si vous avez des projets créés avec des SciViews Box antérieures, deux solutions existent :

1. Gardez-les tel quels. Faites éventuellement une désinstallation partielle de la Box. Vous pourrez toujours revenir plus tard sur ces projets après réinstallation.

2. Migrez-les vers la nouvelle SciViews Box. Copiez vos projets depuis le répertoire `shared` de l'ancienne Box vers celui de la nouvelle. Dans ce cas, vous devrez **vérifier** que votre code fonctionne toujours sous la nouvelle Box, et l'adapter éventuellement.


### Github Desktop

<center>

![](images/annexe1/github-desktop-website.png)

</center>

Dans ce cours, nous utilisons **Git** et **Github** pour gérer les différentes versions de vos projets et les partager avec vos binômes et vos enseignants. [Github Desktop](https://desktop.github.com) facilite grandement la gestion de vos projets sous Git. Ce programme gratuit est très facile à installer : son téléchargement et le lancement de son installeur ne pose pas de problèmes particuliers. _Notez toutefois que ce programme n'est pas encore disponible pour Linux._

**A présent, tous les ligiciels requis sont installés... Il ne reste plus que quelques petites opérations de configuration à réaliser. Voyez ceci à la section suivante.**


## Configuration

Même si la SciViews Box est pré-configurée, vous allez avoir quelques manipulations simples à réaliser pour être complètement opérationnel. Ces étapes sont détaillées ci-dessous. Nous en profiterons par la même occasion par nous familiariser avec quelques uns des outils logiciels que vous utiliserez plus tard, à commencer par le lanceur rapide SciViews Box.


### Lanceur SciViews Box

L'application que vous venez d'installer est un **lanceur rapide** qui facilite le démarrage, la fermeture et la gestion de votre machine virtuelle SciViews Box 2018a. Démarrez-là et vous verrez la fenêtre suivante:

![](images/annexe1/svbox-launcher-comment.png)

Le message en rouge n'apparait pas systématiquement. Il signale des éléments importants. Ici, il indique que la configuration de la SciViews Box doit encore être faite, et pour cela, vous devez (1) **la démarrer** à l'aide du gros bouton en haut à gauche, (2) **vous logger** (mot de passe = **sv**), et (3) **répondre `Yes`** lorsqu'une boite de dialogue vous propose d'installer 'svbox2018a v1.0.0'.

<center>

![](images/annexe1/autoinstall-question.png)

</center>

<br/>

<div class="warning">
<p>Cette dernière étape est importante! Ne cliquez pas <code>No</code> ici, sous peine de ne pas avoir une machine virtuelle configurée comme celle de vos collègues!</p>
</div>

Le mot de passe vous sera redemandé, et ensuite, l'installation se poursuivra. Elle pourra prendre plusieurs minutes. Soyez patient. Vous pourrez ouvrir la fenêtre du terminal où s'opère le travail pour en suivre la progression, si vous le souhaitez.

<center>

![](images/annexe1/svbox-install_terminal.png)

</center>

A la fin vous verrez la fenêtre du configurateur de la SciViews Box apparaître.


### Configurateur de la Box

<center>

![](images/annexe1/svbox-config1.png)

</center>

Prenez le temps de parcourir les différents éléments dans cette fenêtre^[Si jamais vous voulez retourner plus tard au configurateur de la SciViews Box, vous n'aurez qu'à cliquer sur son icône tout en haut à droite dans la barre supérieure.].

La partie à gauche en haut concerne la **configuration du clavier**. En effet, la machine virtuelle utilisera votre clavier physique, mais elle n'a aucun moyen de déterminer de quel modèle il est. Vous allez donc l'indiquer maintenant. Utilisez la zone de texte intitulée `Test area (type here)`  pour vérifier que la machine virtuelle interprète correctement les touches de votre clavier. Pour le changer, cliquez sur le bouton `Change keyboard layout`. 

<center>

![](images/annexe1/config-keyboard.png)

</center>

La boite de dialogue de sélection du clavier apparait. Elle propose des configurations différentes sous forme de représentations graphiques, avec les touches caractéristiques surlignées en jaune. Vous pouvez entrer les premières lettres du type de clavier pour aller directement à la configuration correspondante dans la liste (ex.: entrez `be` pour un clavier belge). Si votre clavier ne se trouve pas dans les templates les plus courants, configurez-le à l'aide du bouton `Other keyboard...`. Fermez cette fenêtre pour retourner au configurateur lorsque vous aurez fini.

Enfin, toujours concernant le clavier, la case à cocher `Exchange left CTRL / CMD (Mac shortcuts)` permet d'utiliser les raccourcis Mac (comme `Cmd-c` pour copier et `Cmd-v` pour coller à la place de `Ctrl-c` ou `Ctrl-v` sur un PC.

![](images/annexe1/svbox-config2.png)

Cette option n'est utile qu'aux possesseurs d'un Mac qui veulent avoir des raccourcis plus homogènes entre leur système MacOS hôte et la machine virtuelle^[Le Mac définit ses raccourcis claviers différemment du PC. Outre l'inversion de l'utilisation des touches `Ctrl` et `Cmd`, le Mac possède deux touches `Alt`, une à gauche et une à droite. Le PC a, par contre, deux touches correspondantes, mais celle de droite est nommée `Alt Gr`. Ces touches jouent des rôles différents: raccourcis claviers pour `Alt` et accès aux touches de niveau 3 et 4 pour `Alt Gr`. **Pour les utilisateurs Mac, notez que vos deux touches `Alt` ont des rôles différents dans la SciViews Box comme pour un clavier PC.** Enfin, VirtualBox réserve une touche clavier à son propre usage. Par défaut, c'est la touche `Cmd` ou `Win` de droite. **Il est déconseillé de modifier ce choix car toutes les autres touches sont indispensables dans la SciViews box!**].

Juste en dessous, vous voyez la configuration du fuseau horaire.

![](images/annexe1/svbox-config3.png)

Ici aussi, votre machine virtuelle n'a pas l'information de votre système hôte, et peut donc ne pas afficher l'heure correctement. Vous avez la possibilité de corriger cela en cliquant sur le bouton `Change time zone`. Vous devez débloquer la boite de dialogue (bouton `Unlock` en bas, puis entrer le mot de passe pour pouvoir effectuer des changements).

Les trois boutons à gauche en bas servent à choisir le stylage des fenêtres, le set d'icônes et l'image d'arrière plan de votre SciViews Box.

![](images/annexe1/svbox-config4.png)

C'est ici que vous pourrez la paramétrer au mieux pour qu'elle vous plaise visuellement. A noter que, si vous double-cliquez sur les entrées dans les boites de dialogue de configuration, vous allez pouvoir **prévisualiser** l'effet en live. Utile pour apprécier le rendu avant de faire son choix!

La zone en bas à droite permet de modifier le mot de passe.

![](images/annexe1/svbox-config5.png)

Pour rappel, il s'agit d'un mot de passe simple et peu sécure par défaut: `sv`. En fait, vous n'avez pas réellement besoin d'un mot de passe à l'intérieur de votre SciViews Box telle qu'elle est configurée car vous ne pouvez y accéder qu'en local à partir de l'ordinateur hôte. Par contre, il est possible d'ouvrir l'accès. A ce moment-là, il serait utile, *et même indispensable*, de modifier le mot de passe.

<div class="error">
<p>Dans le cadre de votre utilisation de la SciViews Box pour ce cours, que ce soit sur les machines de la salle de T.P., ou sur votre ordinateur personnel, ne <strong>changez pas</strong> le mot de passe! Votre machine virtuelle est <em>déjà</em> protégée par votre système hôte puisque seul un accès local est autorisé.</p>
</div>

La zone en haut à droite permet de configurer votre compte Git.

![](images/annexe1/svbox-config6.png)

Comme vous allez utiliser Git et Github de manière intensive tout au long de ce cours, **veuillez configurer cette partie du système correctement d'amblée!** Les trois boutons du bas proposent de s'enregistrer sur trois systèmes distants d'hébergement de dépôts Git (si vous ne savez pas ce que c'est, imaginez juste que c'est là que vous allez pouvoir entreposer de manière sûre tous vos projets!): **Github**, **Gitlab** ou **Bitbucket**. Tous trois ont des avantages et des inconvénients, et ils proposent tous des utilisations gratuites dans certains cas.

<div class="note">
<p>Durant nos cours de Science des Données à l’UMONS, nous utiliserons <strong>Github</strong>. Cette utilisation sera gratuite pour vous, et vous allez pouvoir déjà commencer à construire <strong>votre identité professionnelle sur le Net</strong> par son intermédiaire. Donc, enregistrez-vous de manière sérieuse. Choisissez un login représentatif de vos nom et prénom, pas un truc louffoque ou rigolo sur le moment, mais que vous regretterez plus tard, sachant que votre login ne pourra <strong>pas</strong> être changé ensuite!</p>
</div>

Vous allez donc vous créer un compte sur Github en cliquant sur le bouton correspondant, et en indiquant un login et un mot de passe. **Nous vous demandons également d'utiliser expressément et uniquement votre adresse email UMONS ici : prénom.nom@student.umons.ac.be.** En effet, ce sera, pour nous, notre seul moyen de vous identifier sans erreur sur Github lorsque nous interviendrons pour vous conseiller et/ou pour corriger vos travaux.

<center>

![](images/annexe1/github-login.png)

</center>

Une fois enregistré sur le site de Github, reportez votre login et votre adresse email dans le configurateur de la SciViews Box, pour que Git puisse vous identifier correctement en local^[A la première utilisation de Git à l'intérieur du logiciel **RStudio**, votre login et votre mot de passe vous seront également redemandés. De même, vous devrez également fournir ces informations dans **Github Desktop** et la première fois que vous naviguerez vers https://github.com depuis le navigateur Web de votre PC hôte. Mais ensuite, vous accèderez immédiatement au service.].

![](images/annexe1/svbox-config7.png)

Une fois tout ceci effectué vous pourrez cliquer sur le bouton `OK` de la fenêtre du configurateur SciViews Box. La machine virtuelle devra redémarrer pour appliquer toutes les modifications de manière durable. Cliquez également `OK` donc dans la boite de dialogue qui apparait ensuite (sinon, elle redémarrera toute seule après 30 sec) :

<center>

![](images/annexe1/svbox-config-reboot.png)

</center>


### Installation des tutoriels {#install-tuto}

Nous allons maintenant installer les tutoriels liés à ces cours de science des données biologiques. Vous allez apprendre par la même occasion comment ajouter des applications dans votre SciViews Box. Cela se fait en trois étapes:

1) Télécharger l'installeur de l'application. Vous le trouverez à l'adresse http://go.sciviews.org/BioDataScience1. Assurez-vous de bien le charger dans le répertoire **Downloads** ou **Téléchargements** par défaut sur votre ordinateur^[Il pourra ainsi être replacé au bon endroit et exécuté dans la Box]. Téléchargez, de même, la mise-à-jour vers la version 2.0 de la SciViews Box à l'adresse http://go.sciviews.org/svbox2018a2.

2) Rentrez dans le lanceur rapide de la SciViews Box. Il repère les autoinstalleurs et les déplace dans le dossier partagé pour les rendre utilisables par la SciViews Box. Vous devez voir un message indiquant la disponibilité d'autoinstalleur(s). Vos fichiers téléchargés ont également disparus du répertoire de téléchargement à ce stade,

   ![](images/annexe1/autoinstall-message.png)

3) Rentrez dans la SciViews Box depuis le lanceur. Si la Box était déjà active ou si elle est réveillée du mode veille, vous allez devoir vous délogger et relogger pour que l'installation démarre, ... sinon, vous allez voir directement le message suivant qui propose d'installer ces apps (cliquez sur `Yes`, bien sûr, pour l'installer).

![](images/annexe1/autoinstall-bdd-message.png)

Si le message n'apparait pas, voici comment se délogger (**log out**).

<center>

![](images/annexe1/svbox-exit.gif)

</center>

Ensuite, entrez votre mot de passe comme d'habitude pour vous relogger... A ce moment, le message doit apparaitre, et l'installation doit se faire après avoir cliqué le bouton `Yes`.

**Bravo! Vous avez terminé l'installation et la configuration de votre SciViews Box. Cependant, nous allons encore effectuer une petite opération qui vous facilitera la vie, et nous vous expliquerons par la même occasion comment accéder aux fichiers respectifs de la machine virtuelle et du système hôte dans la section suivante.**


### Accès aux fichiers

Le disque physique de votre ordinateur hôte, et le disque virtuel de la SciViews Box sont deux choses différentes. Cela signifie que vous avez, en réalité deux ordinateurs et deux disques indépendants. Donc, vous n'accédez **pas** aux fichiers d'une machine à partir de l'autre^[Le presse-papier est synchronisé entre les deux machines pour le texte qui y est copié.]. Ce n'est pas pratique, et ce n'est pas vrai pour un dossier particuler nommé **shared**.

<center>

![](images/annexe1/svbox-diagram.svg)

</center>

Ce dossier **shared** est synchronisé en temps réel entre les deux systèmes. C'est donc l'endroit idéal pour échanger des données et pour faire collaborer vos deux machines. Inutile de préciser, donc, que nous travaillerons essentiellement à l'intérieur de ce dossier. Un sous-dossier, nommé **projects** sera utilisé pour héberger toutes nos analyses. Il est donc primordial d'y accéder facilement à la fois depuis l'ordinateur hôte et depuis la SciViews Box. Vous allez donc apprendre à retrouver ce dossier **projects** facilement.

Sur votre **ordinateur hôte**, ce dossier est un peu difficile à trouver en naviguant dans l'explorateur de fichiers (ou le Finder sur le Mac). Pour cette raison, le lanceur rapide propose un bouton pour y accéder plus facilement.


Une fois dans le dossier **shared**, nous vous conseillons d'épingler le sous-dossier **projects** dans les raccourcis rapides de votre explorateur de fichiers. Voici comment faire sous Windows et sous MacOS. 

\BeginKnitrBlock{win}<div class="win">Sous Windows, cliquez bouton droit sur **projects**, et sélectionnez "épingler dans Accès rapide".

![](images/annexe1/pin-projects-win.gif)
</div>\EndKnitrBlock{win}

\BeginKnitrBlock{mac}<div class="mac">Sous MacOS, vous glissez-déposez **projects** dans la barre latérale du Finder.

![](images/annexe1/svbox_mac-pin-projects.gif)
</div>\EndKnitrBlock{mac}

Dans la **SciViews Box**, ce dossier est accessible depuis deux endroits: `/media/sf_shared` et `~/shared` (`~` représente le répertoire de l'utilisateur, c'est-à-dire `/home/sv`). Ici aussi vous pouvez épingler votre dossier **projects** pour en facilter l'accès:

\BeginKnitrBlock{svbox}<div class="svbox">Les deux moyens d'accéder au dossier **projects** dans la SciViews Box et comment l'épingler sur le côté.

![](images/annexe1/pin-projects-svbox.gif)
</div>\EndKnitrBlock{svbox}

**A retenir:** le dossier **shared** et ses sous-dossiers comme **projects** sont considérés un peu comme des dossiers réseau par la SciViews Box. Cela implique que certaines fonctions du système de fichiers n'y sont pas accessibles. Parmi celles-ci, la **poubelle**. Donc, vous ne pourrez qu'effacer complètement des items en cliquant bouton droit et sélectionnant 'Delete' dans le menu contextuel dans le gestionnaire de fichiers. Si vous essayer de placer des fichiers ou dossiers depuis **shared** dans la poubelle de la SciViews Box, cela vous sera refusé (voir copie d'écran ci-dessous). _Par contre, cela fonctionne très bien depuis l'ordinateur hôte._

<center>

![](images/annexe1/shared_no-trash.png)

</center>

Un tout dernier point concernant les ordinateurs de la salle de T.P. de l'UMONS. Pour des questions de performance, la machine virtuelle SciViews Box, et le dossier **shared** ne sont **pas** sur votre compte, mais directement sur le disque de l'ordinateur. Cela signifie qu'ils ne sont pas transportables vers un autre ordinateur. Vous pouvez créer une copie de **shared** dans **mes documents** ou sur une clé USB pour les transporter vers un autre ordinateur... mais nous verrons que cela n'est pas nécessaire pour tout ce que vous stockerez sur Github. En effet, vous avez accès à ces contenus depuis n'importe où via n'importe quelle connexion internet.

## Utilisation {#svbox_use}

Une fois votre machine virtuelle configurée, vous vous trouvez confronté à cet écran qui montre le fond d'écran et un ensemble d'items par dessus. Nous l'appellerons le bureau de la SciViews Box. 

![](images/annexe_a1/desktop.png)

Cette machine virtuelle utilise le système d'exploitation Linux. Vous pouvez accèder au application présentes sur cette machine à partir du menu `Applications` en haut à gauche du bureau. Ce dernier offre un menu déroulant avec l'ensemble des applications disponibles. Ces applications sont rangé en dossier  tel que `Favorites`, `Recently Used` , `All`, ...

![](images/annexe_a1/sv_app.gif)

Le "dock" en bas du bureau permet de lancer des applications rapidement et d'accéder aux fenêtres des applications en cours d'exécution tel que RStudio, Jupyter, Spyder,...

![](images/annexe_a1/sv_bar.png)

Pour accèder à vos dossiers et fichiers, il suffit de cliquer sur l'icône en forme de dossier avec une image de petite maison que l'on retrouve également dans le dock.

![](images/annexe_a1/sv_home.gif)



