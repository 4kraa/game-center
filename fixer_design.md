# FIXER — Design Document

> **Status** : Phase de conception (v0.1-design)
> **Genre** : Tycoon / Gestion de production
> **Thème** : Concevoir et fabriquer des téléphones portables
> **Format** : Web (HTML/JS natif, 100% offline, localStorage)

---

## 1. Pitch

Tu démarres **pauvre et inconnu** dans un garage, avec un budget minuscule et un marché dominé par les géants (Apple, Samsung, etc.). Ton objectif : **concevoir des téléphones portables pièce par pièce** — écran, processeur, RAM, batterie, caméra, châssis, OS — jusqu'à devenir le leader mondial.

Chaque téléphone est assemblé à partir de composants choisis. Le score global détermine le prix de vente, la demande et la réputation. Plus tu vends, plus tu gagnes, plus tu peux investir dans de meilleurs composants, R&D, marketing et usines.

---

## 2. Boucle de gameplay

```
┌─────────────────────────────────────────────────────────────┐
│  1. CHOISIR UN PROJET (modèle à concevoir)                  │
│     → cible : entrée de gamme, milieu, premium, gaming…    │
├─────────────────────────────────────────────────────────────┤
│  2. SÉLECTIONNER LES COMPOSANTS                              │
│     écran · CPU · RAM · stockage · batterie · caméra ·      │
│     châssis · OS · connectique                              │
├─────────────────────────────────────────────────────────────┤
│  3. ASSEMBLER & VALIDER LE PROTOTYPE                         │
│     → calcul automatique du score qualité + coût de revient │
├─────────────────────────────────────────────────────────────┤
│  4. LANCER LA PRODUCTION                                     │
│     → choisir quantité + prix de vente                       │
├─────────────────────────────────────────────────────────────┤
│  5. VENDRE SUR LE MARCHÉ                                     │
│     → ventes calculées vs demande + prix + réputation        │
├─────────────────────────────────────────────────────────────┤
│  6. RÉINVESTIR                                               │
│     → R&D (nouveaux composants) · usines · marketing ·       │
│       recrutement · brevets                                  │
└─────────────────────────────────────────────────────────────┘
```

---

## 3. Les composants

Chaque téléphone est constitué de **9 slots de composants**. Chaque composant a :

| Attribut | Description |
|---|---|
| `cost` | Coût d'achat unitaire (à l'usine) |
| `tier` | Niveau technologique (1 = bas de gamme, 5 = premium) |
| `perf` | Score de performance (1-100) |
| `power` | Consommation énergétique (plus bas = mieux) |
| `weight` | Poids en grammes |
| `brand` | Marque (générique, ou sous licence R&D) |

### 3.1 Écran (`screen`)
- Taille (5.0" → 7.2"), résolution (HD → 4K), technologie (LCD, OLED, AMOLED, LTPO)
- Taux de rafraîchissement (60/90/120/144 Hz)
- Impact direct sur le score "Affichage" perçu par les clients

### 3.2 Processeur (`cpu`)
- Cœurs (4/6/8/10), fréquence, gravure (14nm → 3nm)
- Marques fictives : "Snapcore A1", "Mediatekk Helio", "Qualcomms Dragon"
- Impact : performance générale + autonomie (gravure plus fine = moins de conso)

### 3.3 RAM (`ram`)
- 2/4/6/8/12/16/24 Go, type (LPDDR4/4X/5/5X)
- Impact : multitâche + gaming

### 3.4 Stockage (`storage`)
- 32/64/128/256/512/1024 Go, type (eMMC, UFS 2.1, UFS 3.1, UFS 4.0)
- Impact : vitesse d'installation + photos/vidéos

### 3.5 Batterie (`battery`)
- Capacité (2000 → 6000 mAh), technologie (Li-Ion, Li-Po, Si-C, Graphène)
- Charge rapide (10W → 240W)
- Charge sans fil (Non/Qi/Reverse)

### 3.6 Caméra (`camera`)
- Nombre de modules (1, 2, 3, 4), mégapixels (12 → 200 MP)
- Capteurs : standard, grand-angle, téléobjectif, macro, ToF
- Stabilisation (EIS, OIS, IBIS)
- Score DXOM-like (qualité photo calculée)

### 3.7 Châssis (`chassis`)
- Matière : plastique, métal, verre, titane, céramique
- Étanchéité : IP53 / IP67 / IP68
- Poids + durabilité perçue

### 3.8 OS (`os`)
- Propriétaire (basique), Android (licence), iOS-like (besoin R&D), Custom (en house)
- Impact : fluidité, mises à jour, écosystème

### 3.9 Connectique (`ports`)
- USB-C 2.0 / 3.0 / 4.0, jack 3.5mm (Y/N), microSD (Y/N), dual-SIM (Y/N), eSIM (Y/N), 5G (Y/N)

---

## 4. Score du téléphone

Le téléphone assemblé produit 4 scores principaux (0-100) :

| Score | Formule (résumé) |
|---|---|
| **PERF** | `moy(cpu.perf × 0.5, ram.perf × 0.3, storage.perf × 0.2)` |
| **DISPLAY** | `screen.perf` (avec bonus taux rafraîchissement + résolution) |
| **CAMERA** | `moy(camera modules + stabilisation + MP)` |
| **BATTERY LIFE** | `battery.mAh / (cpu.power × screen.power × 1.2)` |

Le **score global** est une moyenne pondérée selon la cible :
- Entrée de gamme : BATTERY (40%) + CAMERA (10%) + PERF (30%) + DISPLAY (20%)
- Premium : tous à 25%
- Gaming : PERF (50%) + DISPLAY (30%) + BATTERY (20%)
- Photo : CAMERA (60%) + DISPLAY (20%) + BATTERY (20%)

Le score global détermine :
- le **prix de vente conseillé** (price = score × tier × brand multiplier)
- la **demande** (% de la population intéressée par ce score)

---

## 5. Marché & ventes

### 5.1 Segments de clientèle
| Segment | Budget | Priorité |
|---|---|---|
| Étudiants | 100-300 € | BATTERY + prix bas |
| Grand public | 300-600 € | Bon équilibre |
| Gamers | 500-1000 € | PERF + DISPLAY |
| Photographes | 700-1200 € | CAMERA + DISPLAY |
| Business | 800-1500 € | Autonomie + durabilité |
| Passionnés | 1000-2000 € | Tout au max |

### 5.2 Calcul des ventes (par "mois" de jeu)
```
ventes_potentielles = population_du_segment × taux_d_intérêt(score, prix)
ventes_réelles = ventes_potentielles × (1 + réputation × 0.05) × (1 + marketing × 0.1)
                 × max(0, 1 - (prix / prix_conseillé - 1))   # si prix > conseil, ça chute
                 × (1 - concurrence)                          # marché saturé par les géants
```

### 5.3 Réputation
- Bon rapport qualité/prix → +réputation
- Téléphone avec défaut majeur (batterie trop faible pour un gaming) → -réputation
- Lancer des modèles régulièrement → +réputation (loyauté)

---

## 6. Progression

### Phase 1 — Le garage (tier 1-2 composants)
- Budget : 5000 €
- Composants : génériques bas de gamme
- Objectif : vendre 100 téléphones, atteindre +5k € de réputation
- Débloque : atelier, 1er employé

### Phase 2 — Petit atelier (tier 2-3)
- Budget : 50k €
- Composants : marques sous licence
- Objectif : recruter ingénieur R&D, débloquer OS custom
- Débloque : R&D, marketing basique

### Phase 3 — PME (tier 3-4)
- Budget : 500k €
- Composants : premiums
- Objectif : ouvrir usine, conquérir 10% du marché
- Débloque : usine propre, brevets, marketing TV

### Phase 4 — Multinationale (tier 5)
- Budget : illimité
- Composants : prototypes exclusifs (graphène, 200MP, etc.)
- Objectif : battre Apple/Samsung sur le marché
- Débloque : fusion-acquisition, campus R&D mondial

---

## 7. Système économique

### Coûts par téléphone
- **Coût composants** = somme des `cost` des 9 composants
- **Coût assemblage** = base 5€ (augmente avec complexité)
- **Coût R&D** = amorti sur la série (plus tu produis, moins c'est cher par unité)
- **Coût marketing** = 0 par défaut, jusqu'à 30% du prix de vente

### Revenus
- `revenu = ventes × prix_vente - (ventes × coût_total) - coûts_fixes`

### Coûts fixes (mensuels)
- Loyer atelier (1k€ → 500k€ selon phase)
- Salaires employés (2k€ à 50k€ chacun)
- Licences OS / brevets

---

## 8. UI / UX (à venir)

### Écrans prévus
1. **Atelier** : vue isométrique du téléphone en cours d'assemblage + 9 slots composants cliquables
2. **Marché** : segments clients, courbes de demande, concurrents
3. **R&D** : arbre de technologies (CPU, écran, batterie, OS, caméra)
4. **Usine** : lignes de production, capacité, stocks
5. **Bilan** : finances, réputation, parts de marché
6. **Bureau** : employés, contrats spéciaux (clients VIP)

### Style visuel
- Theme : "Tech Lab" — fond sombre #0a0d12, accents cyan/violet
- Police : Chakra Petch (titres) + Barlow (corps) + JetBrains Mono (datas)
- Vue isométrique du téléphone en cours d'assemblage (SVG/CSS)
- Animations : composants qui se clipsent au téléphone, ventes en temps réel

---

## 9. Étapes de développement

| Étape | Statut | Description |
|---|---|---|
| 1. Concept | ✅ Terminé | Ce document |
| 2. Prototype UI atelier | ⏳ À faire | Sélection composants + score temps réel |
| 3. Marché & ventes | ⏳ À faire | Boucle économique de base |
| 4. R&D | ⏳ À faire | Arbre de technologies |
| 5. Progression phases | ⏳ À faire | Garage → multinationale |
| 6. Polish UI/UX | ⏳ À faire | Animations, son, balance |

---

## 10. Décisions finales (validées avec l'opérateur)

- [x] **Rythme** : **Tour-par-tour** — le joueur clique sur "Mois suivant" pour avancer
- [x] **Profondeur** : **12 composants** (ajout de refroidissement, biométrie, audio, réseau aux 9 initiaux)
- [x] **Mode sandbox** : prévu mais **pas au lancement** (mode carrière uniquement pour la beta)
- [x] **Style graphique** : **Mélange flat + isométrique** (téléphone en iso SVG, UI autour en flat)

---

## 11. Composants étendus (12 slots)

| # | Slot | Rôle | Tiers 1 → 5 |
|---|---|---|---|
| 1 | Écran (screen) | Affichage | LCD 5" → LTPO 6.7" 144Hz |
| 2 | Processeur (cpu) | Performance | 4-core 14nm → 10-core 3nm |
| 3 | RAM (ram) | Multitâche | 2Go LPDDR4 → 24Go LPDDR5X |
| 4 | Stockage (storage) | Capacité | 32Go eMMC → 1To UFS 4.0 |
| 5 | Batterie (battery) | Autonomie | 2000mAh Li-Ion → 6000mAh Si-C |
| 6 | Caméra arrière (camrear) | Photos | 8MP → 200MP + 4 modules |
| 7 | Caméra avant (camfront) | Selfies | 5MP → 32MP 4K |
| 8 | Châssis (chassis) | Construction | Plastique → Titane IP68 |
| 9 | OS | Logiciel | Propriétaire → Custom premium |
| 10 | Connectique (ports) | USB-C/jack/microSD | USB 2.0 → USB 4 + eSIM |
| 11 | Réseau (network) | 4G/5G/WiFi | 4G → WiFi 7 + 5G mmWave |
| 12 | Refroidissement (cooling) | Gaming/sustained perf | Passif → Vapor chamber |

*Bonus à venir en v0.3+ : biométrie (empreinte/face ID), audio (DAC/haut-parleurs), NFC, capteurs AR.*
