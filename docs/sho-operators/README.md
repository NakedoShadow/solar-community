*[English version](README.en.md)*

# Shadow Hermes Operators (SHO)

Même modèle que [BioSentinel](https://github.com/NakedoShadow/biosentinel/blob/master/docs/sho-operators/README.md) : chaque **SHO** est un profil [Hermes](https://github.com/NousResearch/Hermes-Agent) isolé en Bot Mode, un rôle et un périmètre précis. Solar Community en introduit un cinquième par rapport à BioSentinel : `sho-safeguard`, parce que ce projet touche à un risque physique (électricité) que BioSentinel n'avait pas.

## Les cinq opérateurs

### `sho-kitbuilder`
**Rôle :** compiler des listes de composants open source (panneaux, contrôleurs, batteries) et générer des BOM (Bill of Materials) adaptées à différents budgets.
**Périmètre :** recommandation avec sources, pas d'instruction d'installation. Sortie dans `bom/`.

### `sho-fieldmapper`
**Rôle :** utiliser des données GPS et de l'imagerie satellite libre (Sentinel-2) pour identifier les emplacements optimaux — ensoleillement annuel, impact environnemental.
**Périmètre :** analyse et recommandation de sites, pas d'action sur le terrain. Sortie dans `siting/`.

### `sho-trainer`
**Rôle :** créer des tutoriels et ateliers pour que chaque participant utilise le logiciel (dashboard, monitoring, génération de BOM) de façon autonome.
**Périmètre :** pédagogie logicielle uniquement. **Aucun tutoriel de câblage ou d'installation électrique** tant que `sho-safeguard` n'a pas validé un cadre (voir [docs/safety/](../safety/README.md)).

### `sho-balancer`
**Rôle :** équilibrer la répartition d'énergie entre les nœuds du réseau, via le protocole MQTT open source, en continu.
**Périmètre :** logiciel pur, opère sur des nœuds déjà installés et raccordés par des tiers qualifiés.

### `sho-safeguard`
**Rôle :** garde-fou sécurité électrique et réglementaire. Audite tout contenu ou fonctionnalité qui toucherait, même indirectement, à l'installation physique d'un système électrique.
**Périmètre :** revue, droit de veto — même position que `sho-dataguard` chez BioSentinel, mais sur la sécurité physique plutôt que la vie privée. Un refus de `sho-safeguard` bloque un merge, point final.

## Statut

Bootstrap : les cinq profils existent, ont un rôle défini (`SOUL.md`), câblés sur DeepSeek (`deepseek-v4-flash`) comme le reste de Hermes. **Pas encore activés** — même contrainte de crédit que BioSentinel, réactivation après recharge.
