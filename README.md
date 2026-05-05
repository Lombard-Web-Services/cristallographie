# Cristallographie — Datavis & Storytelling

> **Application de la détermination des principes à la détermination des espèces minérales**  
> *Inspiré de l'ouvrage de René Just Haüy (1822)* — "Application de la détermination des principes à la détermination des espèces minérales"

---

## À propos

Ce projet est une **exploration interactive et visuelle** de la cristallographie historique, centrée sur la théorie des décroissements développée par **René Just Haüy** dans son traité de 1822. À travers des visualisations WebGL, des animations paramétriques et une narration structurée, nous rendons accessibles des concepts cristallographiques fondamentaux qui ont jeté les bases de la minéralogie moderne.

Le projet se concentre notamment sur le **fer sulfuré** (pyrite, marcasite et variétés) comme fil rouge pédagogique — un minéral emblématique dont les multiples formes cristallines illustrent parfaitement la théorie des décroissements.

---

## La théorie des décroissements

### Contexte historique

La théorie des décroissements en minéralogie est une ancienne théorie de cristallographie, principalement développée au XVIIIᵉ siècle par le naturaliste français **René Just Haüy** (1743–1822), considéré comme le père de la cristallographie moderne.

### Idée centrale

Elle cherche à expliquer la forme des cristaux à partir d'un principe simple :

> **Un cristal se construit comme un empilement régulier de petites unités identiques** (appelées à l'époque *molécules intégrantes*), et ses faces se forment par retraits successifs de couches.

Ces retraits progressifs sont appelés des **"décroissements"**.

### Ce que signifie "décroissement"

Un décroissement correspond à une diminution régulière d'une couche de matière sur une face du cristal, un peu comme si on "rabotait" des marches sur les arêtes.

Selon Haüy :

- Les cristaux ne sont pas des formes arbitraires.
- Ils dérivent tous d'une **forme primitive géométrique** (cube, prisme, etc.).
- Les différentes faces apparaissent par **soustraction régulière** de rangées de briques microscopiques.

### Types de décroissements

On distingue notamment :

| Type | Description | Résultat |
|------|-------------|----------|
| **Décroissement simple** | Retrait régulier dans une seule direction | Formes simples (octaèdre) |
| **Décroissement multiple** | Retraits combinés dans plusieurs directions | Formes complexes (trapézoèdre, dodécaèdre) |

Ces mécanismes permettent d'expliquer pourquoi certains cristaux présentent des faces inclinées ou des formes polyédriques variées.

### Importance historique

Cette théorie est aujourd'hui remplacée par la cristallographie moderne (réseaux cristallins, indices de Miller, diffraction des rayons X), mais elle a été essentielle car elle a introduit une idée clé :

> **La forme externe d'un cristal reflète une organisation interne régulière.**

### En résumé

La théorie des décroissements explique les formes cristallines comme le résultat de retraits géométriques réguliers dans une structure fondamentale, ce qui a été une étape majeure vers la compréhension moderne des cristaux.

---

## Les formules du traité (vérifiées)

Les visualisations interactives de ce repos reposent sur les formules exactes extraites du traité de Haüy (pages 5–8, figures 6 et 7) :

### Rapports fondamentaux

```
g' : p' = (n+1)√2 : √(2n²+1)
bp : Op = (n+1) : n
```

### Incidences angulaires

```
Incidence u|u  = 90° + arcsin((4n+1)/(4n²+2))
Incidence u|u' = 2·arctan(√(4n²+1))
```

Où **n** est le paramètre de la loi de décroissement :

- **n = 0.5** → Octaèdre régulier (dégénérescence, faces coplanaires)
- **n = 1** → Trapézoèdre à 24 faces (cas du fer sulfuré trapézoïdal)
- **n > 1** → Formes intermédiaires de plus en plus cubiques

### Valeurs de référence

| n | g' : p' | bp : Op | u\|u | u\|u' | Forme |
|---|---------|---------|------|------|-------|
| 0.5 | √3 : 1 ≈ 1.732 | 3 : 1 | 180° | 109.47° | Octaèdre régulier |
| 1.0 | √8 : √3 ≈ 1.633 | 2 : 1 | 146°26'33" | 131°48'36" | Trapézoèdre 24 faces |
| 2.0 | 3√2 : 3 ≈ 1.414 | 1.5 : 1 | 120° | 152.73° | Forme intermédiaire |

---

## Visualisations interactives

### 1. Décroissement paramétrique (WebGL)

Visualisation 3D temps réel d'un trapézoèdre cubique avec shaders personnalisés, éclairage Phong et navigation interactive.

🔗 [https://lombard-web-services.github.io/cristallographie/De_la_decroissance.html](https://lombard-web-services.github.io/cristallographie/De_la_decroissance.html)

**Fonctionnalités :**
- Slider paramétrique **n** (0.5 à 3)
- Rotation 3D (clic-glisser / tactile)
- Zoom molette
- Auto-rotation
- Affichage des valeurs calculées en temps réel
- Arêtes en fil de fer

### 2. Narration structurée

Parcours guidé à travers la théorie des décroissements, avec explications textuelles synchronisées aux visualisations.

🔗 [https://lombard-web-services.github.io/cristallographie/index.html](https://lombard-web-services.github.io/cristallographie/index.html)

### 3. Formes dérivées du cube

Focus sur les transformations géométriques du cube vers le trapézoèdre et l'octaèdre, avec calculs des rapports et incidences.

🔗 [https://github.com/Lombard-Web-Services/cristallographie/blob/main/Decroissement_sur_le_cube.html](Décroissement sur le cube)

---

## Le fer sulfuré comme cas d'étude

Le **fer sulfuré** (principalement la pyrite FeS₂) est un excellent exemple pour illustrer la théorie des décroissements, car il présente plusieurs formes cristallines distinctes :

- **Pyrite cubique** : forme primitive (cube)
- **Pyrite pentagonododécaédrique** : décroissements combinés
- **Fer sulfuré trapézoïdal** : variété avec trapézoèdre à 24 faces (n=1)
- **Marcasite** : forme orthorhombique (décroissements sur prisme)

Ces variétés, décrites par Haüy dans son traité, démontrent comment un même composé chimique peut adopter des morphologies cristallines différentes selon les conditions de cristallisation — toutes explicables par la théorie des décroissements.

---

## Stack technique

| Technologie | Usage |
|-------------|-------|
| **WebGL** (natif) | Rendu 3D temps réel sans dépendances |
| **GLSL Shaders** | Éclairage Phong, fresnel, brouillard |
| **JavaScript vanilla** | Logique paramétrique et interactions |
| **HTML5 / CSS3** | Interface responsive et storytelling |
| **GitHub Pages** | Hébergement statique |

---

## Méthodologie

Ce projet combine :

1. **Analyse historique** : lecture critique du traité de Haüy (1822)
2. **Vérification mathématique** : reconstruction et validation des formules du texte
3. **Modélisation géométrique** : construction algorithmique des polyèdres
4. **Data visualization** : représentation interactive des paramètres
5. **Storytelling numérique** : narration structurée pour le grand public

---

## Crédits & Références

- **René Just Haüy** — *Traité de minéralogie* (1822), tome I, pages 5–8, figures 6 et 7
- **Readme généré avec Kimi** (Moonshot AI)
- Projet développé par **Lombard Web Services**

---

## Licence

Ce projet est open source. Les ressources historiques (traité de Haüy) sont dans le domaine public.

---

<p align="center">
  <em>"La nature ne fait rien en vain, et le moins qu'elle peut."</em><br>
  <strong>— René Just Haüy</strong>
</p>
