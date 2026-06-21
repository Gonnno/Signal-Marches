# Signal Marchés · v3

Dashboard multi-marchés hébergeable sur GitHub Pages. Analyse en temps réel des semi-conducteurs, Nasdaq, bourse européenne, pétrole, or et crypto.

## Fonctionnalités

- **Vue globale** — 6 marchés + radar volatilité, sparklines historiques, indice Fear & Greed, carte vedette
- **Prédictions** — estimations 24h / 1 semaine avec sentiment actualités traduit en français
- **Portefeuille** — suivi P&L personnel, prix en temps réel, stockage local

## Sources de données

| Source | Usage |
|---|---|
| Finnhub | Quotes actions, ETF, bourse européenne |
| Binance / CoinGecko | Prix crypto |
| Finnhub News | Actualités par ticker |
| MyMemory | Traduction FR |

Historique des clôtures stocké en `localStorage` — s'enrichit à chaque analyse.

## Installation

1. Forker le repo ou créer un nouveau repo GitHub
2. Copier `index.html` à la racine
3. Activer GitHub Pages (Settings → Pages → `main` / `root`)
4. Remplacer la clé Finnhub ligne ~260 :

```js
const FH = 'VOTRE_CLE_FINNHUB';
```

Clé gratuite sur [finnhub.io](https://finnhub.io).

## Signaux

| Score | Signal |
|---|---|
| ≥ 60 | ACHAT |
| 43–59 | NEUTRE |
| ≤ 42 | VENTE |
| — | DANGER (≥ 2 alertes critiques) |

**Filtres de sécurité automatiques** : RSI > 75 · chute 5j > 8% · volatilité > 4%/j → signal neutralisé ou bloqué.

## Portefeuille

Saisir ticker + quantité + PRU. Les prix sont mis à jour à chaque analyse. Données sauvegardées dans le navigateur (`localStorage`).

## Avertissement

Outil informatif uniquement. Pas un conseil en investissement. Risque très élevé sur produits à levier.
