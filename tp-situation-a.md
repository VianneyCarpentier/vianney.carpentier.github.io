# Remplacement d'un switch d'étage saturé

[← Retour au portfolio](tp-camille.html)

*PME de métallurgie, 45 postes, site principal — mars 2026 — option SISR*

## Contexte

Le site principal compte 45 postes, dont 12 dans l'atelier, reliés à un switch d'étage installé en 2016. Les postes de l'atelier servent aux plans de fabrication et à la saisie des temps.

## Problématique

Depuis trois semaines, les 12 postes de l'atelier subissaient des coupures réseau de quelques secondes, plusieurs fois par jour. La sauvegarde du serveur de fichiers, lancée à 12 h, durait 42 minutes au lieu des 6 minutes habituelles et terminait parfois en erreur.

## Démarche

J'ai d'abord relevé les débits depuis un poste de l'atelier : 8 Mo/s en copie vers le serveur, contre 74 Mo/s depuis un poste du bureau. Trois hypothèses : le câblage, la carte réseau des postes, le switch.

J'ai écarté le câblage : les liens ont été certifiés en 2023 et un test au testeur de câble sur trois prises n'a rien montré. J'ai écarté la carte réseau : le problème touchait les 12 postes, pas un seul.

Restait le switch, un modèle 16 ports à 100 Mb/s dont les compteurs affichaient des erreurs de collision. Je l'ai remplacé par un switch administrable gigabit prêté par le fournisseur, pour valider l'hypothèse avant tout achat.

## Outils mobilisés

- Switch administrable 16 ports gigabit (modèle de prêt, puis modèle acheté)
- Testeur de câble RJ45
- Wireshark 4.2 pour observer les retransmissions
- GLPI 10.0 pour le suivi du ticket et la mise à jour de l'inventaire

## Précautions prises

J'ai sauvegardé la configuration de l'ancien switch, étiqueté les 16 câbles avant de les débrancher, et programmé l'intervention entre 12 h 30 et 13 h 15, hors production. J'ai prévenu le chef d'atelier la veille.

## Résultats

Le débit de copie est passé de 8 Mo/s à 74 Mo/s. La sauvegarde est redescendue à 6 minutes. Aucune coupure signalée dans les trois semaines qui ont suivi. L'inventaire GLPI a été mis à jour le jour même.

## Bilan personnel

J'ai perdu deux jours à suspecter le câblage alors que les compteurs d'erreurs du switch donnaient la réponse dès le premier relevé. La prochaine fois, je commencerai par interroger les équipements réseau en SNMP avant de tester les liens un par un.

---

**Compétences mobilisées** : gérer le patrimoine informatique ; répondre aux incidents et aux demandes d'assistance.

##Situation B

RÉCIT BRUT — À TRANSFORMER, NE PAS RECOPIER TEL QUEL

Voici ce que Camille a raconté à l'oral, en vrac. À vous de le réécrire dans la trame en six blocs.

« Y a un poste au bureau d'études qui redémarrait tout seul, genre 3 ou 4 fois par jour, ça durait depuis une quinzaine de jours et la personne perdait son travail à chaque fois. J'ai regardé l'observateur d'événements, y avait des Kernel-Power 41. J'ai d'abord cru à Windows, j'ai fait les mises à jour, ça a rien changé. Après j'ai pensé à la RAM, j'ai lancé un memtest une nuit, 0 erreur. Du coup j'ai ouvert le poste, l'alim était pleine de poussière et le ventilateur faisait un bruit bizarre. J'ai mesuré la conso avec une prise wattmétrique, le poste tirait 310 W en pointe avec une alim de 350 W, donc limite. J'ai remplacé l'alim par une 550 W, j'ai nettoyé, et depuis plus aucun redémarrage en un mois. J'étais content parce que c'était ma première panne matérielle trouvée tout seul. Faudrait que je pense à vérifier l'alim plus tôt la prochaine fois. »

## CONTEXTE

L'entreprise Ballon-à-GOGO possède 15 postes de travaille au sein du bureau d'étude, le mois dernier l'un de des postes à commencé à montrer des redémarrages spontannés qui causent de pertes de temps, dû à la suppression du travaille en cour sur le poste.

## PROBÉLMATIQUE:

"Le 24/09/2019 Un des postes de modèle d'ordinateur Lenovo ThinkCenter (WH-564-LN-6) tour du bureau d'étude a commencé à rencontrer des redémarrages spontanés de 3 à 4 fois par jour, ce qui a fait perdre énormément de temps aux personnes l'utilisant dû aux pertes du travail effectué. Cette problématique à durée une quinzaine de semaine.

## DÉMARCHE

Afin de porter un premier diagnostique j'ai accédé au logiciel "observateur d'événements" de windows. J'y ai constaté une erreur critique récurrente de type Kernel 41. Par précaution j'ai vérifié que toute les mise à jour les plus récente étaient effectuées et installé celles qui manquaient. Le problème c'est montré toujours présent, donc j'y ai soupçonné un problème de RAM défectueuse. J'ai donc effectué un memtest via le logiciel MemTest86 une nuit entière , mais celui-ci s'est montré dépourvu d'erreur.
Je me suis donc penché directement sur la machine en y dévissant la plaque latérale. J'y ai trouvé un ordinateur encrassé dans la poussière, mais ce qui m'a particulièrement heurté, a été l'alimentation ayant un ventilateur travaillant difficilement. J'ai donc éteint l'ordinateur, je l'ai débranché du secteur, je suis resté appuyé 30 secondes sur le bouton de décharge de l'alimentation le temps que l'alimentation se vide et sécurisé le matériel, une fois sécurisé, j'ai sorti l'ordinateur des bureau pour l'installer dans la cour de l'entreprise pour y passer un coup de souffleur en bloquant les ventilateur à l'aide d'une tige et un nettoyage au chiffon antistatique. Une fois rallumé toujours désossé le problème c'est montré de nouveau, j'ai donc effectué une prise de consommation en pleine charge à l'aide d'une prise wattmétrique , à l'issue du test la valeur de 310 W en pique est apparu, j'ai donc vérifié les spécification de l'alimentation, qui était une alimentation de 350 W forma ATx de production interne sans certification. J'ai donc immédiatement commandé une nouvelle alimentation de 550 W de certification 80+ Bronze auprès de l'intégrateur en précisant le numéro de série du modèle d'ordinateur utilisé, pour remplacé l'alimentation que j'ai considéré comme non-viable. Dès la réception de la nouvelle alimentation j'ai procédé au remplacement de l'ancienne. 
Je suis contente d'avoir pu agir et d'avoir résoulu le problème matériel par mon seul raisonnement et pour la première fois.
À l'avenir je mettrai l'alimentation en premier coupable face à  une erreur identique.

## OUTILS MOBILISÉS

- Logiciel windows: Observateur d'événements
- Logiciel MemTest86
- Tourne-vis crusiforme
- Wattmètre de marque Perel
- Soufleur de marque COMPUCLEANER XPERT
- Chiffon antistatique
- Nouvelle alimentation de 550 W 80+ Bronze de conception OEM

## RÉSULTAT

Le poste n'a plus montré de redémarrage spontané depuis le remplacement de l'alimentation et le service en est ravie par le fait qu'il puisse travailler sans le stresse de potentiellement tout perdre à tout moment.

## Bilan Personnelle

Malgré une recherche de panne fastidieuse de 2 jours, je suis contente d'avoir pu mettre le doigt sur le problème. J'en ai retenu de la confiance en moi accru et de la motivation de persévérer pour développer mes compétences en supports

Depuis le remplacement, aucun redémarrage spontané n'a été notifié pour le moment.
Ce qu'il manque et que vous devrez inventer de façon plausible : la date, le modèle exact du matériel, et la précaution prise avant d'ouvrir le poste.
