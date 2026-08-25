*[English version](README.en.md)*

# Sécurité électrique — contrainte de conception

## La règle

**Solar Community ne publie aucun contenu qui pousse une personne à installer seule un système électrique** (panneaux, câblage, onduleur, raccordement batterie ou réseau). Ce n'est pas une question de prudence excessive : une installation solaire mal faite est un risque d'incendie et d'électrocution réel, et dans la plupart des juridictions, le raccordement au réseau électrique est soumis à des règles (certification, contrôle par un professionnel) que ce projet n'a ni la légitimité ni la compétence de contourner.

Cette règle est **au même niveau de priorité** que la contrainte vie privée de `sho-dataguard` chez BioSentinel : non négociable, avec droit de veto de l'opérateur responsable (`sho-safeguard`) sur tout contenu ou fonctionnalité qui l'enfreint.

## Ce qui est dans le périmètre du projet dès maintenant

- **Firmware de supervision** — lecture de production, de charge batterie, d'état onduleur. Aucune de ces tâches ne demande de manipuler du courant à l'installation : elles lisent des points de mesure déjà présents sur du matériel certifié.
- **Génération de BOM** (`sho-kitbuilder`) — recommander des composants, avec sources et prix. Recommander n'est pas guider l'installation.
- **Cartographie de sites** (`sho-fieldmapper`) — analyse d'imagerie satellite, aucune manipulation physique.
- **Équilibrage de charge** (`sho-balancer`) — logiciel pur, MQTT entre nœuds déjà installés.
- **Tutoriels logiciels** (`sho-trainer`) — utiliser le dashboard, configurer le monitoring, lire ses données. Pas de tutoriel de câblage.

## Ce qui est explicitement hors périmètre pour l'instant

- Tout guide pas-à-pas de câblage, de raccordement onduleur/batterie, ou de raccordement au réseau.
- Toute fonctionnalité qui présenterait une installation DIY comme suffisante sans validation par un professionnel qualifié.

## Ce qu'il faudrait pour lever cette limite un jour

Avant d'envisager un contenu touchant à l'installation physique, il faudrait au minimum :
1. Une revue par une personne qualifiée (électricien certifié), pas seulement par l'équipe du projet.
2. Des avertissements et des références explicites aux normes locales, avec clause de non-responsabilité claire — et probablement des variantes par pays/région plutôt qu'un guide unique.
3. Un mode par défaut qui oriente vers un professionnel/installateur certifié plutôt que vers l'auto-installation, avec l'auto-installation en option clairement marquée comme telle, pour les juridictions qui l'autorisent.

Tant que ces conditions ne sont pas réunies, `sho-safeguard` bloque. C'est un blocage volontaire, pas un oubli.
