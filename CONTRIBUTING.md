*[English version](CONTRIBUTING.en.md)*

# Contribuer à Solar Community

Le projet est jeune (voir [ROADMAP.md](ROADMAP.md)). Lisez d'abord le [WHITEPAPER.md](WHITEPAPER.md) et [docs/safety/](docs/safety/README.md) — la contrainte de sécurité électrique n'est pas négociable et gouverne ce qui peut ou non entrer dans ce dépôt.

## Comment contribuer

1. Forkez, créez une branche descriptive (`bom/panel-catalog`, `siting/sentinel2-pipeline`, etc.).
2. Ouvrez une issue avant une grosse PR si le changement touche à l'architecture.
3. Committez petit et clair.
4. Décrivez le *pourquoi* dans la PR, pas seulement le *quoi*.

## Règle absolue : toute PR touchant à l'installation physique passe par `sho-safeguard`

Toute contribution qui, même indirectement, oriente vers l'installation, le câblage ou le raccordement électrique doit être explicitement validée du point de vue sécurité avant merge (voir [docs/safety/](docs/safety/README.md)). Tant que les opérateurs SHO ne sont pas activés, cette revue est faite manuellement par le mainteneur, avec la même rigueur. En cas de doute, la PR est refusée par défaut — ce n'est pas à l'auteur de la PR de prouver qu'elle est sans risque, c'est la charge de la preuve inverse.

## Proposer un composant matériel

Format `sho-kitbuilder` : une note dans `firmware/notes/` ou `bom/`, avec lien datasheet, prix/disponibilité, pourquoi ce choix, limites connues.

## Proposer un site ou une méthode de cartographie

Format `sho-fieldmapper` : documentez la source de données (Sentinel-2 ou équivalent libre), la méthode d'évaluation, et les limites de précision.

## Style de code

Pas encore figé — les premiers outils logiciels (v0.1, voir [ROADMAP.md](ROADMAP.md)) poseront les conventions.

## Rapporter un problème

- **Bug technique** → template *Bug report*.
- **Proposition de composant** → template *Component proposal*.
- **Préoccupation sécurité électrique** → template *Safety concern*, traité en priorité absolue.

## Licence de vos contributions

Toute contribution est soumise à la licence [MIT](LICENSE) du projet.
