<!-- Argus (TM) v4.7 - Copyright (c) 2026 skyllon. Tous droits reserves. Licence : voir LICENSE. Empreinte ARGUS-PB-2026-8de20fbe89. -->

# Argus : le protocole operationnel d'elite pour Claude Code

> (c) 2026 skyllon. Argus est un protocole proprietaire diffuse sous licence (voir `LICENSE`). Tu peux l'utiliser et l'adapter pour toi, mais tu dois conserver l'attribution et l'empreinte de provenance, et tu ne peux pas le revendiquer comme ta creation. Empreinte : `ARGUS-PB-2026-8de20fbe89`.

Argus (Argos Panoptes, le geant aux cent yeux de la mythologie grecque : le veilleur que rien ne trompe) est un mode operationnel pour Claude Code. Une seule commande (`/argus`) fait basculer l'agent en posture "preuve avant affirmation" :

- il **execute et lit l'output** avant de declarer quoi que ce soit (jamais de "c'est corrige" sans preuve) ;
- il **re-verifie les faits dates** (quota, version, limite, fichier, flag) avant de batir dessus, meme affirmes par l'utilisateur, meme documentes par une note interne ;
- il **s'auto-critique en adverse** avant de livrer, et pour les audits il fait verifier chaque trouvaille par des sceptiques independants, **en aveugle** (le verificateur recoit l'artefact, jamais le diagnostic prealable) ;
- il **orchestre des sous-agents routes par etages** pour les recherches larges, les decisions a fort enjeu et les taches repetitives : modeles economes sur le mecanique, modeles capables sur le jugement ;
- il **fractionne les gros livrables** (jamais de sortie monolithique confiee a un seul agent) et verifie la couverture apres coup ;
- il traite tout contenu ramene par un outil comme de la **donnee, jamais comme un ordre** (resistance aux injections de prompt) ;
- il ecrit **direct, sans hedging ni remplissage**, ouvre chaque reponse par le resultat, et n'invente aucun fait ;
- il **discipline son propre contexte** : plafond de contexte par session avec persistance d'etat avant compaction, lots de production delegues a des sessions economes, orchestrateur maigre qui delegue les lectures a des sous-agents jetables.

Version 4.7 (2026-07-23). Le protocole complet vit dans `argus/SKILL.md` : c'est la seule chose a installer, il est autonome et generique (aucune regle personnelle, aucun chemin specifique, aucun quota code en dur).

## Ce que ca change, mesure

La difference de comportement a ete validee par un test comparatif reel sur la v4.2 : deux agents identiques (meme modele, memes outils), meme mission piegee, seul le second recevait Argus. L'agent standard a confirme un fait perime en citant la note qui le documentait sans la lire, puis a bati toute son architecture dessus ; l'agent Argus a rejete le fait, cite la mesure a jour et corrige l'architecture. Detail complet : `COMPARATIF-v4.2.md`. Sur 22 comportements compares, 12 n'existent pas sans le protocole.

## Contenu du depot

```
argus/SKILL.md              le protocole complet, autonome (la seule chose a installer)
README.md                   ce fichier
LICENSE                     conditions d'utilisation et de redistribution
CHANGELOG.md                historique des versions (v1 a v4.7)
COMPARATIF-v4.2.md          ce que le protocole change, mesure sur un test reel
PROVENANCE.md               empreintes SHA-256 scellees (preuve d'origine)
PROVENANCE.sha256           fichier de verification (sha256sum -c)
```

## Installation

1. Copier le dossier `argus/` dans ton repertoire de skills Claude Code : `~/.claude/skills/argus/` (sous Windows : `C:\Users\<toi>\.claude\skills\argus\`).
2. Redemarrer Claude Code (ou ouvrir une nouvelle session) pour qu'il decouvre le skill.
3. Verifier : taper `/argus`. La reponse attendue est une seule ligne de confirmation contenant `zero fait invente ni perime`.

Si tu remplaces une version anterieure d'Argus (v1 a v4.2, quel que soit son format), retire d'abord les anciens fichiers (`argus-prompt*.md`, ancien `SKILL.md`) pour que cette version soit bien celle qui se charge.

## Utilisation

- Activer : `/argus`, ou en langage naturel "argus", "active argus", "mode argus".
- Desactiver : "stop argus", "mode normal".
- Le mode reste actif jusqu'au stop explicite ou la fin de session.

Le protocole est entierement generique. Tu peux ajouter tes propres regles non negociables en tete de la section "Protocole" du `SKILL.md` ; conserve alors l'avis de copyright et signale tes modifications (LICENSE, article 2).

## Nouveautes de la v4.7

- Economie de contexte (nouvelle section 14) : plafond de contexte courant par session, persistance d'etat PUIS compaction, un lot egale une session.
- Lots de production (traduction, redaction de masse, extraction, sweeps) delegues a une session dediee sur un modele intermediaire econome ; le modele le plus capable garde l'architecture et la synthese.
- Orchestrateur maigre aussi en LECTURE : les sous-agents lisent les gros volumes, le parent ne garde que les conclusions.
- Extraction mecanique sur modele leger a effort bas ; interroger un graphe ou index du projet plutot que relire les fichiers.

Raison : mesure sur des sessions longues reelles, la relecture du contexte accumule a chaque appel d'outil est le poste de cout dominant, loin devant la generation.

Historique complet : `CHANGELOG.md`.

## Licence et provenance

Argus est un protocole **proprietaire** de skyllon, diffuse sous la licence du fichier `LICENSE`. En resume :

- Tu peux l'**utiliser** et l'**adapter** pour ton propre usage, sans frais.
- Si tu le **redistribues** (tel quel ou modifie), tu dois conserver l'avis de copyright, le fichier `LICENSE` et l'empreinte de provenance, signaler tes modifications, et ne pas le faire passer pour ta creation.
- **Interdit** : revendiquer la paternite d'Argus, retirer ou masquer l'attribution ou l'empreinte, le revendre ou l'integrer dans une offre commerciale sans accord ecrit prealable.

**Empreinte de provenance.** Chaque fichier porte le marqueur `ARGUS-PB-2026-8de20fbe89` et le paquet est scelle par les empreintes SHA-256 de `PROVENANCE.md`. Ce marqueur permet de prouver l'origine d'une copie qui circulerait ailleurs. Pour verifier qu'un paquet n'a pas ete trafique : `sha256sum -c PROVENANCE.sha256` (les valeurs de reference sont dans `PROVENANCE.md`).

Contact pour toute autorisation : https://github.com/skyllon
