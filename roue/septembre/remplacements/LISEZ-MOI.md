# Remplacer une image de la Roue sans toucher au code

Déposer ici un PNG nommé exactement comme le calque à remplacer, puis relancer
l'extraction de sa planche :

    node scripts/extraire-calques.mjs roue-medaillons --composer --verifier

Le PNG est servi à la place de l'image tirée du fichier Illustrator, à la même
place et à la même taille. Le manifeste note alors `"origine":
"client-remplacement"`.

Noms attendus, tels qu'ils figurent dans `content/roue/calques/*.json` :

- `medaillon-serenite.png` … `medaillon-magie.png` : les douze médaillons ;
- `vignette-serenite.png` … `vignette-magie.png` : les douze vignettes des
  panneaux d'élément.

Aucun fichier n'est obligatoire : sans dépôt, c'est l'image de la planche du
client qui est servie.

## Médaillons : état au 28 septembre 2026

Les médaillons servis sont ceux que le client a détourés lui-même dans
« Roue des relations médaillons.ai » (22 septembre), lus à leur résolution
native (1254 px) par `python3 scripts/extraire-medaillons.py`. Ce dossier ne
contient donc aucun médaillon.

Les JPG du 16 septembre (`images/`, hors dépôt) restent le repli, médaillon par
médaillon, si une image du .ai n'a pas la résolution de la vue agrandie et que
le JPG en a davantage : `python3 scripts/preparer-medaillons.py images` dépose
alors ici le médaillon détouré, puis relancer `scripts/extraire-medaillons.py`
et l'extraction de la planche. Au 28 septembre, aucun médaillon n'est dans ce
cas (même résolution des deux côtés).
