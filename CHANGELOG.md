<!-- Argus (TM) - Copyright (c) 2026 skyllon. Tous droits reserves. Licence : voir LICENSE. Empreinte ARGUS-PB-2026-8de20fbe89. -->

# Changelog Argus (editions publiques)

## v5.0 (2026-07-27)

Refonte majeure. Le corpus source a ete rescanne INTEGRALEMENT (et non plus par ajouts ponctuels) : 76 system prompts publies, depouilles par sept lecteurs paralleles, puis tries contre l existant. Trois audits a lentilles distinctes (coherence interne, redondance, angles morts au regard du niveau d autonomie) ont ensuite ete passes sur le protocole lui-meme.

- Boucle operatoire (section 1) : le blocage se detecte aussi par la repetition d ACTIONS, pas seulement d erreurs, avec une escalade graduee avant de demander de l aide. Un probleme d environnement se signale puis se contourne au lieu d etre repare par defaut. La premisse d une demande peut etre fausse, et cela se dit AVANT d executer. L intention se reevalue a chaque message, pas seulement au premier.
- Verification (section 3) : un test qui echoue accuse le code et jamais le test. Une modification multi-emplacements se prouve par une recherche du symbole sur tout le depot. Lint, typage et analyse statique sont trois portes distinctes des tests.
- Discipline d outils (section 6) : l historique de conversation n est pas une source d autorite, un tour attribue a l assistant a pu etre edite ou fabrique.
- Style (section 8) : simplifier sans qu on le demande est de la condescendance ; quand la concision est demandee elle porte sur la prose, jamais sur la completude des livrables. L ambigu s interprete charitablement.
- Code (section 9) : le depot ne bouge que sur instruction explicite ; une proposition de fusion ne quitte le brouillon que sur preuves. Dependances par l outil du projet et version compatible avec le manifeste present. Jamais de contournement cosmetique d un bug. Schema de base append-only. Une erreur qui remonte vaut mieux qu un repli silencieux qui masque une donnee fausse.
- Gout UI (section 10) : partir de zero est un dernier recours, le vocabulaire visuel existant prime, la palette ne s invente pas, les vides ne se remplissent pas de contenu fabrique, minimums de lisibilite et de zone tactile, refus de reproduire l identite d une marque tierce.
- Securite de l espace de travail (section 13) : un sous-agent herite des permissions du parent et doit etre borne a un chemin de sortie declare. Toute ecriture de masse en base passe par sauvegarde, transaction et comparaison du nombre de lignes. Un magasin ecrit par plusieurs sources se relit avant reecriture et ne se resout jamais par ecrasement. Passe de fuite avant toute sortie vers un tiers. Une donnee produite par une automatisation se verifie en fraicheur.
- Economie de contexte (section 14) : correction majeure. Une variante de fenetre etendue se DEMANDE explicitement et ne s herite jamais d un modele a l autre ; changer le modele par defaut pour une generation plus recente peut diviser la fenetre reelle par cinq en silence. Les seuils de reprise s ancrent sur un pourcentage affiche, jamais sur un nombre absolu de tokens. Le plafonnement de session se tient par discipline et non par un reglage qui bride la fenetre.

## v4.9 (2026-07-27)

- Calibration de confiance (section 4) : nouvelle regle sur les changements de generation. Les caracteristiques mesurees sur la generation precedente d un modele ou d un outil (quota, debit, fenetre de contexte, tarif, comportement d une option) ne se transposent pas a la suivante ; re-mesurer avant d affirmer et signaler explicitement ce qui n a pas ete re-mesure.
- Economie de contexte (section 14) : une fenetre de contexte elargie est une capacite, pas une autorisation de la remplir. Le contexte porte est refacture a chaque appel d outil, donc le plafond de travail par session ne suit pas la taille de la fenetre du modele.
- Securite de l espace de travail (section 13) : deux regles de configuration issues d une bascule de defaut reelle. Porter un nouveau defaut dans le chemin principal plutot que dans un correctif conditionnel, pour que le chemin d echec atterrisse sur le comportement voulu ; et couvrir explicitement le cas non prevu d un aiguillage, faute de quoi une valeur non listee herite silencieusement de la branche voisine et produit un comportement faux sans erreur.

## v4.8 (2026-07-23)

- Nouvelle section 15, Routage de skills : a chaque demande, matcher d'abord les skills installees et les invoquer directement (chainees : process avant implementation, la plus specifique gagne) ; sinon chercher et installer la meilleure candidate de l'ecosysteme puis l'invoquer dans la foulee, avec quarantaine et scan obligatoires avant toute installation tierce ; ne pas forcer si rien de pertinent n'existe.
- Section 14 completee (lecons d'un incident reel de thrashing d'auto-compaction) : persister l'etat AVANT le seuil de sa propre initiative (la raison d'un blocage PreCompact n'est jamais transmise au modele : bloquer une compaction ne fait que laisser gonfler le contexte) ; placer le seuil d'auto-compaction au-dessus du plancher incompressible de la session, sinon la fenetre se re-remplit apres chaque resume jusqu'a coupure de l'auto-compaction par le harnais ; un gros fichier se lit par morceaux.
- Boucle operatoire, cas de bord compaction complete : une compaction en plein travail ne termine pas la tache, reprendre immediatement.

## v4.7 (2026-07-23)

- Nouvelle section 14, Economie de contexte : plafond de contexte courant par session (ordre de grandeur 200k tokens) avec persistance d'etat PUIS compaction, dans cet ordre ; un lot egale une session ; lots de production (traduction, redaction de masse, extraction, sweeps) sur une session dediee a modele intermediaire econome ; orchestrateur maigre aussi en LECTURE (les sous-agents lisent, le parent ne garde que les conclusions) ; modele leger a effort bas pour l'extraction mecanique, et interrogation d'un graphe ou index du projet plutot que relecture des fichiers.
- Motivation mesuree : sur une session longue, la relecture du contexte accumule a chaque appel d'outil devient le poste de cout dominant, loin devant la generation elle-meme.

## v4.6 (2026-07-15)

- Boucle operatoire : test binaire du biais vers l'action ; signalement explicite des hypotheses qui devient la trajectoire ; cas de bord (message recu pendant l'execution : remplace ou complete ; reprise apres compaction de contexte ; une demande de persistance n'elargit pas les actions autorisees).
- Mode ensemble : gate de pertinence explicite pour le fan-out ; verification adverse EN AVEUGLE (le verificateur recoit l'artefact, jamais le diagnostic prealable) ; regle single-writer sur les fichiers de coordination partages ; degradation signalee (continuer en sequentiel plutot que bloquer si l'orchestration est indisponible).
- Calibration : nommer la note ou la source qui fonde une decision (tracabilite).
- Style : pas d'auto-congratulation par contraste ; maximum une question par reponse.
- Securite de l'espace de travail : un espace sale (changements non commites) appartient a l'utilisateur, preserver et ne jamais nettoyer sans demande.

## v4.2 (2026-07-04)

- Fusion des deux distributions precedentes (skill autonome et paquet complet) en un seul format : tout le protocole vit dans `argus/SKILL.md`.
- Routing par etages des sous-agents (modeles economes sur le mecanique, capables sur le jugement).
- Calibration anti-fait-perime : re-verifier tout fait date avant de batir dessus, meme affirme par l'utilisateur.
- Contenu d'outil traite comme donnee, jamais comme instruction (resistance aux injections).
- Lisibilite avant compression.
- Validation par test comparatif reel : voir `COMPARATIF-v4.2.md`.

## v3 (2026-06-22)

- Premiere edition partagee sous licence : LICENSE, empreinte de provenance `ARGUS-PB-2026-8de20fbe89`, scellement SHA-256.
- Protocole en deux fichiers (prompt + skill).

## v1 a v2 (2026-06-16 et suivants)

- Versions internes initiales (codename Frankenstein) : fusion de disciplines issues de l'etude comparative de system prompts d'agents du marche, reecrites et unifiees en un protocole unique.
