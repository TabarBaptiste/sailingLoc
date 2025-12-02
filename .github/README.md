# Configuration GitHub pour SailingLoc

Ce dossier contient toute la configuration GitHub optimisée pour maximiser l'efficacité de développement avec GitHub Copilot.

## 📁 Structure

```
.github/
├── workflows/           # Actions GitHub CI/CD
│   ├── copilot-optimized.yml    # CI principale optimisée
│   ├── copilot-review.yml       # Review automatique
│   └── pr_checks.yml            # Vérifications PR
├── ISSUE_TEMPLATE/      # Templates d'issues
│   ├── bug.md
│   └── feature_request.md
├── llm/                 # Configuration LLM/Copilot
│   ├── system_prompt.md         # Prompt système
│   ├── copilot-guide.md        # Guide d'utilisation
│   ├── vscode-setup.md         # Configuration VS Code
│   └── usage.md               # Instructions d'usage
├── dependabot.yml      # Mises à jour automatiques
└── security.md        # Politique de sécurité
```

## 🚀 Workflows automatisés

### `copilot-optimized.yml`
- Lint avec annotations GitHub
- Type checking TypeScript
- Tests avec couverture
- Audit de sécurité
- Analyse CodeQL

### `copilot-review.yml`
- Review automatique des PR
- Détection de console.log
- Vérification des types 'any'
- Suggestions d'optimisation Copilot

### `pr_checks.yml`
- Validation des titres de PR (Conventional Commits)
- Labeling automatique
- Checks de qualité de base

## 🧠 Configuration LLM/Copilot

### Optimisations incluses
- Prompts système adaptés au projet
- Guide d'utilisation des meilleures pratiques
- Configuration VS Code recommandée
- Standards de documentation pour Copilot

### Utilisation
1. Lis le guide dans `llm/copilot-guide.md`
2. Configure VS Code selon `llm/vscode-setup.md`
3. Utilise les prompts définis dans `llm/system_prompt.md`

## 🔧 Configuration locale recommandée

1. **Extensions VS Code** (voir `llm/vscode-setup.md`)
   - GitHub Copilot + Chat
   - TypeScript + ESLint
   - Prettier

2. **Hooks Git**
   ```bash
   npm run setup  # Configure commitlint et autres hooks
   ```

3. **Variables d'environnement**
   ```bash
   cp .env.example .env.local
   # Remplis les valeurs nécessaires
   ```

## 📊 Métriques et monitoring

- **Quality gates** : ESLint, TypeScript, Tests
- **Security** : CodeQL, npm audit, Dependabot
- **Performance** : Bundle analysis, Coverage tracking
- **Maintenance** : Automatic dependency updates

## 🎯 Objectifs de cette configuration

1. **Maximiser l'efficacité de Copilot** avec des conventions claires
2. **Maintenir la qualité** avec des checks automatisés
3. **Sécuriser le développement** avec des analyses continues
4. **Faciliter la collaboration** avec des templates et guides

## 🔄 Maintenance

Cette configuration est évolutive. Pour proposer des améliorations :
1. Ouvre une issue avec le template feature_request
2. Documente les bénéfices attendus
3. Teste les modifications sur une branche feature/
4. Soumets une PR avec les changements

---

*Configuration maintenue par @TabarBaptiste*