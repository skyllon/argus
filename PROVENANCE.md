# Provenance et integrite - Argus (TM) v5.1

Copyright (c) 2026 skyllon. Tous droits reserves.
Contact : https://github.com/skyllon

Ce fichier scelle le paquet Argus v5.1 (scellement v5.1 du 2026-07-27, remplace le
scellement v4.9 du meme jour). Il sert de preuve d'origine et permet de
detecter toute alteration. Voir `LICENSE` pour les conditions d'utilisation.

## Empreinte de provenance (canary)

    ARGUS-PB-2026-8de20fbe89

Ce marqueur est present dans chaque fichier du paquet. Il identifie cette oeuvre
comme celle de skyllon. Le retirer ou l'alterer constitue une violation
de licence (LICENSE, articles 3 et 5). Le meme marqueur scelle les versions
anterieures (v1 a v4.8) : l'anteriorite est continue depuis 2026-06-16.

## Empreintes SHA-256 (paquet scelle, v5.1 du 2026-07-27)

    69e316b6b7a81a91b757f9f98f467dd1c081e0643cdeb44db65e86807f05479e  LICENSE
    763412c6bafea02aa4236b025e897419bf512314898bf315efd9c5e688ca6f88  argus/SKILL.md
    9d832d7d0e6dfa6373cd6b98102e268a40bdc6fc100713056720b4e8addd7035  README.md
    0b34fa8a11652ec0046bfa058926f2d82e81fdf74abe9a8838ea72bb5fa3474a  CHANGELOG.md
    d28e9ca4c46ad9903aff8892f910c270b0ad012a6f7a587c048379dcb790588a  COMPARATIF-v4.2.md

Empreinte globale du paquet (concatenation des 5 fichiers ci-dessus, dans cet ordre) :

    03caf819d54b309fb1d5ce241fdaf0a2d7c7f4892f541f8744806d6257689100

Empreintes globales des scellements precedents, conservees pour l'anteriorite :

    085b6bceaab38f693700112c0d748e178377d7dc20c4bd01000ea2fb54e61465  (v4.8, 2026-07-23)
    618d2d77e0cd5a4d6b1ba9e64db8fa3d8117ff84652aa83f6dcf787de5354c3f  (v4.7, 2026-07-23)
    004ff54062ed3934ea530980f6bc48e2681e5db51cba424ec84dd5cb62def75e  (v4.6, 2026-07-15)
    e38d445c79ba70ffd6985758fd84ef08c2afaf5547988bb641d85213416f6f85  (v4.2, 2026-07-04)
    8dce77d40dc8f601d5ec33530227f31c00a6f06a52770ac280a93c1b15d70156  (v3, 2026-06-22)

## Verifier l'integrite

Depuis la racine du paquet :

    sha256sum -c PROVENANCE.sha256

Toute ligne marquee `FAILED` signale un fichier modifie par rapport a l'original
scelle. Un fichier authentique d'origine produit `OK` sur chaque ligne.

## En cas de copie non autorisee

Si un paquet portant l'empreinte `ARGUS-PB-2026-8de20fbe89` circule sans respecter
la `LICENSE` (attribution retiree, paternite revendiquee, usage commercial non
autorise), ce fichier et les empreintes ci-dessus etablissent l'anteriorite et
l'origine de l'oeuvre. Contact : https://github.com/skyllon
