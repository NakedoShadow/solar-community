# Security Policy / Politique de sécurité

*For electrical/physical safety concerns (not code vulnerabilities), see [docs/safety/](docs/safety/README.en.md) instead. / Pour une préoccupation de sécurité électrique/physique (pas une vulnérabilité de code), voir [docs/safety/](docs/safety/README.md).*

## English

Solar Community's software touches internet-connected monitoring hardware and an MQTT-based control layer between grid nodes — a real attack surface (spoofed telemetry, malicious MQTT messages disrupting load balancing, credential leakage). If you find a security vulnerability (firmware, backend, dashboard, or deployment tooling), **please do not open a public issue.**

Use GitHub's private vulnerability reporting: **Security** tab of this repository → **Report a vulnerability**. If unavailable, open a normal issue titled `[security] please contact` with no technical detail, and the maintainer will reach out privately.

We'll acknowledge reports as fast as we can — young, mostly-volunteer project, please be patient. Once fixed, we'll credit reporters (unless you'd rather stay anonymous) in the fix's changelog.

## Français

Le logiciel de Solar Community touche du matériel de supervision connecté et une couche de contrôle MQTT entre les nœuds du réseau — une vraie surface d'attaque (télémétrie falsifiée, messages MQTT malveillants perturbant l'équilibrage de charge, fuite d'identifiants). Si vous découvrez une faille de sécurité (firmware, backend, dashboard, outillage de déploiement), **merci de ne pas ouvrir d'issue publique.**

Utilisez le signalement privé de vulnérabilités de GitHub : onglet **Security** de ce dépôt → **Report a vulnerability**. Si indisponible, ouvrez une issue classique intitulée `[security] please contact` sans détail technique, et le mainteneur vous recontactera en privé.

Les signalements seront traités aussi vite que possible — projet jeune, essentiellement bénévole, merci de votre patience. Une fois corrigé, les personnes à l'origine du signalement seront créditées (sauf préférence pour l'anonymat) dans le changelog du correctif.
