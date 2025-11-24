# Qu’est-ce que Git ?
Git est un logiciel de gestion de versions (ou versioning) créé en 2005 par Linus Torvalds, le fondateur de Linux. Un tel outil permet de conserver l’historique des modifications d’un projet, d’identifier rapidement les changements effectués et de revenir à une version antérieure en cas de problème.

Aujourd’hui, les systèmes de gestion de versions sont devenus indispensables :

Ils simplifient la gestion des projets.

Ils facilitent le travail collaboratif.

Parmi ces outils, Git s’impose comme la référence incontournable. Tout développeur doit en maîtriser l’usage.

## À quoi sert un système de gestion de versions ?
Prenons l’exemple d’un site web :

Chaque modification ou ajout de fonctionnalité nécessite une sauvegarde préalable pour éviter les pertes en cas d’erreur.

Ce processus est lourd mais gérable tant qu’une seule personne travaille sur le projet.

Maintenant, imaginez une équipe de 10 développeurs travaillant simultanément sur différentes fonctionnalités :

Il faut éviter que leurs contributions entrent en conflit.

Chacun doit savoir sur quoi les autres travaillent.

Tous doivent disposer d’une version à jour du projet pour tester et intégrer leurs ajouts.

La solution logique est de mettre en place un serveur central qui conserve l’historique des modifications. Chaque développeur peut alors copier le projet en local pour travailler dessus. C’est le principe d’un système de gestion de versions décentralisé.

Git va plus loin en offrant des fonctionnalités robustes et pratiques :

Synchronisation automatique entre le dossier local et le serveur.

Gestion des différences entre versions.

Coordination fluide entre plusieurs contributeurs.

### Avec Git :

Plusieurs versions d’un même fichier peuvent coexister.

L’historique complet du projet est accessible : qui a modifié quoi, quand et pourquoi.

## Les deux modèles de gestion de versions
Les logiciels de gestion de versions reposent sur deux approches :

Modèle centralisé

Le code source est stocké sur un serveur unique.

Les utilisateurs doivent se connecter à ce serveur pour travailler.

Modèle décentralisé (ou distribué)

Le code est toujours hébergé sur un serveur distant.

Mais chaque utilisateur télécharge une copie complète du projet sur sa machine.

Git a popularisé ce modèle distribué, qui présente deux grands avantages :

Flexibilité : on peut travailler hors ligne sur sa propre copie.

Sécurité : chaque copie complète du projet peut servir de sauvegarde en cas de problème sur le serveur central.

# Qu’est-ce que GitHub ?
Git est le logiciel qui gère les versions. GitHub, lui, est une plateforme en ligne qui héberge les dépôts (repositories ou repos) Git.

C’est le plus grand hébergeur de dépôts Git au monde.

Beaucoup de projets y sont publics : chacun peut télécharger le code et proposer des améliorations.

# En résumé :

Git = outil de gestion de versions.

GitHub = service d’hébergement des dépôts Git, jouant le rôle de serveur central.

Dans la suite du cours, nous verrons en détail comment utiliser GitHub après avoir appris à manipuler Git.
