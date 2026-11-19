# 🎮 Game Center

> Une plateforme web rétro-arcade & tycoon regroupant deux jeux complets, immersifs et 100% autonomes en JavaScript natif, jouables directement dans le navigateur sans aucune installation.

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](#)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](#)
[![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](#)
[![Web Audio API](https://img.shields.io/badge/Web_Audio_API-Synth-blueviolet?style=for-the-badge)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](#)

---

## 🧭 Sommaire

- [Vue d'ensemble](#-vue-densemble)
- [Les Jeux Inclus](#-les-jeux-inclus)
  - [1. 💰 Thune Simulator v3.1](#1--thune-simulator-v31)
  - [2. 🧟 Zombie Survivor.io — Bunker OS v7.0](#2--zombie-survivorio--bunker-os-v70)
- [Architecture & Fichiers du Projet](#-architecture--fichiers-du-projet)
- [Démarrage Rapide](#-démarrage-rapide)
- [Technologies & Conception](#-technologies--conception)
- [Codes Secrets](#-codes-secrets-zombie-survivorio)

---

## 🌟 Vue d'ensemble

**Game Center** est une suite de jeux web indépendants développés pour offrir une expérience fluide, rapide et riche en fonctionnalités, directement accessible via une page d'accueil moderne (`index.html`) au design Cyberpunk / Neon.

Tous les jeux sont développés **sans dépendance de build** (pas de Node.js, Webpack ou Vite requis). Il suffit d'ouvrir les fichiers dans n'importe quel navigateur web moderne.

---

## 🕹️ Les Jeux Inclus

```
┌─────────────────────────────────────────────────────────────────┐
│                           GAME CENTER                           │
│                          (index.html)                           │
└────────────────┬───────────────────────────────┬────────────────┘
                 │                               │
                 ▼                               ▼
       💰 THUNE SIMULATOR v3.1          🧟 ZOMBIE SURVIVOR.io v7.0
       • Tycoon / Idle Clicker          • Action Rogue-lite 2D
       • Bourse & Multivers             • Bullet Heaven & Vagues
       • Progression infinie            • Équipements RPG & Boss
```

---

### 1. 💰 Thune Simulator v3.1
**Fichier :** [`g_n_rateur_de_thune_artificielle_securise_corrige.html`](file:///c:/Users/VICTO/.gemini/antigravity/scratch/game-center/g_n_rateur_de_thune_artificielle_securise_corrige.html)  
**Genre :** Idle Tycoon / Simulateur Financier / Clicker incrémental  
**Design System :** *« Aurora Noir »* (glassmorphism sombre, néons émeraudes et or, typographies *Inter* et *JetBrains Mono*).

Devenez le magnat absolu en partant d'un simple clic pour bâtir un empire financier transcendant les dimensions cosmiques !

#### ✨ Fonctionnalités majeures :
- **16+ Commerces automatisables :** Du stand *Kebab 24/7 « Le Roi du Sauce Blanche »* aux agences de terraformation martienne, sphères de Dyson et banques multiverselles.
- **Managers Dédiés :** Recrutez des managers emblématiques (*Chef Momo*, *Elon-X Prime*, *Dr. Singularité*...) pour automatiser chaque flux de revenus.
- **10 Rangs de Maîtrise :** Débloquez des multiplicateurs massifs tous les 50 niveaux (de *Bronze I* à *Transcendant ∞*).
- **24 Infrastructures Financières :** Planches à billets clandestines, serveurs de trading HFT, fermes quantiques générant des revenus passifs continus.
- **Bourse & Marchés Spéculatifs :** Achetez bas, vendez haut sur des actions et cryptos dynamiques.
- **R&D & Expansion Géographique :** Développez des technologies exclusives et étendez votre influence sur plusieurs continents.
- **Prestige Cosmique & Singularity Vault :** Réinitialisez votre trésorerie en échange de particules de singularité et de multiplicateurs permanents.
- **Classement Forbes & Factions :** Grimpez les échelons du classement mondial jusqu'au statut d'entité cosmique.
- **Sauvegarde Automatique :** Sauvegarde persistante en `localStorage` avec modes d'achat rapides (`x1`, `x10`, `x100`, `MAX`).

---

### 2. 🧟 Zombie Survivor.io — Bunker OS v7.0
**Fichier :** [`surivor_games.html`](file:///c:/Users/VICTO/.gemini/antigravity/scratch/game-center/surivor_games.html)  
**Genre :** Action Rogue-lite / Bullet Heaven / Top-Down Shooter 2D  
**Ambiance :** Terminal militaire tactique *Bunker OS* (vert radioactif, UI découpée industrielle, police *Chakra Petch*).

Enfermé dans un bunker en zone de quarantaine, affrontez des hordes de mutants, ramassez des gemmes d'XP, améliorez vos armes à la volée et terrassez des boss titanesques !

#### ✨ Fonctionnalités majeures :
- **Moteur Canvas 2D fluide :** Gestion de centaines d'ennemis simultanés à l'écran, particules, débris et effets de recul.
- **6 Armes Actives :**
  - 🔫 **Pistolet :** Tir direct rapide avec perforation et tirs multiples.
  - 🌀 **Lames orbitales :** Cercle défensif tranchant autour du survivant.
  - 🛸 **Drone de combat :** Soutien aérien automatisé tirant des rafales laser.
  - ⚡ **Chaîne Tesla :** Arcs électriques rebondissant entre les mutants.
  - 🔥 **Cocktail Molotov :** Zones d'incendie persistantes au sol.
  - 💥 **Onde de choc :** Impulsion radiale dévastatrice repoussant la horde.
- **Système d'Équipement RPG sur 6 Emplacements :**
  - Arme, Casque, Armure, Gants, Bottes, Amulette.
  - 5 Raretés : *Commun*, *Rare*, *Épique*, *Légendaire*, *S-GRADE*.
  - Calcul dynamique de votre **Power Score** global.
- **4 Secteurs d'Intervention × 5 Niveaux (20 niveaux au total) :**
  1. *Rues Dévastées* (Boss : **Titan Muté Enragé** — 16k HP)
  2. *Hôpital en Ruines* (Boss : **Le Chirurgien Fou** — 34k HP)
  3. *Métro Infesté* (Boss : **Roi des Rats Corrompu** — 65k HP)
  4. *Zone Zéro* (Boss : **Titan Alpha Cauchemar** — 110k HP)
  - Niveaux 1-4 : objectif secondaire (éliminations, gemmes, combo, élites, etc.) + survie 3 min
  - Niveau 5 : **BOSS DIFFICILE** qui spawn immédiatement et lâche un butin d'XP à ramasser
  - Vitesse (tempo) progressive par niveau : ×0.75 → ×1 → ×1.5 → ×2 → ×2 (boss)
- **Arbre de Talents Permanents :** Dépensez vos pièces d'or récoltées pour booster vos PV, Attaque, Vitesse, Aimant à butin et Coups critiques.
- **Audio Procédural Web Audio API :** Synthétiseur sonore complet en pur code (aucun fichier MP3/WAV externe requis) : tirs, impacts, explosions, montée de niveau et nappe d'ambiance dynamique qui s'intensifie lors des boss.

---

## 📁 Architecture & Fichiers du Projet

```text
game-center/
├── index.html                                            # Hub d'accueil Game Center
├── g_n_rateur_de_thune_artificielle_securise_corrige.html# Jeu 1 : Thune Simulator v3.1
├── surivor_games.html                                    # Jeu 2 : Zombie Survivor.io v7.0
├── README.md                                             # Documentation complète
└── .gitignore                                            # Fichiers exclus du versionnement
```

---

## 🚀 Démarrage Rapide

### Option 1 : Lancement direct en local
Aucun serveur ni installation nécessaire ! Double-cliquez simplement sur :
👉 [**`index.html`**](file:///c:/Users/VICTO/.gemini/antigravity/scratch/game-center/index.html) pour accéder au menu central.

### Option 2 : Serveur local rapide (facultatif)
Pour tester avec un mini-serveur HTTP local (Python, Live Server, etc.) :

```bash
# Avec Python 3
python -m http.server 8080

# Ou avec npx serve
npx serve .
```
Puis ouvrez votre navigateur sur `http://localhost:8080`.

---

## 🎮 Contrôles de Jeu

### Zombie Survivor.io
| Action | Clavier (PC) | Écran Tactile (Mobile/Tablette) |
| :--- | :--- | :--- |
| **Se déplacer** | `Z` `Q` `S` `D` ou `Touches Fléchées` | Joystick virtuel flottant à l'écran |
| **Visée & Tir** | Automatique sur l'ennemi le plus proche | Automatique |
| **Pause / Menu** | `Échap` ou bouton ⏸️ en haut à droite | Bouton ⏸️ |

### Thune Simulator
- **Clic gauche / Tap :** Générer de la thune manuellement sur le bouton central.
- **Boutons de quantité :** Alternez entre `x1`, `x10`, `x100` et `MAX` pour des achats optimisés.

---

## 🛠️ Technologies & Conception

- **100% Client-Side :** Fonctionne entièrement hors-ligne dans le navigateur.
- **Zéro dépendance lourde :** Aucun bundler, pas de `node_modules`.
- **Rendu Canvas haute performance :** Boucle de jeu `requestAnimationFrame`, détection de collisions spatiales optimisée.
- **Génération sonore temps réel :** Oscillateurs, générateurs de bruit blanc et filtres biquad via l'API Web Audio native.
- **Persistance locale :** Sauvegarde transparente de la progression via l'API `localStorage`.

---

## 🎁 Codes Secrets (Zombie Survivor.io)

Les codes d'accès **ne sont pas publics** — ils sont distribués manuellement par l'opérateur du bunker (le créateur du jeu) aux joueurs.

Dans le lobby de **Zombie Survivor.io**, cliquez sur l'icône de terminal pour saisir un code que vous avez reçu. Chaque code débloque :
- Des secteurs d'intervention (accès dérogatoire)
- Du butin (pièces, gemmes, équipement)
- Des ressources d'urgence

Une fois un code utilisé, il est enregistré dans le journal et ne peut plus être réutilisé. Si vous n'avez pas reçu de code, progressez normalement : chaque niveau validé débloque le suivant.

---

*Game Center — Projet open-source créé pour le plaisir du gameplay rétro et addictif.*
