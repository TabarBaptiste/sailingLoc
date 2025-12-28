# Politique de sécurité

## Divulgation responsable

Nous apprécions les efforts des chercheurs en sécurité qui nous aident à maintenir la sécurité de notre projet. Si vous découvrez une vulnérabilité de sécurité, veuillez nous en informer de manière responsable.

**Ne créez pas d'issues publiques** pour les vulnérabilités de sécurité. Au lieu de cela, contactez-nous directement via [email@example.com](mailto:email@example.com) ou via un canal privé.

Nous nous engageons à :

- Répondre rapidement aux rapports de sécurité.
- Collaborer avec vous pour résoudre le problème.
- Créditer les découvreurs dans nos notes de version, si souhaité.

## Versions supportées

Nous fournissons des mises à jour de sécurité pour les versions suivantes :

- Version actuelle et les deux dernières versions majeures.

Veuillez mettre à jour vers la dernière version pour bénéficier des correctifs de sécurité.

## Bonnes pratiques

- **Stockage des secrets** : Utilisez GitHub Secrets pour stocker les clés API, mots de passe et autres informations sensibles. Ne les commitez jamais dans le code.
- **Fichiers sensibles** : Évitez de committer des fichiers comme `.env`, `.key`, ou tout fichier contenant des informations confidentielles. Utilisez `.gitignore` pour les exclure.
- **Dépendances** : Mettez régulièrement à jour les dépendances pour éviter les vulnérabilités connues.
- **Authentification** : Utilisez des méthodes d'authentification fortes, comme l'authentification à deux facteurs (2FA).
- **Chiffrement** : Chiffrez les données sensibles en transit et au repos.

## Contact

Pour toute question relative à la sécurité, contactez-nous à [email@example.com](mailto:email@example.com).

Merci de contribuer à la sécurité de notre projet !
