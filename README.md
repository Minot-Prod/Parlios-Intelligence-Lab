# Parlios Intelligence Lab

Ce repo définit le **cerveau expérimental Parlios 7.x** :
- architecture multi-agents (UA / MA / MAP + agents spécialisés),
- catalogue de capacités (skills) basé sur tes outils existants,
- connaissances et stratégies (UA Knowledge, prompts gold),
- profils de gouvernance (`lab` vs `prod`),
- protocole d’utilisation pour ChatGPT.

**Objectif :** fournir un socle d’intelligence **maximale** en mode LAB, sans les contraintes
de production (budgets, quotas, blocages automatiques). Les contraintes "prod" restent possibles,
mais sont optionnelles et désactivées par défaut.

## Structure

- `profiles/` : profils d’exécution (lab, prod).
- `core/agents/` : définitions d’agents (UA, Master Agent, MAP).
- `skills/` : registre des capacités disponibles (GitHub, n8n, Supabase, HTTP, etc.).
- `knowledge/` : index de ta base de connaissance (UA Knowledge + docs ZIP + autres repos).
- `runners/chatgpt/` : instructions pour qu’un GPT custom charge et respecte ce kernel.
- `evaluation/` : scénarios de test et scorecards pour mesurer les performances.

## Usage typique

1. **Tu clones ce repo** et le pousses sur GitHub.
2. Tu l’utilises de deux façons :
   - soit en **uploadant les fichiers** dans un GPT custom,
   - soit via un **tool GitHub** pour que le GPT lise ce repo en live.
3. Tu demandes à ton GPT de suivre les instructions dans `runners/chatgpt/bootstrap_instructions.md`.

Ce repo est conçu comme un **LAB** :
- profil par défaut = `lab` (exploration maximale),
- les contraintes type Base44 / budgets / blocages sont **hors** chemin critique.
