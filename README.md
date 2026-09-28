# Pipeline Automatisé PIM E-commerce : Scraping, IA Locale & Airtable

Projet d'automatisation démontrant la mise en place d'un pipeline complet d'ingestion de données catalogue, d'enrichissement sémantique par modèle de langage local et de synchronisation relationnelle.

## Architecture de la solution

1. **Extraction de données (Scraping)** : Récupération dynamique des fiches produits, visuels, prix et fils d'Ariane sans doublons.
2. **Qualification sémantique (LLM Local)** : Extraction d'attributs techniques normalisés (matières, certifications écologiques, bénéfices clés) via Ollama en format JSON strict.
3. **Modélisation PIM Relationnelle (Airtable)** :
   - Gestion d'une taxonomie multi-niveaux (Rayons Niveau 1 -> Sous-rayons Niveau 2).
   - Gestion de l'idempotence (Upsert) pour garantir l'absence de doublons lors des réexécutions.

## Stack technique

- **Orchestration** : n8n
- **Traitement IA** : Ollama (LLM local / Privacy-first)
- **Base de données / PIM** : Airtable
- **Transformation** : JavaScript (Node.js)

## Comment importer ce workflow

1. Télécharger le fichier `ecommerce-pim-enrichment-workflow.json`.
2. Dans n8n, créer un nouveau workflow, cliquer sur `...` puis `Import from file`.
3. Renseigner vos propres identifiants Airtable et votre URL cible dans les nœuds correspondants.
