# Guide d'utilisation optimale de GitHub Copilot

## Configuration de l'environnement

### 1. Extensions VS Code recommandées
- GitHub Copilot
- GitHub Copilot Chat
- TypeScript Importer
- ESLint

### 2. Configuration Copilot
```json
{
  "github.copilot.enable": {
    "*": true,
    "yaml": false,
    "plaintext": false,
    "markdown": true,
    "typescript": true,
    "javascript": true
  },
  "github.copilot.editor.enableAutoCompletions": true,
  "github.copilot.suggestions.count": 3
}
```

## Techniques pour optimiser Copilot

### 1. Commentaires descriptifs
```typescript
// Fonction pour calculer le prix total d'une location de bateau
// en tenant compte des réductions, de la durée et des options
function calculateBoatRentalPrice(
  basePrice: number, 
  duration: number, 
  discount: number,
  options: RentalOption[]
): number {
  // Copilot va suggérer l'implémentation basée sur ce commentaire
}
```

### 2. Nommage explicite
```typescript
// ✅ Bon
const validateUserEmailFormat = (email: string) => { /* ... */ }

// ❌ Éviter
const validate = (e: string) => { /* ... */ }
```

### 3. Structure de projet claire
```
src/
  domain/          # Logique métier
  infrastructure/  # Adapters externes
  application/     # Use cases
  interfaces/      # Controllers, DTOs
```

### 4. Types explicites
```typescript
interface BoatRental {
  id: string;
  boatId: string;
  userId: string;
  startDate: Date;
  endDate: Date;
  totalPrice: number;
  status: 'pending' | 'confirmed' | 'cancelled';
}
```

## Prompts Copilot Chat efficaces

### Pour générer du code
```
/explain cette fonction fait quoi exactement ?
/fix ce code a un problème de performance
/tests génère des tests unitaires pour cette fonction
/doc ajoute la documentation JSDoc
```

### Pour l'architecture
```
Aide-moi à implémenter le pattern Repository pour la gestion des bateaux
Comment structurer cette feature en suivant l'architecture hexagonale ?
```

## Bonnes pratiques spécifiques

1. **Contexte local** : Garde les fichiers liés ouverts dans l'éditeur
2. **Commentaires de contexte** : Ajoute des commentaires qui expliquent le métier
3. **Tests first** : Écris les tests avant l'implémentation
4. **Types avant tout** : Définis les types/interfaces en premier
5. **Refactoring guidé** : Utilise Copilot pour identifier les améliorations