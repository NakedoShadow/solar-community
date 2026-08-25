*[English version](WHITEPAPER.en.md)*

# Solar Community — Livre blanc

**Version 0.1 — 26 août 2026**

---

## Résumé

Solar Community est un framework open source pour concevoir, dimensionner et superviser des micro-réseaux solaires communautaires, indépendamment des fournisseurs d'énergie centralisés. Il repose sur quatre principes : **décentralisation** (micro-réseaux autonomes mais interconnectés), **transparence** (code, schémas et protocoles publiés sous licence MIT), **évolutivité** (matériel modulaire, DIY accepté au niveau logiciel) et **co-création** (chaque communauté personnalise son propre dashboard). Le projet est né comme une intention formulée par ADA, une interface d'intelligence agentique open source, dans la continuité directe de [BioSentinel](https://github.com/NakedoShadow/biosentinel).

Ce document complète [README.md](README.md) (démarrage rapide), [ROADMAP.md](ROADMAP.md) (jalons) et [CONTRIBUTING.md](CONTRIBUTING.md) (comment participer).

## 1. Le problème

L'accès à l'énergie solaire reste, dans beaucoup de communautés, médié par des acteurs qui imposent leurs propres règles : matériel propriétaire, tarifs de rachat opaques, dépendance à un fournisseur unique pour le dimensionnement comme pour la maintenance. Une communauté qui veut simplement produire et partager son énergie localement n'a souvent pas accès aux outils qui lui permettraient de le faire en connaissance de cause — combien de panneaux, où les poser, comment répartir la charge entre foyers.

## 2. Pourquoi l'open source, et pourquoi MIT

Même refus de dépendance propriétaire que dans tous les projets initiés par ADA : le code, les schémas électriques et les protocoles de communication sont publics et auditables dès le premier commit. Le choix de licence diffère cependant de BioSentinel (GPL-v3) : Solar Community adopte la licence **MIT**, plus permissive. Ce choix est délibéré — un framework de dimensionnement et de supervision énergétique se répand plus vite s'il peut être repris tel quel par des installateurs, des coopératives locales ou des fabricants de matériel, y compris dans des offres commerciales, sans obligation de reverser leurs propres ajouts. La transparence du cœur du projet est garantie par la publication elle-même, pas par la contrainte de licence.

## 3. Les principes fondateurs

- **Décentralisation** — chaque micro-réseau fonctionne de façon autonome, tout en restant interconnecté pour partager l'excédent d'énergie avec ses voisins.
- **Transparence** — code, schémas électriques et protocoles de communication publiés et consultables par tous.
- **Évolutivité** — le système accepte des capteurs de batterie, des onduleurs DIY, et des solutions de stockage thermique, sans architecture figée.
- **Co-création** — les communautés locales personnalisent leur propre tableau de bord, avec les visualisations qui reflètent leurs priorités (réduction d'empreinte carbone, autonomie alimentaire, etc.).

## 4. Architecture technique

| Pilier | Techno | Rôle |
|---|---|---|
| Firmware de supervision (`firmware/`) | Arduino-compatible | Lecture production/batterie/onduleur |
| Génération de BOM (`bom/`) | Scripts / données ouvertes | Listes de composants par budget |
| Cartographie de sites (`siting/`) | Imagerie Sentinel-2 | Évaluation ensoleillement/impact |
| Plateforme de données (`backend/`) | Node.js + MQTT + TimescaleDB | Ingestion, équilibrage de charge |
| Dashboard (`dashboard/`) | React + D3.js | Visualisation personnalisable |

### Flux de données

```
[Nœud installé — panneaux + onduleur + batterie, par des tiers qualifiés]
   │ télémétrie (production, charge, état) via MQTT
   ▼
[Backend Node.js] ──► [TimescaleDB]
   │
   ├──► [sho-balancer] — ajuste la répartition entre nœuds, toutes les heures
   ▼
[Dashboard React/D3 — personnalisable par communauté]
```

Le firmware et le backend ne s'occupent que de *mesurer* et *équilibrer* un système déjà installé — jamais de guider son installation (section 6).

## 5. Gouvernance : humain, ADA, et les opérateurs SHO

Même modèle à trois niveaux que BioSentinel : le mainteneur humain décide et garde la responsabilité finale, ADA délègue plutôt que de tout construire elle-même, et cinq **Shadow Hermes Operators (SHO)** — agents Hermes en Bot Mode — portent chacun un rôle isolé : `sho-kitbuilder` (composants), `sho-fieldmapper` (sites), `sho-trainer` (pédagogie logicielle), `sho-balancer` (équilibrage MQTT), et `sho-safeguard` (garde-fou sécurité électrique et réglementaire, droit de veto). Détails : [docs/sho-operators/](docs/sho-operators/README.md).

## 6. Sécurité électrique : la contrainte qui prime sur tout le reste

Solar Community touche à un risque que BioSentinel n'avait pas : l'électricité. Une installation solaire mal faite est un risque d'incendie et d'électrocution réel, et le raccordement au réseau est encadré par la loi dans la plupart des juridictions. **Ce projet ne publiera donc aucun guide poussant une personne à installer seule un système électrique.** Le firmware de supervision (lecture de mesures sur du matériel déjà installé par des professionnels) est dans le périmètre ; le câblage et le raccordement ne le sont pas, tant qu'un cadre de sécurité n'a pas été validé — au minimum une revue par un électricien certifié, des avertissements conformes aux normes locales, et un défaut qui oriente vers un professionnel plutôt que vers l'auto-installation. Détail complet : [docs/safety/](docs/safety/README.md).

## 7. Une précision sur l'origine de ce document

La graine originelle du projet (le Dream Memory d'ADA du 24 août 2026) décrit un premier pilote déployé dans un village fictif, avec des chiffres précis de réduction d'énergie et de CO₂. **Ce pilote n'a jamais eu lieu.** Ce livre blanc reprend la vision et les principes de cette graine, mais traite ses chiffres de déploiement comme des objectifs à atteindre et valider en conditions réelles (voir [ROADMAP.md](ROADMAP.md)), jamais comme un résultat déjà obtenu.

## 8. Feuille de route

Résumé — détail dans [ROADMAP.md](ROADMAP.md) :

- **v0.1** — Générateur de BOM minimal + pipeline de cartographie de site (Sentinel-2, un point GPS).
- **v0.2** — Firmware de supervision (lecture production/batterie) sur un nœud déjà installé par un tiers qualifié.
- **v0.3** — Backend MQTT + TimescaleDB, ingestion réelle.
- **v0.4** — Dashboard minimal, personnalisable.
- **v0.5** — `sho-balancer` : équilibrage réel entre au moins deux nœuds.
- **v1.0** — Premier pilote réel, chiffres mesurés (pas supposés) sur la réduction de dépendance au réseau.

## 9. Comment contribuer

Voir [CONTRIBUTING.md](CONTRIBUTING.md). Toute proposition touchant, même indirectement, à l'installation physique passe par une revue `sho-safeguard` avant merge — sans exception.

## 10. Licence

[MIT](LICENSE) — redistribution, modification et usage commercial autorisés, y compris dans des offres fermées construites par-dessus.

---

*Ce document évolue avec le projet.*
