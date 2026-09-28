# Diagnostique et guide de montage d'un ordinateur à distance

## Contexte

Une conaissance m'éxprimme que la performance du processeur de son ordinateur n'a jamais corespondu avec celles des nombreux testes que l'on peut retrouvé sur l'internet et qu'il présente d'énormes ralitessements.
Mais comme il avait récement changé de carte graphique pour passer sur un modèle bien plus récent et performant , il m'a donc demandé conseil sur les composnats qu'il devrait prendre à prix raisonable, surtout dans notre conjoncture de marché actuelle où  tous les composnats exploses en prix.
Outre l'achat des composants, il n'avait touché à son ordinateur que pour changé sa carte graphique, il a donc fallut entièrement le guidé à distance en appelle pour démonter et installer les nouveau composants.

## Problématique

- L'ordinateur de ma connaissance montre des résultats de performance bien en dessous que ceux recensés sur l'internet.
- Il souhaite remplacé sois-même son processeur et carte-mère pour passer sur une plateforme plus moderne et fiable dans le temps, sans avoir jamais exercer ni connaitre la démarche à suivre.

## Démarche:

- Pour commencer il me fallait comprendre le pourquoi ce processeur montrait des résultats aussi en dessous des moyennes connus, pour cela, le 28/03/2026, nous avons procéder à un premier appelle afin d'effectuer des testes de stabilités et de performances.
Je lui ai premièrement demandé d'installer un logiciel de BenchMark CPU du nom de CINEBENCH 2026 qui effectue un rendu d'image lourd et quantifié la performance du cpu utilisé sous forme de points.
Pour son processeur qui est un 11900K la moyenne en single-core se trouve autour des 95 points et 789 en multi-cores. Cependant une fois le test fini les résultats ont montré des résultat bien en dessous des moyennes.
En single-core il a obtenu un résultat de 38 points et 498 en multi-core.
J'en ai donc suspecté un problème de surchauffe matériel, pour vérifier cela, je lui ai fait installer le logiciel OCCT qui permet d'effectuer différent stress-test sur quasiment l'intégrité des éléments d'un ordinateur tout en ayant une interface monitoré de l'ensemble des sondes , et donc dans notre cas un stress-test-cpu, pour mesurer la chauffe et consomation de celui-ci.
Après une vingtaine de minutes de teste, la chauffe était plus que correcte, mais une des information semblait incohérente, le cpu en charge maximal ne consommé que  80 W alors qu'il est sensé consommé jusqu'à 250 W et une tension de 10.2V au lieu du 12V normal.
Je me suis donc penché sur l'alimentation que possédait ma connaissance , mais c'était une alimentation SQ POWER 12 700 W 80+ Platinium, donc bien assez de puissance pour alimenter le cpu.
C'est alors que je lui ai demandé de vérifier le modèle de sa carte mère, et j'ai obtenu la réponse au problème par son modèle.
Il avait une carte-mère ASROCK H510M-HDV/M.2 SE, un modèle micro-ATX réservé aux cpu très entré de gamme à consommation faible.
En effet il est recommandé pour un Intel Core I9 11900K une carte mère haut-de-gamme avec minimum 14 vrm pour garantir une stabilité et une charge maximal, la ASROCK H510M-HDV/M.2 SE, n'en possède que 7, soit la moitié de ce qui est recommandé pour une utilisation stable.

- Mais étant donné qu'il souhaitait évoluer vers une plateforme plus moderne ce diagnostique n'a eu comme intérêt qu'un défis de recherche de problématique.
Pour déterminer le besoin de ma conaissance je lui ai demandé quelles seront les futurs utilisation de son ordinateur pour lui proposer une amélioration cohérente à ses activités, mais aussi quel budget il serait prêt à investir dans cet achat.
Il ses principales activités étaient, du rendu 3D sur Blender, du jeux vidéo demandant des ressource cpu lourde pour la gestion des physiques et de la Réalité Virtuel, le tout pour un budget de 450 euros.
Je lui ai donc rediriger vers un Intel Core I5 13600Kf, un processeur qui malgrès son appellation I5, délivre la puissance du I9 de la génération précédente. Afin qu'il n'est pas de nouveau le problème de vrm je lui ai conseillé une carte mère de chez MSI, une MSI B760 Gaming Plus WiFi DDR4 Carte mère, ATX , qui en plus d'une conception solide pour son CPU lui permet de conserver sa ram en DDR4 afin d'éviter de dépasser le budget en prenant de la ram en DDR5 qui est hors de prix raisonnable.
Mais comme son nouveau processeur aller avoif une envellope thermique bien plus élevé que l'ancien, je lui ai recommandé de prendre un ventirad plus performant comme le Thermaright Peerless assasin 120 SE ARGB, un ventirad à prix/performance imbatable. J'aurais pu lui conseiller de prendre un water cooling en AIO entré de gamme, mais un AIO n'aurait pas était assez fiable dans le temps, surtout pour un modèle entrée-de-gamme.
C'est deux jour plus tard qu'il a reçu l'intégralité des composants et que je pouvais enfin le guider pour le montage.
Premièrement je lui ai demandé d'éteindre l'alimentation de son ordinateur, de le débrancher du secteur, et de rester appuyer sur le bouton de décharge de l'alimentation de l'alimentation, afin de commencer en toute sécurité. Puis de démonter le ventirad, retirer sa carte graphique , puis de dévisser la carte mère et la remettre dans sa boite d'origine. Et enfin ce munir des manuelles des nouveaux composants, afin de pouvoir soutenir mes propos et relever toutes confusions.
Dès ce moment le montage c'est poursuit lentement  étape par étape en suivant le manuel de la carte mère et du ventirad, jusqu'à l'étape du câblage du front panel où un problème et survenu.
Confiant j'ai espéré qu'il n'inverserait pas les branchement du front panel, et n'étant pas sur place pour vérifier, je ne pouvais en être sûr.
Et c'est ainsi que quand il était temps d'appuyer sur le bouton d'alimentation du boitier, rien se passait, aucun signe de vie.
J'ai naturellement pensé à un câble mal branché, mais après une minutieuse examinassions tout était en ordre.
J'ai donc eu le doute sur la rigueur mise pour le câblage du Front-Panel, et je lui ai suggérer de débrancher les câble du front panel et de faire un allumage alternatif et faisant rencontrer le pôle positif et négatif du front panel à l'aide de la pointe de son tourne-vis. Et en faisant ainsi l'ordinateur c'est allumé et à donné un affichage.
J'en ai donc bien conclu qu'il les avait effectivement mal branchés.
Une fois branché dans le bonne ordre je lui ai fait installé toutes les mise à jour pilotes driver et Bios ( Bios indispensable pour garantir la sécurité contre des potentiels virus et pour appliquer le correctif réglant le problème de sur-tension présent sur les générations des 13000 et 14000 de chez intel) nécessaire et nous avons procédé aux mêmes testes effectué sur l'ancien cpu, mais cette fois-ci, plus aucun problème.
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

##Résultat

L'ordinateur n'a plus aucune latence et exploite pleinement les performances disponibles, tout en étant futur-proof pour de longue années.

##Bilan Personnelle

Cette expérience à pu me permettre de mettre en avant mes qualités de support à distance et ma pédagogie face à une situation difficile présenté devant un novice dans l'informatique.
J'en ressort une satisfaction de pouvoir aider avec mes connaissances, tout en étant encore qu'un passionné.
