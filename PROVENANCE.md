# Provenance et integrite - Argus (TM) v4.8

Copyright (c) 2026 skyllon. Tous droits reserves.
Contact : https://github.com/skyllon

Ce fichier scelle le paquet Argus v4.8 (scellement du 2026-07-23, remplace le
scellement v4.7 du meme jour). Il sert de preuve d'origine et permet de
detecter toute alteration. Voir `LICENSE` pour les conditions d'utilisation.

## Empreinte de provenance (canary)

    ARGUS-PB-2026-8de20fbe89

Ce marqueur est present dans chaque fichier du paquet. Il identifie cette oeuvre
comme celle de skyllon. Le retirer ou l'alterer constitue une violation
de licence (LICENSE, articles 3 et 5). Le meme marqueur scelle les versions
anterieures (v1 a v4.7) : l'anteriorite est continue depuis 2026-06-16.

## Empreintes SHA-256 (paquet scelle, v4.8 du 2026-07-23)

    69e316b6b7a81a91b757f9f98f467dd1c081e0643cdeb44db65e86807f05479e  LICENSE
    17ec63a4ca6d41be1f712750f9feb9fd0397d3c13ce70e72f1460703e44fa49b  argus/SKILL.md
    48cec9a7ddd94a85ef36c3240c617a3caa014dacbda9b63fce5df52916d3fd29  README.md
    43b0e2018fd7f655439fe97a4550810fb5055355c7d401a1b35c4611f1cf91d7  CHANGELOG.md
    d28e9ca4c46ad9903aff8892f910c270b0ad012a6f7a587c048379dcb790588a  COMPARATIF-v4.2.md

Empreinte globale du paquet (concatenation des 5 fichiers ci-dessus, dans cet ordre) :

    085b6bceaab38f693700112c0d748e178377d7dc20c4bd01000ea2fb54e61465

Empreintes globales des scellements precedents, conservees pour l'anteriorite :

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
