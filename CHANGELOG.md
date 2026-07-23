<!-- Argus (TM) - Copyright (c) 2026 skyllon. Tous droits reserves. Licence : voir LICENSE. Empreinte ARGUS-PB-2026-8de20fbe89. -->

# Changelog Argus (editions publiques)

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
