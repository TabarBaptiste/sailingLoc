# Contribuer à SailingLoc 🚤

Merci de contribuer au projet SailingLoc ! Ce guide t'aidera à maximiser l'efficacité avec GitHub Copilot.

## 🚀 Démarrage rapide

### Installation
```bash
npm ci
npm run setup  # Configure les hooks git et l'environnement
```

### Commandes essentielles
```bash
npm test           # Lance tous les tests
npm run lint       # Vérification ESLint
npm run typecheck  # Vérification TypeScript
npm run build      # Build de production
```

## 📝 Standards de contribution

### 1. Branches et commits
- **Branches** : `feature/nom-fonctionnalite`, `fix/nom-bug`, `docs/mise-a-jour`
- **Commits** : Respecte [Conventional Commits](https://conventionalcommits.org/)
  ```
  feat: ajoute la recherche de bateaux par prix
  fix: corrige le calcul des réductions
  docs: met à jour le guide d'installation
  ```

### 2. Pull Requests
- Cible toujours la branche `develop` (sauf urgences vers `main`)
- Utilise le template de PR fourni
- Assure-toi que la CI passe (lint, tests, typecheck)
- Demande une review avant merge

## 🧠 Optimisation GitHub Copilot

### Configuration recommandée
1. Installe les extensions VS Code (voir `.github/llm/vscode-setup.md`)
2. Configure ton workspace selon nos standards
3. Utilise les prompts définis dans `.github/llm/`

### Techniques de codage pour Copilot

#### ✅ Commentaires descriptifs
```typescript
/**
 * Calcule le prix total d'une location incluant les options et réductions
 * @param basePrice Prix de base du bateau par jour
 * @param duration Durée de location en jours
 * @param options Options supplémentaires sélectionnées
 * @param userType Type d'utilisateur pour les réductions
 * @returns Prix total calculé avec toutes les charges
 */
function calculateTotalRentalPrice(
  basePrice: number,
  duration: number,
  options: RentalOption[],
  userType: UserType
): number {
  // Copilot suggèrera automatiquement l'implémentation
}
```

#### ✅ Nommage explicite
```typescript
// ✅ Bon - Copilot comprend le contexte
const findAvailableBoatsInDateRange = (startDate: Date, endDate: Date) => { }
const validateUserPaymentInformation = (paymentData: PaymentData) => { }

// ❌ À éviter - Context flou pour Copilot
const find = (d1: Date, d2: Date) => { }
const validate = (data: any) => { }
```

#### ✅ Structure modulaire
```typescript
// Sépare la logique en modules focused
export class BoatRentalService {
  constructor(
    private readonly boatRepository: BoatRepository,
    private readonly priceCalculator: PriceCalculator,
    private readonly notificationService: NotificationService
  ) {}

  // Méthodes courtes et spécifiques
  public async createRental(request: CreateRentalRequest): Promise<Rental> {
    // Implémentation guidée par Copilot
  }
}
```

### Types TypeScript précis
```typescript
// ✅ Types explicites pour de meilleures suggestions
interface BoatSearchFilters {
  readonly priceRange: {
    readonly min: number;
    readonly max: number;
  };
  readonly capacity: number;
  readonly boatType: 'sailboat' | 'motorboat' | 'catamaran';
  readonly location: GeoLocation;
  readonly availableDates: DateRange;
}

// Évite les 'any' - utilise des unions ou génériques
type ApiResponse<T> = 
  | { success: true; data: T }
  | { success: false; error: string };
```

## 🧪 Tests et qualité

### Tests guidés par Copilot
```typescript
describe('BoatRentalService', () => {
  // Copilot générera les tests basés sur ces descriptions
  it('should calculate correct price with weekend surcharge', () => {
    // Test implementation guided by Copilot
  });

  it('should apply loyalty discount for returning customers', () => {
    // Implementation
  });
});
```

### Documentation JSDoc
- Toujours documenter les fonctions publiques
- Utilise des exemples d'usage
- Spécifie les cas d'erreur possibles

## 🔧 Architecture recommandée

```
src/
├── domain/              # Logique métier pure
│   ├── entities/       # Entités business
│   ├── repositories/   # Interfaces de persistance
│   └── services/       # Services de domaine
├── application/         # Use cases et orchestration
│   ├── usecases/       # Cas d'usage spécifiques
│   └── dto/           # Data Transfer Objects
├── infrastructure/      # Implémentations concrètes
│   ├── database/       # Repos et migrations
│   ├── external/       # APIs externes
│   └── config/        # Configuration
└── interfaces/          # Controllers et adapters
    ├── http/           # REST controllers
    ├── websocket/      # WebSocket handlers
    └── cli/           # Commandes CLI
```

## 🚨 Règles de sécurité

- ❌ **Jamais de secrets** dans le code (utilise les variables d'environnement)
- ❌ **Pas de console.log** en production
- ✅ **Validation** de toutes les entrées utilisateur
- ✅ **Sanitization** des données avant persistance
- ✅ **Rate limiting** sur les APIs publiques

## 📚 Ressources

- [Guide Copilot](.github/llm/copilot-guide.md)
- [Configuration VS Code](.github/llm/vscode-setup.md)
- [Prompts système](.github/llm/system_prompt.md)
- [Architecture du projet](docs/architecture.md)

## ❓ Aide

- Problème avec Copilot ? Consulte le guide de troubleshooting
- Questions sur l'architecture ? Ouvre une discussion GitHub
- Bug trouvé ? Crée une issue avec le template approprié