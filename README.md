# TimeTravel Agency — Webapp Interactive

Webapp pour une agence de voyage temporel fictive, développée dans le cadre du projet supervisé IA M2.

---

## Membres du groupe

> - Léa PERIN
> - Kyrian PEROUMAL

---

## Lien de la webapp déployée

> https://nerlyss1.github.io/timetravel-agency/#

---

## Stack technique

| Technologie | Usage |
|---|---|
| HTML5 / CSS3 | Structure et design de la webapp |
| JavaScript vanilla | Interactivité, quiz, chatbot, validation formulaire |
| AOS (Animate On Scroll) v2.3 | Animations au scroll (CDN) |
| GitHub Pages | Hébergement et déploiement |

---

## Fonctionnalités implémentées

### Phase 1 — Architecture
- [x] Définition des features (page d'accueil, galerie, chatbot, formulaire)
- [x] Maquette mentale : Header → Hero → Destinations → Quiz → Réservation → Footer

### Phase 2 — Code & Assets
- [x] Hero section avec animation d'étoiles scintillantes et design dark mode premium
- [x] Navigation fixe responsive (mobile + desktop) avec effet de compression au scroll
- [x] Galerie de 3 destinations temporelles avec cards interactives et images générées (projet 1)
- [x] Design cohérent : thème sombre, accents dorés
- [x] Formulaire de réservation complet (Phase 2 optionnel) :
  - Sélection destination + dates + nombre de voyageurs
  - Calcul du prix en temps réel
  - Validation automatisée (champs requis, email, date future)
  - Page de confirmation avec référence de réservation

### Phase 2.3 — Animations (exercice optionnel)
- [x] **AOS (Animate On Scroll)** — fade-up progressif sur les sections, cards et titres au scroll
- [x] **Micro-interactions boutons** — hover lift + halo doré, effet ripple au clic
- [x] **Hover cards** — zoom image, translateY élastique, halo sombre
- [x] **Animations hero** — entrée en cascade (badge → titre → texte → boutons)
- [x] **Barre de progression** — indicateur de scroll doré/violet en haut de page
- [x] **Nav scroll** — compression de la hauteur après 60px de scroll
- [x] **Chatbot** — anneau pulsant sur le bouton, ouverture animée de la fenêtre
- [x] **Quiz** — chaque nouvelle étape glisse depuis la droite

### Phase 3 — IA & Agents
- [x] **Chatbot Chloé** — agent conversationnel intelligent basé sur un moteur de classification par mots-clés (sans API externe, fonctionne offline) avec réponses variées, délai simulé et historique visuel
- [x] **Quiz de personnalisation** (exercice 3.2) — 4 questions, recommandation de destination avec algorithme de scoring basé sur les réponses

### Phase 4 — Déploiement
- [x] README complet
- [x] Déployé sur GitHub Pages

---

## Destinations

| Destination | Époque | Prix de base |
|---|---|---|
| Paris 1889 | Belle Époque | 12 400 € / 7 jours |
| Crétacé | -65 millions d'années | 28 900 € / 5 jours |
| Florence 1504 | Renaissance italienne | 18 700 € / 6 jours |

---

## Outils IA utilisés

| Usage | Outil / Modèle |
|---|---|
| Génération et assistance au code | Claude Sonnet 4.6 (Claude Code / claude.ai) |
| Agent conversationnel (Chloé) | Moteur rule-based JS — classification par mots-clés |
| Recommandations quiz | Algorithme de scoring JS (offline) |
| Visuels destinations | Images générées par IA (projet 1) |

---

## Architecture du chatbot

Le chatbot Chloé fonctionne sans API externe. Un moteur de classification analyse le message de l'utilisateur par expressions régulières et sélectionne la catégorie de réponse :

| Catégorie détectée | Mots-clés déclencheurs |
|---|---|
| `paris` | paris, belle époque, tour eiffel, 1889, exposition |
| `cretace` | crétacé, dinosaure, t-rex, vélociraptor, préhistorique |
| `florence` | florence, renaissance, michel-ange, david, léonard, 1504 |
| `prix` | prix, coût, tarif, combien, budget |
| `reservation` | réserver, réservation, book, acompte, date |
| `inclus` | inclus, comprend, service, fourni, kit |
| `securite` | sécurité, danger, risque, assurance |

Chaque catégorie dispose de 2 variantes de réponse alternées pour éviter la répétition.

---

## Prompt Chloé (personnalité définie)

```
Tu es Chloé, la conseillère virtuelle de TimeTravel Agency, une agence de voyage temporel de luxe.
Ton rôle : conseiller les clients sur les meilleures destinations temporelles.
Ton ton : professionnel mais chaleureux, passionné d'histoire, enthousiaste sans être trop familier.
Tu connais parfaitement :
- Paris 1889 (Belle Époque, Tour Eiffel, Exposition Universelle)
- Crétacé -65M (dinosaures, nature préhistorique)
- Florence 1504 (Renaissance, art, Michel-Ange)
Prix : Paris 12 400€/7j — Florence 18 700€/6j — Crétacé 28 900€/5j
```

---

## Installation locale

```bash
git clone https://github.com/nerlyss1/timetravel-agency.git
cd timetravel-agency
# Ouvrir index.html dans un navigateur
# Aucune dépendance, aucun build requis
```

---

## Déploiement GitHub Pages

1. Pusher le code sur GitHub
2. `Settings` → `Pages` → Source : `main` / `root`
3. L'URL est disponible en quelques minutes

---

## Réflexion sur le processus

Ce projet nous a permis d'explorer le **vibe coding** et l'intégration d'animations et d'interactivité dans une webapp sans framework. Les points clés appris :

- L'importance de **ne pas dépendre d'APIs externes** pour des fonctionnalités critiques (le chatbot fonctionne offline grâce au moteur rule-based)
- La **validation de formulaire côté client** : regex email, contrainte de date future, affichage d'erreurs inline
- Le **prompt engineering** pour définir la personnalité d'un agent et structurer ses réponses
- Trouver le bon équilibre entre **animations fluides** et performance (AOS avec `once: true`, transitions CSS optimisées)

---

## Licence

Projet pédagogique — M2 — Usage éducatif uniquement.
