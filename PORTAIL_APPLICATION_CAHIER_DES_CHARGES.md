---
type: cahier des charges
projet: PORTAIL_APPLICATIONS
created: 2025-05-09
author: BERGE_ALEXANDRE
updated: 
version: 2
---
**CAHIER DES CHARGES**

**Projet : Portail des Applications DRSM Île-de-France**

**(DRSM-IDF-PORTAIL-CDC-V2.0)**
**

---

**Historique des Versions**

| Version | Date           | Auteur(s)                                         | Modifications Principales                                                                                                               | Statut       |
| :------ | :------------- | :------------------------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------- | :----------- |
| 1.0     | 09/05/2025     | Équipe de développement (interne/externe)         | Version initiale basée sur le README.md du projet.                                                                                      | Archivé      |
| 1.1     | 19/05/2025     | Équipe de développement (interne/externe)         | Alignement avec l'état final du développement collaboratif.                                                                             | Archivé      |
| **2.0** | **JJ/MM/AAAA** | **[Votre Nom/Service] + Chef de Projet DRSM IDF** | **Consolidation, structuration professionnelle, ajout des exigences non-fonctionnelles, gestion de projet, et critères d'acceptation.** | **En Revue** |

---

**TABLE DES MATIÈRES**

1.  INTRODUCTION
    1.1. Objet du Document
    1.2. Contexte et Justification du Projet
    1.3. Objectifs du Projet
    1.4. Périmètre du Projet
    1.5. Public Cible
    1.6. Définitions et Glossaire
    1.7. Documents de Référence
2.  EXIGENCES FONCTIONNELLES
    2.1. Vision d'Ensemble de la Solution
    2.2. Structure Générale de l'Interface Utilisateur (UI)
    2.3. Gestion de l'Affichage des Applications
    2.4. Fonctionnalité de Recherche
    2.5. Fonctionnalités de Filtrage ("Affectation")
    2.6. Gestion des Données des Applications
    2.7. Navigation et Interactivité
3.  EXIGENCES NON-FONCTIONNELLES
    3.1. Performance
    3.2. Sécurité
    3.3. Utilisabilité et Ergonomie (UX)
    3.4. Accessibilité (A11Y)
    3.5. Maintenabilité et Évolutivité
    3.6. Compatibilité
    3.7. Disponibilité et Fiabilité
    3.8. Conformité Légale et Réglementaire
4.  ARCHITECTURE ET SPÉCIFICATIONS TECHNIQUES
    4.1. Architecture Applicative
    4.2. Technologies Imposées et Recommandées
    4.3. Structure et Gestion des Données
    4.4. Environnement Technique (Déploiement, Hébergement)
5.  GESTION DE PROJET
    5.1. Acteurs et Rôles
    5.2. Phasage et Planning Prévisionnel (si applicable pour cette version)
    5.3. Livrables Attendus
    5.4. Critères d'Acceptation
    5.5. Modalités de Suivi et de Reporting
    5.6. Gestion des Risques (Identifiés à ce stade)
6.  EXPLOITATION, MAINTENANCE ET SUPPORT
    6.1. Procédures de Mise à Jour du Contenu
    6.2. Support Utilisateur
    6.3. Monitoring et Supervision (si applicable)
    6.4. Sauvegarde et Restauration
7.  ÉVOLUTIONS FUTURES ENVISAGÉES
8.  ANNEXES (Optionnel)

---

## 1. INTRODUCTION

### 1.1. Objet du Document

Le présent Cahier des Charges (CdC) définit les besoins, les objectifs, les exigences fonctionnelles et non-fonctionnelles, ainsi que les contraintes techniques et organisationnelles pour la conception, le développement, et la mise en service du "Portail des Applications DRSM Île-de-France" (ci-après dénommé "le Portail"). Ce document sert de référence contractuelle entre la maîtrise d'ouvrage (MOA) représentée par la DRSM Île-de-France et la maîtrise d'œuvre (MOE) chargée de la réalisation. Il se fonde sur la version 1.1, correspondant à l'état final du développement collaboratif initial, et vise à le consolider pour une adoption institutionnelle.

### 1.2. Contexte et Justification du Projet

La Direction Régionale du Service Médical (DRSM) d'Île-de-France, dans le cadre de ses missions, s'appuie sur un nombre significatif et croissant d'applications informatiques, qu'elles soient nationales ou locales. Actuellement, l'accès à ces outils est dispersé, ce qui peut entraîner une perte de temps, une complexité pour les nouveaux arrivants, et une potentielle baisse d'efficacité.
La création d'un portail centralisé est donc identifiée comme une solution stratégique pour simplifier l'accès à ces ressources, améliorer la productivité des collaborateurs et harmoniser les pratiques.

### 1.3. Objectifs du Projet

Le Portail vise à atteindre les objectifs suivants :
*   **O1. Centralisation :** Fournir un point d'accès unique, organisé et exhaustif à l'ensemble des applications référencées et utilisées par la DRSM Île-de-France.
*   **O2. Simplicité et Rapidité d'Accès :** Permettre aux utilisateurs d'identifier et de lancer rapidement les applications nécessaires à leurs activités quotidiennes.
*   **O3. Efficacité Opérationnelle :** Réduire le temps de recherche des outils et fluidifier la navigation, contribuant ainsi à l'optimisation des processus métier.
*   **O4. Expérience Utilisateur Optimisée :** Offrir une interface intuitive, moderne, et adaptée à une utilisation sur divers types de terminaux (responsive design).
*   **O5. Clarté de l'Information :** Distinguer clairement les applications locales (spécifiques à l'Île-de-France) des applications nationales.
*   **O6. Autonomie des Utilisateurs :** Faciliter la découverte d'outils pertinents pour les missions des collaborateurs.

### 1.4. Périmètre du Projet

**Inclus dans le périmètre :**
*   La conception et le développement de l'interface utilisateur du Portail.
*   L'intégration de la liste des applications (environ 140 initialement) avec leurs métadonnées (nom, URL, service, catégorie, icône, portée).
*   Les fonctionnalités de recherche textuelle sur les noms d'applications.
*   Les fonctionnalités de filtrage par service, catégorie et échelon.
*   La distinction visuelle des applications locales et nationales.
*   Le design responsive assurant une consultation sur ordinateurs de bureau, tablettes et smartphones.
*   La documentation utilisateur de base et la documentation technique pour la maintenance.
*   La livraison du code source finalisé (fichier HTML unique avec CSS et JavaScript intégrés).

**Exclus du périmètre (pour cette version) :**
*   Système d'authentification des utilisateurs.
*   Personnalisation de l'affichage par profil utilisateur (favoris, historique).
*   Interface d'administration dédiée pour la gestion des applications (les mises à jour se font par modification du code source).
*   Fonctionnalités collaboratives (notation, commentaires sur les applications).
*   Intégration avec d'autres systèmes d'information (annuaires, SSO) au-delà des liens URL.
*   Statistiques d'utilisation détaillées.

### 1.5. Public Cible

Le Portail est destiné à l'ensemble des collaborateurs de la DRSM Île-de-France, quel que soit leur service, leur fonction ou leur niveau d'aisance avec les outils informatiques. Cela inclut :
*   Personnel administratif et technique.
*   Praticiens-conseils et personnel médical.
*   Managers et responsables de service.
*   Nouveaux arrivants.

### 1.6. Définitions et Glossaire

| Terme       | Définition                                                                                                |
| :---------- | :-------------------------------------------------------------------------------------------------------- |
| **DRSM IDF**| Direction Régionale du Service Médical d'Île-de-France.                                                     |
| **Portail** | L'application web "Portail des Applications DRSM IDF" objet de ce CdC.                                    |
| **Application** | Outil informatique, site web ou service en ligne référencé dans le Portail.                             |
| **Carte d'Application** | Élément graphique cliquable représentant une application dans la grille du Portail.               |
| **Service ER**| Service de l'Entité Régionale (ex: SI, CCX, COM). Utilisé comme critère de filtrage.                    |
| **Échelon**   | Unité géographique ou administrative locale (ex: ELSM 75). Utilisé comme critère de filtrage.             |
| **Catégorie** | Classification fonctionnelle d'une application (ex: Documentation, Pilotage). Utilisé comme critère de filtrage. |
| **Portée**    | Indique si une application est locale (Île-de-France) ou nationale.                                       |
| **SPA**       | Single Page Application. Application web qui charge une seule page HTML et met à jour dynamiquement son contenu. |
| **UI**        | User Interface (Interface Utilisateur).                                                                   |
| **UX**        | User Experience (Expérience Utilisateur).                                                                 |
| **A11Y**      | Accessibility (Accessibilité web).                                                                        |
| **CDN**       | Content Delivery Network. Réseau de serveurs pour distribuer du contenu statique (ex: Tailwind, Font Awesome). |
| **MOA**       | Maîtrise d'Ouvrage (Commanditaire du projet).                                                             |
| **MOE**       | Maîtrise d'Œuvre (Réalisateur du projet).                                                                 |

### 1.7. Documents de Référence

| Réf.    | Titre du Document                                                   | Version  | Date       |
| :------ | :------------------------------------------------------------------ | :------- | :--------- |
| [DR-01] | Cahier des Charges – Portail des Applications DRSM IDF              | 1.1      | 19/05/2025 |
| [DR-02] | README.md - Portail des Applications DRSM Île-de-France             | 1.0      | 09/05/2025 |


## 2. EXIGENCES FONCTIONNELLES

### 2.1. Vision d'Ensemble de la Solution

Le Portail est une application web de type SPA, accessible via un navigateur web standard. Il présente une liste d'applications sous forme de cartes interactives, organisées dans une grille. L'utilisateur peut affiner cette liste grâce à des fonctionnalités de recherche textuelle et de filtrage multicritères.

### 2.2. Structure Générale de l'Interface Utilisateur (UI)

**EF-UI-001 : En-tête Supérieur**
Le Portail doit afficher un bandeau supérieur fin, de couleur blanche (#FFFFFF).
Ce bandeau doit contenir le logo officiel de l'Assurance Maladie (partie "Sécurité Sociale") aligné à gauche, avec une hauteur de 32px (h-8) sur mobile et 36px (h-9) sur les écrans plus larges. Le logo utilisé est `https://placehold.co/180x40/1E293B/FFFFFF?text=Logo+Assurance+Maladie` ou l'image officielle si fournie.

**EF-UI-002 : En-tête Principal**
Sous l'en-tête supérieur, le Portail doit afficher un en-tête principal avec un fond de couleur bleue institutionnelle (bg-blue-700).
Cet en-tête doit afficher le titre "Portail des applications DRSM IDF" centré, en texte blanc, avec une taille de police adaptée (text-2xl à text-4xl) et en gras.

**EF-UI-003 : Zone de Contenu Principale**
La zone de contenu doit être située sous l'en-tête principal.
*   **EF-UI-003.1 (Desktop/Tablette) :** Sur les écrans de taille moyenne et supérieure (breakpoint `md` de Tailwind, 768px et plus), cette zone doit être divisée en deux colonnes verticales :
    *   Colonne de Gauche ("Affectation") : Largeur fixe (25% de la largeur du conteneur, min 280px, max 350px), dédiée aux filtres.
    *   Colonne de Droite (Applications) : Occupe l'espace restant, dédiée à la barre de recherche et à la grille des applications.
*   **EF-UI-003.2 (Mobile) :** Sur les écrans de petite taille (inférieur à `md`), la colonne de gauche doit s'afficher au-dessus de la colonne de droite.

**EF-UI-004 : Pied de Page**
Le Portail doit afficher un pied de page fin, avec un fond de couleur gris foncé/bleu sobre (bg-slate-700).
Le pied de page doit afficher le texte "© [Année en cours] DRSM IDF - Tous droits réservés." centré, en texte de couleur claire (text-slate-300) et de petite taille (text-xs). L'année doit être mise à jour dynamiquement.

### 2.3. Gestion de l'Affichage des Applications

**EF-APP-001 : Grille d'Applications**
Les applications (résultant des filtres et/ou de la recherche) doivent être affichées sous forme de cartes dans une grille.
La grille doit être responsive :
*   1 colonne sur écrans `xs` (extra-small).
*   2 colonnes à partir de `sm` (small).
*   3 colonnes à partir de `md` (medium).
*   4 colonnes à partir de `lg` (large).
*   5 colonnes à partir de `xl` (extra-large).
*   6 colonnes à partir de `2xl` (2x extra-large).

**EF-APP-002 : Carte d'Application - Contenu**
Chaque carte d'application doit afficher les informations suivantes :
*   Nom de l'application (lisible, centré).
*   Service associé (sous le nom, plus petit).
*   Catégorie de l'application (sous le service, encore plus petit).
*   Icône principale représentative de l'application (issue de Font Awesome), affichée dans un cercle au-dessus du nom.

**EF-APP-003 : Carte d'Application - Indicateur de Portée**
Chaque carte doit afficher un indicateur visuel de la portée de l'application :
*   **Portée Locale (Île-de-France) :**
    *   Le cercle de fond de l'icône principale doit être de couleur verte (bg-green-100).
    *   L'icône principale doit être de couleur verte (text-green-700).
    *   Une petite icône "punaise" (`fas fa-map-pin`) de couleur verte (text-green-600) doit être affichée en haut à droite de la carte.
*   **Portée Nationale :**
    *   Le cercle de fond de l'icône principale doit être de couleur bleue (bg-blue-100).
    *   L'icône principale doit être de couleur bleue (text-blue-600, ou selon `app.iconColor`).
    *   Une petite icône "drapeau" (`fas fa-flag`) de couleur bleue (text-blue-600) doit être affichée en haut à droite de la carte.

**EF-APP-004 : Carte d'Application - Interactivité**
Un clic sur une carte d'application doit ouvrir l'URL associée à cette application dans un nouvel onglet du navigateur (`target="_blank" rel="noopener noreferrer"`).
Si l'URL d'une application commence par `#`, la carte ne doit pas être cliquable, le curseur doit être de type "non autorisé" (`cursor-not-allowed`), et la carte doit avoir une opacité réduite (opacity-70) pour indiquer son inactivité.
Les cartes doivent avoir un effet visuel au survol (légère élévation `translateY(-5px)` et ombre portée accrue `box-shadow`).

**EF-APP-005 : Tri des Applications**
Les applications affichées dans la grille doivent être triées par ordre alphabétique croissant de leur nom.

**EF-APP-006 : Absence de Résultats**
Si la combinaison des filtres et/ou de la recherche ne retourne aucune application, un message clair doit être affiché dans la zone de la grille : "Aucune application ne correspond à ces filtres." (col-span-full, text-center, py-12, text-lg).

### 2.4. Fonctionnalité de Recherche

**EF-SEARCH-001 : Barre de Recherche**
Une barre de recherche textuelle (`<input type="search">`) doit être positionnée en haut de la colonne de droite (section des applications).
Elle doit comporter un placeholder invitant à la saisie : "Rechercher une application...".

**EF-SEARCH-002 : Comportement de la Recherche**
La recherche doit s'effectuer dynamiquement sur le nom des applications (filtrage en temps réel à chaque caractère tapé ou supprimé).
La recherche doit être insensible à la casse.
La recherche doit s'appliquer aux résultats déjà potentiellement filtrés par les filtres d'affectation.

**EF-SEARCH-003 : Positionnement "Sticky"**
Sur les écrans de taille `md` et plus, la barre de recherche doit être "collante" (sticky) en haut de la colonne des applications, restant visible lors du défilement de la grille des applications. Sur les écrans plus petits, elle n'est pas sticky.

### 2.5. Fonctionnalités de Filtrage ("Affectation")

**EF-FILTER-001 : Colonne des Filtres**
La colonne de gauche, intitulée "Affectation" (text-xl, font-bold, mb-5, border-b), doit contenir les mécanismes de filtrage.
Elle doit être scrollable indépendamment de la grille des applications sur les écrans `md` et plus si son contenu dépasse la hauteur visible.

**EF-FILTER-002 : Structure en Accordéons**
Les filtres doivent être regroupés par type (Services ER, Échelons, Catégories), chaque type étant présenté dans un accordéon repliable.
Chaque accordéon doit afficher un titre (nom du type de filtre) et une icône chevron (`fas fa-chevron-down`) indiquant son état (ouvert/fermé).
Par défaut, tous les accordéons doivent être repliés au chargement de la page.
Un clic sur l'en-tête d'un accordéon doit le déployer (afficher les options de filtre) ou le replier (masquer les options). L'icône chevron doit pivoter en conséquence.

**EF-FILTER-003 : Filtre "Services ER"**
Cet accordéon doit permettre de filtrer les applications par le service auquel elles sont rattachées.
La liste des options de service doit être générée dynamiquement à partir des valeurs uniques du champ `service` des applications (excluant les valeurs vides ou "À définir" sauf si explicitement inclus).
Une option "Tous" doit être présente en début de liste pour désactiver le filtre sur ce critère et afficher toutes les applications (selon les autres filtres).
Une option "À définir" doit être présente en fin de liste si des applications ont cette valeur pour le service.

**EF-FILTER-004 : Filtre "Échelons"**
Cet accordéon doit permettre de filtrer les applications par échelon géographique local.
La liste des options est prédéfinie et doit inclure : "Tous les échelons", "ELSM 75", "ELSM 77", "ELSM 78", "ELSM 91", "ELSM 92", "ELSM 93", "ELSM 94", "ELSM 95".
L'option "Tous les échelons" désactive le filtre sur ce critère.

**EF-FILTER-005 : Filtre "Catégories"**
Cet accordéon doit permettre de filtrer les applications par leur catégorie fonctionnelle.
La liste des options de catégorie doit être générée dynamiquement à partir des valeurs uniques du champ `category` des applications (excluant les valeurs vides ou "À définir" sauf si explicitement inclus).
Une option "Toutes" doit être présente en début de liste pour désactiver le filtre sur ce critère.
Une option "À définir" doit être présente en fin de liste si des applications ont cette valeur pour la catégorie.

**EF-FILTER-006 : Logique de Filtrage Exclusive et Combinée**
*   **Exclusivité d'axe principal :** La sélection d'une valeur spécifique (autre que "Tous", "Toutes", "Tous les échelons") dans l'un des trois filtres (Services ER, Échelons, ou Catégories) active ce filtre comme filtre principal. Les deux autres types de filtres doivent alors être automatiquement réinitialisés à leur valeur par défaut ("Tous", "Tous les échelons", "Toutes") et leurs options visuellement désactivées ou mises en évidence comme non prioritaires.
*   **Interaction Spécifique Services ER et Catégories Globales :** Si le filtre "Services ER" est l'axe principal actif (une valeur spécifique est sélectionnée) :
    *   Les applications correspondant directement au service sélectionné sont affichées.
    *   EN PLUS, les applications appartenant à des catégories définies comme "globales" (codées en dur : `["Ressources Humaines", "Communication"]`) sont également affichées, même si leur champ `service` ne correspond pas au service sélectionné.
    *   Cette règle d'inclusion des catégories globales ne s'applique PAS si un filtre de "Catégories" ou d'"Échelons" est l'axe principal actif.
*   Les boutons de filtre actifs doivent avoir un style distinct (ex: `bg-blue-100`, `text-blue-600`, `font-semibold`).

**EF-FILTER-007 : Application des Filtres**
Toute modification d'un filtre doit entraîner la mise à jour immédiate de la grille des applications.

### 2.6. Gestion des Données des Applications

**EF-DATA-001 : Source des Données**
Les informations relatives à chaque application doivent être stockées dans un tableau JavaScript nommé `applications`, directement intégré dans le code source du fichier HTML.

**EF-DATA-002 : Structure d'un Objet Application**
Chaque élément du tableau `applications` doit être un objet JavaScript avec les propriétés suivantes :
*   `id` (Number) : Identifiant numérique unique pour l'application.
*   `name` (String) : Nom de l'application (nettoyé et formaté pour l'affichage).
*   `url` (String) : URL d'accès à l'application. Une URL commençant par `#` indique un placeholder non cliquable.
*   `service` (String) : Service principal auquel l'application est rattachée (ex: "SI", "COM", "À définir").
*   `category` (String) : Catégorie fonctionnelle (ex: "Documentation", "Métier", "À définir").
*   `echelon` (String) : Échelon géographique pertinent (ex: "ELSM 75", "À définir").
*   `icon` (String) : Classe Font Awesome pour l'icône principale (ex: "fa-cogs").
*   `iconColor` (String) : Classe Tailwind CSS pour la couleur de l'icône principale (ex: "text-blue-600"). Peut être omis si la couleur est déterminée par la portée.
*   `scope` (String) : Portée de l'application. Valeurs possibles : `'local'`, `'national'`.

**EF-DATA-003 : Qualité des Données Initiales**
La liste initiale fournie (environ 140 applications) doit être intégrée. Les noms, URLs, services, catégories, et la portée doivent être vérifiés et normalisés pour assurer la cohérence et la pertinence. La valeur "À définir" est utilisée par défaut lorsque l'information n'est pas disponible.

### 2.7. Navigation et Interactivité

**EF-NAV-001 : Navigation Monopage**
Le Portail doit fonctionner comme une application monopage. Toutes les interactions (recherche, filtrage) doivent mettre à jour dynamiquement le contenu de la page sans rechargement complet.

**EF-NAV-002 : Liens Externes**
Tous les liens vers les applications externes doivent s'ouvrir dans un nouvel onglet du navigateur.

## 3. EXIGENCES NON-FONCTIONNELLES

### 3.1. Performance

**ENF-PERF-001 : Temps de Chargement Initial**
Le temps de chargement initial complet du Portail (HTML, CSS, JS, icônes, données des applications) doit être inférieur à 3 secondes sur une connexion ADSL standard (ex: 8 Mbps).
**ENF-PERF-002 : Réactivité de l'Interface**
Les opérations de recherche et de filtrage doivent s'exécuter et afficher les résultats en moins de 500 millisecondes après l'action de l'utilisateur.

### 3.2. Sécurité

**ENF-SEC-001 : Accès Public**
Le Portail est destiné à un usage interne mais accessible publiquement via son URL. Il ne doit contenir aucune information sensible ou confidentielle non destinée à une diffusion publique.
**ENF-SEC-002 : Protection contre les Failles Courantes (OWASP)**
Bien que simple, le code JavaScript doit éviter les vulnérabilités de type XSS (Cross-Site Scripting), notamment lors de l'injection de données dans le DOM (même si les données proviennent d'une source interne). Les URLs des applications doivent être traitées comme des données potentiellement non sûres si elles étaient dynamiques (ici, elles sont statiques).
**ENF-SEC-003 : Utilisation de HTTPS**
Si hébergé, le Portail doit être servi exclusivement via HTTPS pour garantir la confidentialité et l'intégrité des données en transit (même si minimes).
**ENF-SEC-004 : Dépendances Externes**
Les dépendances externes (Tailwind CSS, Font Awesome via CDN) doivent provenir de sources fiables et maintenues. L'utilisation de SRI (Subresource Integrity) est recommandée si les CDN le supportent.

### 3.3. Utilisabilité et Ergonomie (UX)

**ENF-UX-001 : Intuitivité**
L'interface doit être intuitive et facile à comprendre, même pour des utilisateurs peu familiarisés avec les outils numériques. Les actions principales (rechercher, filtrer, cliquer) doivent être évidentes.
**ENF-UX-002 : Cohérence Visuelle**
Le design doit être cohérent sur l'ensemble du Portail (couleurs, typographies, espacements, style des icônes et des boutons).
**ENF-UX-003 : Feedback Utilisateur**
Des retours visuels clairs doivent être fournis pour les actions utilisateur (ex: état actif des filtres, effet de survol des cartes).
**ENF-UX-004 : Lisibilité**
Les polices de caractères, les tailles et les contrastes de couleurs doivent garantir une excellente lisibilité. Se référer aux recommandations du RGAA (cf. ENF-A11Y-001).

### 3.4. Accessibilité (A11Y)

**ENF-A11Y-001 : Conformité RGAA**
Le Portail doit viser une conformité au niveau AA du Référentiel Général d'Accessibilité pour les Administrations (RGAA) version en vigueur.
Ceci inclut notamment :
*   Navigation au clavier complète et logique.
*   Alternatives textuelles pour les images et icônes porteuses d'information (attributs `alt`, `aria-label`).
*   Utilisation correcte des balises sémantiques HTML5 ( `<nav>`, `<main>`, `<aside>`, `<header>`, `<footer>`, `<button>`, `<a>`).
*   Contrastes de couleurs suffisants.
*   Étiquettes claires pour les champs de formulaire (barre de recherche).
*   Gestion correcte du focus visible.
*   Utilisation des attributs ARIA si nécessaire pour les composants dynamiques (accordéons `aria-expanded`, `aria-controls`).

### 3.5. Maintenabilité et Évolutivité

**ENF-MAIN-001 : Clarté du Code**
Le code source (HTML, CSS, JavaScript) doit être propre, bien structuré, commenté aux endroits stratégiques, et facile à comprendre pour faciliter la maintenance et les évolutions futures.
**ENF-MAIN-002 : Facilité de Mise à Jour des Données**
La structure des données des applications dans le tableau JavaScript doit être simple et permettre l'ajout, la modification ou la suppression aisée d'applications par un intervenant technique ayant des connaissances de base en JavaScript.
**ENF-MAIN-003 : Modularité (JavaScript)**
Le code JavaScript, bien que dans un seul fichier, doit être organisé en fonctions logiques et modulaires pour une meilleure lisibilité et maintenabilité.

### 3.6. Compatibilité

**ENF-COMPAT-001 : Navigateurs Supportés**
Le Portail doit être compatible et fonctionner de manière optimale sur les deux dernières versions majeures des navigateurs suivants :
*   Google Chrome
*   Mozilla Firefox
*   Microsoft Edge
*   Safari
**ENF-COMPAT-002 : Systèmes d'Exploitation**
Le Portail doit fonctionner correctement sur les systèmes d'exploitation courants supportant les navigateurs listés ci-dessus (Windows, macOS, Linux, Android, iOS).
**ENF-COMPAT-003 : Responsive Design**
Le design doit s'adapter fluidement à différentes résolutions d'écran, depuis les smartphones (largeur minimale de 320px) jusqu'aux écrans de bureau larges (1920px et plus).

### 3.7. Disponibilité et Fiabilité

**ENF-DISPO-001 : Taux de Disponibilité**
Le Portail doit viser un taux de disponibilité de 99.9% (lié à la disponibilité de la solution d'hébergement).
**ENF-DISPO-002 : Fiabilité des Liens**
Bien que la maintenance des applications cibles soit hors périmètre, les URLs listées dans le portail doivent être correctes au moment de leur intégration. Un mécanisme de vérification périodique des liens (manuel ou semi-automatisé) pourrait être envisagé hors projet.

### 3.8. Conformité Légale et Réglementaire

**ENF-LEGAL-001 : Droit d'Auteur**
Le pied de page doit inclure la mention de copyright "© [Année en cours] DRSM IDF - Tous droits réservés."
**ENF-LEGAL-002 : Données Personnelles (RGPD)**
Le Portail, dans sa version actuelle, ne collecte ni ne traite de données personnelles des utilisateurs. Si des évolutions futures impliquent une telle collecte (ex: favoris liés à un utilisateur), une analyse d'impact sur la protection des données (AIPD) sera nécessaire.

## 4. ARCHITECTURE ET SPÉCIFICATIONS TECHNIQUES

### 4.1. Architecture Applicative

Le Portail est conçu comme une application web monopage (Single Page Application - SPA) côté client. L'ensemble de la logique de présentation, de recherche et de filtrage est exécuté par le navigateur de l'utilisateur via JavaScript. Il n'y a pas de composant back-end dédié pour cette application.

### 4.2. Technologies Imposées et Recommandées

*   **HTML5 :** Pour la structure sémantique de la page.
*   **CSS3 :** Pour la mise en forme.
    *   **Framework CSS : Tailwind CSS (v3.x ou supérieure)** utilisé via CDN pour un développement rapide et un design responsive.
    *   Des styles CSS personnalisés additionnels sont permis et intégrés dans la balise `<style>` du fichier HTML principal pour des ajustements spécifiques non couverts nativement ou facilement par Tailwind.
*   **JavaScript (ES6+ Vanilla) :** Pour toute la logique dynamique, sans framework JavaScript majeur (type React, Angular, Vue) pour cette version.
    *   Manipulation du DOM.
    *   Gestion des événements.
    *   Logique de recherche et de filtrage.
    *   Génération dynamique des cartes d'applications et des options de filtre.
*   **Icônes : Font Awesome (v6.x ou supérieure)** utilisé via CDN.

### 4.3. Structure et Gestion des Données

Les données des applications sont stockées localement dans un tableau JavaScript (`const applications = [...]`) au sein du fichier HTML principal. La structure de chaque objet application est détaillée à la section EF-DATA-002.

### 4.4. Environnement Technique (Déploiement, Hébergement)

**ENF-DEPL-001 : Hébergement**
Le Portail, étant un ensemble de fichiers statiques (un fichier HTML unique), doit être hébergé sur un serveur web standard capable de servir des fichiers statiques (ex: Apache, Nginx, ou solutions d'hébergement de sites statiques type GitHub Pages, Netlify, AWS S3, etc.). La solution d'hébergement sera définie par la DRSM IDF ou l'entité responsable de l'infrastructure.
**ENF-DEPL-002 : Nom de Domaine / URL d'Accès**
L'URL d'accès au Portail sera communiquée par la DRSM IDF. Elle devra être simple et mémorisable.

## 5. GESTION DE PROJET

### 5.1. Acteurs et Rôles

| Rôle                                     | Entité / Personne (à compléter) | Responsabilités Principales                                                                                                |
| :--------------------------------------- | :------------------------------ | :------------------------------------------------------------------------------------------------------------------------- |
| **Commanditaire (Sponsor)**              | Direction de la DRSM IDF        | Validation des orientations stratégiques, approbation du budget et des livrables majeurs.                                    |
| **Chef de Projet MOA**                   | [Nom à compléter], DRSM IDF     | Pilotage du projet côté métier, expression des besoins, validation fonctionnelle, coordination des utilisateurs, recette. |
| **Référents Métier / Utilisateurs Clés** | [Noms à compléter], DRSM IDF    | Participation à la définition des besoins, tests utilisateurs, feedback.                                                   |
| **Chef de Projet MOE** (si externe)      | [Nom à compléter], Prestataire  | Pilotage de la réalisation technique, gestion des ressources de développement, respect des engagements (qualité, délai, coût). |
| **Équipe de Développement**              | MOE (interne ou externe)        | Conception technique, développement, tests unitaires et d'intégration, correction des anomalies.                         |
| **Référent Technique/Architecte**        | DSI / MOE                       | Validation des choix techniques, support à l'équipe de développement, supervision de l'intégration.                      |
| **Référent Sécurité (RSSI)**             | DRSM IDF / DSI                  | Validation des aspects sécurité, conseil sur les bonnes pratiques.                                                         |

### 5.2. Phasage et Planning Prévisionnel (si applicable pour cette version)

Ce CdC V2.0 formalise un existant. Les phases de conception initiale et de développement sont considérées comme achevées. Les phases restantes peuvent inclure :
1.  **Phase de Validation et Recette (V2.0) :** [Durée à définir]
    *   Revue et validation du présent CdC V2.0.
    *   Tests d'acceptation par la MOA sur la base des critères définis.
    *   Correction des anomalies résiduelles.
2.  **Phase de Préparation à la Mise en Production :** [Durée à définir]
    *   Finalisation de la documentation.
    *   Préparation de l'environnement de production.
3.  **Phase de Mise en Production et Lancement :** [Date Cible à définir]
    *   Déploiement sur l'environnement de production.
    *   Communication et lancement officiel auprès des utilisateurs.
4.  **Phase de Suivi Post-Lancement :** [Durée à définir]
    *   Monitoring initial, collecte des premiers retours utilisateurs.

### 5.3. Livrables Attendus

| Réf.   | Livrable                                                               | Format        | Phase de Livraison |
| :----- | :--------------------------------------------------------------------- | :------------ | :----------------- |
| [LIV-01]| Cahier des Charges V2.0 (le présent document)                          | Document Word/PDF | Validation         |
| [LIV-02]| Fichier source du Portail (`portail_applications_drsm_idf.html` ou nom similaire) | HTML          | Recette            |
| [LIV-03]| Documentation Utilisateur (simplifiée, ex: guide de prise en main)     | Document Word/PDF | Mise en Production |
| [LIV-04]| Documentation Technique pour la Maintenance (mise à jour des données)  | Document Word/PDF | Mise en Production |
| [LIV-05]| Rapport de Recette (incluant les PV de recette)                        | Document Word/PDF | Recette            |

### 5.4. Critères d'Acceptation

La recette du Portail sera prononcée favorablement si l'ensemble des critères suivants sont satisfaits :
*   **CA-01 : Conformité Fonctionnelle :** Toutes les exigences fonctionnelles décrites dans la section 2 sont implémentées et fonctionnent comme attendu. Un cahier de tests basé sur ces exigences sera utilisé.
*   **CA-02 : Conformité Non-Fonctionnelle :** Les principales exigences non-fonctionnelles (performance de base, compatibilité navigateurs, responsive design, accessibilité de base) sont respectées.
*   **CA-03 : Qualité des Données :** La liste initiale des applications est correctement intégrée, les informations (nom, URL, service, catégorie, portée, icône) sont exactes et cohérentes. Un échantillon représentatif d'applications sera testé (ouverture des liens, affichage des informations).
*   **CA-04 : Stabilité :** Aucune anomalie bloquante ou majeure n'est détectée lors des tests sur les navigateurs et appareils cibles.
*   **CA-05 : Documentation :** Les livrables documentaires ([LIV-03], [LIV-04]) sont complets, clairs et conformes à la solution livrée.
*   **CA-06 : Livraison du Code Source :** Le fichier HTML final est livré et correspond à la version validée.

### 5.5. Modalités de Suivi et de Reporting

(À adapter si le projet continue avec une MOE externe ou des phases significatives)
*   Des points de suivi réguliers seront organisés entre la MOA et la MOE (si applicable).
*   Un reporting d'avancement sera fourni par la MOE à la MOA selon une fréquence à définir.

### 5.6. Gestion des Risques (Identifiés à ce stade)

| Réf.   | Description du Risque                                                                    | Criticité (Faible/Moyen/Fort) | Mesures de Prévention / Atténuation                                                                          |
| :----- | :--------------------------------------------------------------------------------------- | :-------------------------- | :----------------------------------------------------------------------------------------------------------- |
| [RISK-01]| Erreurs ou obsolescence des données des applications (URL, nom, etc.) après le lancement. | Moyen                       | Processus de mise à jour régulier (manuel), sensibilisation des référents applications.                      |
| [RISK-02]| Difficulté de maintenance du fichier unique si le nombre d'applications croît fortement. | Moyen                       | Envisager l'externalisation des données (JSON) comme évolution future prioritaire.                           |
| [RISK-03]| Non-adoption par les utilisateurs si le portail n'est pas perçu comme utile ou à jour. | Fort                        | Communication efficace, implication des utilisateurs, maintien de la qualité des données.                  |
| [RISK-04]| Indisponibilité des CDN (Tailwind, Font Awesome).                                        | Faible                      | Utiliser des versions hébergées localement en cas de besoin critique (évolution future). Suivre statut des CDN. |

## 6. EXPLOITATION, MAINTENANCE ET SUPPORT

### 6.1. Procédures de Mise à Jour du Contenu

**Exploit-001 : Gestion des Applications**
L'ajout, la modification ou la suppression d'applications s'effectue en éditant directement le tableau JavaScript `applications` dans le fichier HTML source du Portail.
Cette opération requiert des compétences techniques de base (édition HTML/JavaScript) et un accès au fichier source sur le serveur d'hébergement.
Une procédure détaillée sera fournie dans la Documentation Technique ([LIV-04]).

**Exploit-002 : Gestion des Filtres**
*   Les options des filtres "Services ER" et "Catégories" sont générées dynamiquement à partir des données du tableau `applications`. Leur mise à jour est donc implicite lors de la modification des données des applications.
*   Les options du filtre "Échelons" sont codées en dur dans la fonction `renderEchelonFilters` du code JavaScript. Leur modification nécessite une intervention sur le code.

**Exploit-003 : Fréquence des Mises à Jour**
La fréquence des mises à jour du contenu sera déterminée par la DRSM IDF en fonction des besoins et des évolutions du parc applicatif. Un processus de collecte des demandes de mise à jour (nouveaux outils, suppressions, modifications) devra être mis en place.

### 6.2. Support Utilisateur

Un point de contact interne à la DRSM IDF (service support informatique, référent métier désigné) sera identifié pour recueillir les retours utilisateurs, les demandes d'assistance de premier niveau et les suggestions d'amélioration.

### 6.3. Sauvegarde et Restauration

Le fichier HTML du Portail devra être inclus dans les procédures de sauvegarde régulières de l'environnement d'hébergement. La restauration consistera à redéployer la version sauvegardée du fichier.

## 7. ÉVOLUTIONS FUTURES ENVISAGÉES

Les pistes d'amélioration suivantes sont identifiées pour des versions ultérieures du Portail et ne font pas partie du périmètre de la V2.0 :
*   **EVOL-01 : Externalisation des Données :** Migrer la liste des applications et leurs métadonnées vers un fichier de données externe (ex: JSON) chargé dynamiquement par le Portail. Cela simplifierait grandement les mises à jour sans nécessiter d'éditer le code JavaScript.
*   **EVOL-02 : Interface d'Administration :** Développer une interface web simple et sécurisée permettant à des administrateurs désignés de gérer la liste des applications (CRUD) sans intervention technique sur le code source.
*   **EVOL-03 : Personnalisation Utilisateur :**
    *   Permettre aux utilisateurs de marquer des applications comme "favorites" pour un accès rapide.
    *   Sauvegarder les filtres préférés ou le dernier état de recherche.
    *   (Nécessiterait une gestion des profils utilisateurs et potentiellement une authentification).
*   **EVOL-04 : Tests d'Accessibilité Approfondis :** Conduire un audit de conformité RGAA complet par un expert et appliquer les correctifs nécessaires pour atteindre un niveau de conformité élevé.
*   **EVOL-05 : Statistiques d'Utilisation :** Intégrer un mécanisme (anonymisé et conforme RGPD) pour collecter des statistiques sur les applications les plus consultées, les recherches fréquentes, etc., afin d'optimiser le portail.
*   **EVOL-06 : Internationalisation (i18n) :** Si besoin, rendre l'interface traduisible dans d'autres langues.
*   **EVOL-07 : Intégration SSO :** Si un système d'authentification unique est déployé, explorer les possibilités d'intégration.
*   **EVOL-08 : Vérification Automatique des Liens :** Mettre en place un script ou un service pour vérifier périodiquement la validité des URLs des applications référencées et signaler les liens brisés.
