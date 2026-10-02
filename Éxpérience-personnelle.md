# Diagnostique et guide de montage d'un ordinateur à distance

## Contexte

Une connaissance m'exprime que les performances du processeur de son ordinateur n'ont jamais correspondu à celles des nombreux tests que l'on peut retrouver sur Internet et qu'il présente d'énormes ralentissements.
Mais comme il avait récemment changé de carte graphique pour passer sur un modèle bien plus récent et performant, il m'a donc demandé conseil sur les composants qu'il devrait prendre à un prix raisonnable, surtout dans notre conjoncture de marché actuelle où tous les composants explosent en prix.
Outre l'achat des composants, il n'avait touché à son ordinateur que pour changer sa carte graphique. Il a donc fallu entièrement le guider à distance, en appel, pour démonter et installer les nouveaux composants.

## Problématique

- L'ordinateur de ma connaissance montre des résultats de performance bien en dessous que ceux recensés sur l'internet.
- Il souhaite remplacé sois-même son processeur et carte-mère pour passer sur une plateforme plus moderne et fiable dans le temps, sans avoir jamais exercer ni connaitre la démarche à suivre.

## Démarche:

- Pour commencer il me fallait comprendre le pourquoi ce processeur montrait des résultats aussi en dessous des moyennes connus, pour cela, le 28/03/2026, nous avons procéder à un premier appelle afin d'effectuer des testes de stabilités et de performances.
Je lui ai premièrement demandé d'installer un logiciel de benchmark CPU du nom de CINEBENCH 2026, qui effectue un rendu d'image lourd et quantifie la performance du CPU utilisé sous forme de points.
Pour son processeur, qui est un 11900K, la moyenne en single-core se trouve autour de 95 points et de 789 en multi-core. Cependant, une fois le test fini, les résultats ont montré des résultats bien en dessous des moyennes.
En single-core, il a obtenu un résultat de 38 points et 498 en multi-core.
J'ai donc suspecté un problème de surchauffe matérielle. Pour vérifier cela, je lui ai fait installer le logiciel OCCT, qui permet d'effectuer différents stress tests sur quasiment l'intégralité des éléments d'un ordinateur, tout en ayant une interface permettant de monitorer l'ensemble des sondes, et donc, dans notre cas, un stress test CPU, pour mesurer la chauffe et la consommation de celui-ci.
Après une vingtaine de minutes de test, la chauffe était plus que correcte, mais une des informations semblait incohérente : le CPU en charge maximale ne consommait que 80 W alors qu'il est censé consommer jusqu'à 250 W, avec une tension de 10,2 V au lieu des 12 V normaux.
Je me suis donc penché sur l'alimentation que possédait ma connaissance, mais c'était une alimentation SQ POWER 12 700 W 80+ Platinum, donc bien assez puissante pour alimenter le CPU.
C'est alors que je lui ai demandé de vérifier le modèle de sa carte mère, et j'ai obtenu la réponse au problème grâce à son modèle.
Il avait une carte mère ASROCK H510M-HDV/M.2 SE, un modèle micro-ATX réservé aux CPU d'entrée de gamme à faible consommation.
En effet, il est recommandé pour un Intel Core i9-11900K une carte mère haut de gamme avec un minimum de 14 VRM pour garantir une stabilité et une charge maximale. La ASROCK H510M-HDV/M.2 SE n'en possède que 7, soit la moitié de ce qui est recommandé pour une utilisation stable.

- Mais étant donné qu'il souhaitait évoluer vers une plateforme plus moderne ce diagnostique n'a eu comme intérêt qu'un défis de recherche de problématique.
Pour déterminer les besoins de ma connaissance, je lui ai demandé quelles seraient les futures utilisations de son ordinateur afin de lui proposer une amélioration cohérente avec ses activités, mais aussi quel budget il serait prêt à investir dans cet achat.
Ses principales activités étaient le rendu 3D sur Blender, les jeux vidéo demandant des ressources CPU importantes pour la gestion de la physique et la réalité virtuelle, le tout pour un budget de 450 euros.
Je l'ai donc redirigé vers un Intel Core i5-13600KF, un processeur qui, malgré son appellation i5, délivre une puissance comparable à celle du i9 de la génération précédente. Afin qu'il n'ait pas de nouveau le problème de VRM, je lui ai conseillé une carte mère de chez MSI, une MSI B760 Gaming Plus WiFi DDR4, au format ATX, qui, en plus d'une conception solide pour son CPU, lui permet de conserver sa RAM en DDR4 afin d'éviter de dépasser le budget en prenant de la RAM en DDR5, qui est hors de prix.
Mais comme son nouveau processeur allait avoir une enveloppe thermique bien plus élevée que l'ancien, je lui ai recommandé de prendre un ventirad plus performant, comme le Thermalright Peerless Assassin 120 SE ARGB, un ventirad au rapport qualité/prix imbattable. J'aurais pu lui conseiller de prendre un watercooling AIO d'entrée de gamme, mais un AIO n'aurait pas été assez fiable dans le temps, surtout pour un modèle d'entrée de gamme.
C'est deux jours plus tard qu'il a reçu l'intégralité des composants et que je pouvais enfin le guider pour le montage.
Premièrement, je lui ai demandé d'éteindre l'alimentation de son ordinateur, de le débrancher du secteur et de rester appuyé sur le bouton d'alimentation afin de décharger les composants et de commencer en toute sécurité. Puis de démonter le ventirad, de retirer sa carte graphique, puis de dévisser la carte mère et de la remettre dans sa boîte d'origine. Et enfin de se munir des manuels des nouveaux composants afin de pouvoir suivre mes indications et relever toute confusion.
Dès ce moment, le montage s'est poursuivi lentement, étape par étape, en suivant le manuel de la carte mère et du ventirad, jusqu'à l'étape du câblage du front panel, où un problème est survenu.
Confiant, j'ai espéré qu'il n'inverserait pas les branchements du front panel et, n'étant pas sur place pour vérifier, je ne pouvais pas en être sûr.
Et c'est ainsi que, lorsqu'il était temps d'appuyer sur le bouton d'alimentation du boîtier, rien ne se passait, aucun signe de vie.
J'ai naturellement pensé à un câble mal branché, mais après une minutieuse vérification, tout était en ordre.
J'ai donc eu un doute sur la rigueur du câblage du Front Panel et je lui ai suggéré de débrancher les câbles du front panel et de faire un allumage alternatif en faisant se rencontrer les pôles positif et négatif du front panel à l'aide de la pointe de son tournevis. En faisant ainsi, l'ordinateur s'est allumé et a affiché une image.
J'en ai donc conclu qu'il les avait effectivement mal branchés.
Une fois branchés dans le bon ordre, je lui ai fait installer toutes les mises à jour nécessaires des pilotes et du BIOS (BIOS indispensable pour garantir la sécurité contre de potentiels virus et pour appliquer le correctif réglant le problème de surtension présent sur les générations 13 000 et 14 000 d'Intel), et nous avons procédé aux mêmes tests effectués sur l'ancien CPU, mais cette fois-ci, plus aucun problème.
L'ordinateur était parfaitement fluide et performant.

## Outils mobilisés:

Logiciel de communication: Discord
Logiciel: CINEBENCH R24
Logiciel: OCCT
Processeur: Intel Core I5 13600K
Carte Mère: MSI B760 GAMING Plus DDR4 WIFI
Ventirad: Thermalright Peerless Assassin 120 SE ARGB
Pâte thermique: Thermalright TF7
Tourne-vis cruciforme

## Résultat

L'ordinateur n'a plus aucune latence et exploite pleinement les performances disponibles, tout en étant futur-proof pour de longues années.

## Bilan personnel

Cette expérience a pu me permettre de mettre en avant mes qualités de support à distance et ma pédagogie face à une situation difficile présentée à un novice en informatique.
J'en ressors avec la satisfaction de pouvoir aider grâce à mes connaissances, tout en étant encore un simple passionné.
