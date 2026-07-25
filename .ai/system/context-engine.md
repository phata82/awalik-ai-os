---
id: ART-006
title: Context Engine
version: 1.0.0
status: Approved
owner: CTO
classification: Internal
depends_on:
  - ART-001
  - ART-002
  - ART-003
  - ART-004
  - ART-005
used_by:
  - AI Orchestrator
  - All AI Roles
last_updated: 2026-07-25
---

# ART-006 — Context Engine

# Objectif

Le Context Engine est responsable de construire le contexte optimal avant toute exécution.

Son rôle est de fournir aux assistants IA uniquement les informations pertinentes afin de réduire les erreurs, d'améliorer la cohérence et d'éviter les réponses hors contexte.

---

# Mission

Transformer une demande utilisateur en un contexte de travail structuré.

Le Context Engine ne produit jamais de code.

Il prépare le travail.

---

# Responsabilités

Le Context Engine doit :

* analyser la demande ;
* identifier le domaine fonctionnel ;
* identifier les modules concernés ;
* retrouver les artefacts utiles ;
* classer les informations par priorité ;
* transmettre un contexte propre à l'Orchestrator.

---

# Entrées

Le moteur reçoit :

* la demande utilisateur ;
* le projet concerné ;
* les métadonnées des artefacts ;
* les décisions d'architecture (ADR) ;
* les règles de la Constitution.

---

# Sortie

Le moteur produit un document appelé **Mission Context**.

Ce document contient :

* le projet concerné ;
* le domaine métier ;
* les composants concernés ;
* les artefacts à consulter ;
* les risques identifiés ;
* les rôles IA à activer ;
* les dépendances techniques ;
* les contraintes connues.

---

# Pipeline

Étape 1

Comprendre la demande.

↓

Étape 2

Identifier le domaine métier.

↓

Étape 3

Identifier les modules applicatifs.

↓

Étape 4

Rechercher les artefacts.

↓

Étape 5

Évaluer les dépendances.

↓

Étape 6

Classer les priorités.

↓

Étape 7

Construire le Mission Context.

↓

Étape 8

Transmettre à l'AI Orchestrator.

---

# Niveaux de priorité

Les artefacts sont classés selon quatre niveaux.

## Niveau 1 — Obligatoire

Toujours chargés.

Exemples :

* Constitution
* Vision
* Core Principles

---

## Niveau 2 — Métier

Selon le domaine.

Exemple :

Gestion locative

↓

Contrats

↓

Paiements

---

## Niveau 3 — Technique

Architecture

API

Base de données

Sécurité

---

## Niveau 4 — Support

Guides

Exemples

Templates

Historique

---

# Mission Context

Chaque mission possède un contexte unique.

Exemple :

Mission :

Créer la gestion des cautions.

Projet :

Awalik Immo

Modules :

Contrats

Paiements

Comptabilité

Artefacts :

ART-002 Constitution

ART-003 Vision

Architecture

Database

Workflow Feature

Prompt Backend

Prompt Frontend

Prompt QA

Risques :

Perte de données

Calcul financier

Permissions

RGPD

---

# Critères de qualité

Le Context Engine est considéré comme correct lorsque :

* aucun artefact essentiel n'est oublié ;
* aucun document inutile n'est chargé ;
* les rôles IA disposent du contexte nécessaire ;
* le Mission Context reste compréhensible par un humain.

---

# Règles

Le Context Engine ne modifie jamais les artefacts.

Il prépare uniquement le contexte.

Toute décision reste de la responsabilité de l'AI Orchestrator.
