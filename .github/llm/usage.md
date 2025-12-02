# Utilisation interne - LLM
Ces fichiers servent de base pour intégrer un assistant (local ou SaaS) qui aiderait au dev (ex: revue de PR, génération d'exemples). Pour automatiser :
1. Créer un workflow GitHub qui appelle une action (self-hosted / cloud) et lui passer les prompts ci-dessus
2. Restreindre l'accès (GH secrets) et loguer toute sortie pour audit


Attention : ne jamais envoyer de secrets (ex : clés privées) dans les prompts.