# Guide du catalogue de presets (BSM)

Les presets Better Sound Maker (BSM) se partagent via le **catalogue de presets
BetterCommunity**. Un preset est un simple fichier JSON décrivant une configuration
sonore et les fichiers d'assets qu'il utilise. Ce guide couvre le format et la
publication.

> [!REMARQUE]
> Un preset contient toutes ses métadonnées *dans* le JSON — pas d'entrée de
> catalogue à remplir séparément. Envoie le `.json` et le catalogue le lit.

---

## 1. Format JSON d'un preset

```json
{
  "name": "Afterburner Boom",
  "version": "1.0.0",
  "color": "#f97316",
  "UpdateNumber": 3,
  "date": "2026-07-01",
  "assetPaths": [
    "sounds/ab_ignite.wav",
    "sounds/ab_loop.wav",
    "sounds/ab_cut.wav"
  ]
}
```

| Champ | Type | Requis | Rôle |
|---|---|---|---|
| `name` | string | **Oui** | Nom affiché |
| `version` | string | **Oui** | Version SemVer |
| `assetPaths` | string[] | **Oui** | Chemins relatifs des assets sonores utilisés |
| `color` | string | Non | Couleur d'accent (`#rrggbb`) de la carte |
| `UpdateNumber` | number | Non | À incrémenter à chaque mise à jour |
| `date` | string | Non | Date `AAAA-MM-JJ` de dernière mise à jour |

Le serveur valide ce format à l'envoi — un preset invalide est refusé avec les
champs fautifs.

---

## 2. Publier dans le catalogue

1. Ouvre **Tableau de bord → Soumettre du contenu**.
2. Projet = **BSM**, Type = **Preset** (BSM ne propose que des presets).
3. Choisis ton `.json` — l'éditeur remplit automatiquement le nom/la version.
4. Envoie. Un modérateur vérifie avant publication.

> [!ASTUCE]
> Utilise **Générer un modèle** dans la fenêtre d'envoi pour partir d'une base valide.

---

## 3. Télécharger des presets

Dans le **Catalogue** (filtré sur BSM) tu peux :

- **Télécharger** un preset depuis sa carte ou sa page.
- **En sélectionner plusieurs** avec les cases puis **Télécharger la sélection**.
- **Trier/filtrer** par *Plus populaires (all-time)*, *Populaires ce mois*, *Récents*
  ou *Plus vus*.

Chaque téléchargement est compté : les auteurs voient combien de fois leurs presets
ont été téléchargés dans les stats de l'élément.

---

## 4. Mettre à jour un preset

Incrémente `version` (et `UpdateNumber`), renvoie via **Mes éléments → proposer une
mise à jour**. Le changement est re-vérifié avant de remplacer la version en ligne.
