# Configuration VS Code optimisée pour SailingLoc

Copie ce contenu dans ton fichier `.vscode/settings.json` pour optimiser GitHub Copilot :

```json
{
  // Configuration Copilot
  "github.copilot.enable": {
    "*": true,
    "yaml": true,
    "plaintext": false,
    "markdown": true,
    "typescript": true,
    "javascript": true,
    "json": true
  },
  "github.copilot.editor.enableAutoCompletions": true,
  "github.copilot.suggestions.count": 5,
  
  // TypeScript
  "typescript.preferences.includePackageJsonAutoImports": "on",
  "typescript.suggest.autoImports": true,
  "typescript.updateImportsOnFileMove.enabled": "always",
  
  // ESLint
  "eslint.validate": [
    "javascript",
    "typescript",
    "javascriptreact",
    "typescriptreact"
  ],
  "eslint.codeAction.showDocumentation": {
    "enable": true
  },
  
  // Formatting
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.organizeImports": true
  },
  
  // IntelliSense
  "editor.suggestSelection": "first",
  "editor.suggest.snippetsPreventQuickSuggestions": false,
  "editor.suggest.localityBonus": true,
  
  // Files
  "files.exclude": {
    "**/node_modules": true,
    "**/dist": true,
    "**/.git": true
  },
  
  // Workspace
  "explorer.fileNesting.enabled": true,
  "explorer.fileNesting.patterns": {
    "*.ts": "${capture}.js, ${capture}.d.ts, ${capture}.js.map",
    "*.tsx": "${capture}.js, ${capture}.d.ts, ${capture}.js.map"
  }
}
```

## Extensions recommandées

Ajoute ces extensions dans `.vscode/extensions.json` :

```json
{
  "recommendations": [
    "github.copilot",
    "github.copilot-chat",
    "ms-vscode.vscode-typescript-next",
    "dbaeumer.vscode-eslint",
    "bradlc.vscode-tailwindcss",
    "ms-vscode.vscode-json",
    "redhat.vscode-yaml"
  ]
}
```