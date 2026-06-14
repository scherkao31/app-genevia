# app-genevia

Configuration de **Lancya Workspace** : un workspace IA souverain basé sur [LibreChat](https://www.librechat.ai), avec inférence hébergée en Suisse chez [Infomaniak AI](https://www.infomaniak.com/fr/hosting/ai-services).

## Contenu

- `librechat.yaml` : configuration LibreChat (endpoint Infomaniak, modèles exposés, interface).

## Modèles exposés

- **Apertus** (`swiss-ai/Apertus-70B-Instruct-2509`) : défaut, modèle suisse.
- **Mistral Small** (`mistralai/Mistral-Small-4-119B-2603`) : boost qualité.

## Déploiement

Le fichier `librechat.yaml` est lu par LibreChat via la variable d'environnement `CONFIG_PATH`, pointée sur l'URL raw de ce repo.

Variables d'environnement requises côté hébergeur (Railway, VPS, etc.) :

| Variable | Description |
|---|---|
| `INFOMANIAK_API_KEY` | Token API Infomaniak (scope `ai-tools`). Secret, jamais committé. |
| `PRODUCT_ID` | Identifiant du produit AI Infomaniak. |
| `CONFIG_PATH` | URL raw de `librechat.yaml`. |
