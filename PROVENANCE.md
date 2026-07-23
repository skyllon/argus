# Provenance et integrite - Argus (TM) v4.7

Copyright (c) 2026 skyllon. Tous droits reserves.
Contact : https://github.com/skyllon

Ce fichier scelle le paquet Argus v4.7 (scellement du 2026-07-23, remplace le
scellement v4.6 du 2026-07-15). Il sert de preuve d'origine et permet de
detecter toute alteration. Voir `LICENSE` pour les conditions d'utilisation.

## Empreinte de provenance (canary)

    ARGUS-PB-2026-8de20fbe89

Ce marqueur est present dans chaque fichier du paquet. Il identifie cette oeuvre
comme celle de skyllon. Le retirer ou l'alterer constitue une violation
de licence (LICENSE, articles 3 et 5). Le meme marqueur scelle les versions
anterieures (v1 a v4.6) : l'anteriorite est continue depuis 2026-06-16.

## Empreintes SHA-256 (paquet scelle, v4.7 du 2026-07-23)

    69e316b6b7a81a91b757f9f98f467dd1c081e0643cdeb44db65e86807f05479e  LICENSE
    a9125e61e10e6d66e8da1a1defef4f839dffcb23ac6bad093da7374d3d473900  argus/SKILL.md
    71e90d0b7f038c225c6f84c2048059f3a3acd3ae1dd114f1300a0bf7f953f5ab  README.md
    3f4f605f393bb854ed6689f617fdf153a2f1775d9bc8fd3bbec62868a7bf870b  CHANGELOG.md
    d28e9ca4c46ad9903aff8892f910c270b0ad012a6f7a587c048379dcb790588a  COMPARATIF-v4.2.md

Empreinte globale du paquet (concatenation des 5 fichiers ci-dessus, dans cet ordre) :

    618d2d77e0cd5a4d6b1ba9e64db8fa3d8117ff84652aa83f6dcf787de5354c3f

Empreintes globales des scellements precedents, conservees pour l'anteriorite :

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
