*[English version](ROADMAP.en.md)*

# Feuille de route

Jalons techniques de Solar Community. Chaque version doit être fonctionnelle avant la suivante. Aucun jalon touchant à l'installation physique n'apparaît tant que `sho-safeguard` n'a pas validé le cadre de sécurité ([docs/safety/](docs/safety/README.md)).

## v0.1 — Outils logiciels de base
- [ ] Générateur de BOM minimal (`sho-kitbuilder`) : liste de composants pour un budget donné, avec sources
- [ ] Pipeline de cartographie de site (`sho-fieldmapper`) : ensoleillement annuel via Sentinel-2 pour un point GPS
- [ ] Revue `sho-safeguard` : confirmer qu'aucun des deux ne franchit la ligne installation physique

## v0.2 — Supervision
- [ ] Firmware de lecture production/batterie/onduleur, sur un nœud déjà installé par un tiers qualifié
- [ ] Format de payload validé par `sho-safeguard` et `sho-dataguard`-équivalent (pas de données personnelles des foyers)

## v0.3 — Ingestion réelle
- [ ] Backend Node.js + broker MQTT
- [ ] TimescaleDB : schéma de séries temporelles
- [ ] Le firmware v0.2 envoie vers le backend réel

## v0.4 — Dashboard minimal
- [ ] React + D3.js, une courbe, personnalisable
- [ ] Déploiement public, accès sans compte

## v0.5 — Équilibrage réel
- [ ] `sho-balancer` : daemon d'équilibrage MQTT, testé sur au moins deux nœuds simulés puis réels

## v1.0 — Premier pilote réel
- [ ] Déploiement avec des installateurs qualifiés (pas d'auto-installation)
- [ ] Mesures réelles de réduction de dépendance au réseau national — publiées seulement une fois mesurées, jamais anticipées
- [ ] Premier rapport `sho-trainer`/dashboard généré à partir de données réelles

---

Rien n'est figé : ce document évolue avec les décisions prises en issues/PR.
