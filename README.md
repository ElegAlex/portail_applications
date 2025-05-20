# Portail des Applications DRSM Île-de-France

**Version :** 1.0
**Date de création :** 13 Mai 2025
**Auteur :** [Votre Nom/Nom de l'Équipe]

## 1. Introduction

Ce document README fournit une description complète du projet "Portail des Applications DRSM Île-de-France". L'objectif de ce portail est de fournir un point d'accès centralisé, simple et efficace à l'ensemble des applications utilisées par les collaborateurs de la DRSM Île-de-France. Il vise à améliorer la productivité en réduisant le temps de recherche des outils nécessaires au quotidien.

## 2. Objectifs du Projet

*   **Centralisation :** Regrouper tous les liens d'applications pertinents en un seul endroit.
*   **Accessibilité :** Offrir un accès rapide et intuitif aux applications.
*   **Filtrage :** Permettre aux utilisateurs de filtrer les applications par service, catégorie et échelon.
*   **Recherche :** Intégrer une fonctionnalité de recherche textuelle pour trouver des applications par nom.
*   **Responsive Design :** Assurer une expérience utilisateur optimale sur différents appareils (ordinateurs de bureau, tablettes, mobiles).
*   **Clarté Visuelle :** Distinguer visuellement les applications locales des applications nationales.

## 3. Fonctionnalités Principales

### 3.1. Affichage des Applications

Les applications sont présentées sous forme de cartes cliquables dans une grille.

Chaque carte affiche :
*   Une icône principale.
*   Le nom de l'application.
*   Le service associé.
*   La catégorie de l'application.
*   Un indicateur visuel de portée (locale ou nationale).

Les applications sont triées par ordre alphabétique.
Un clic sur une carte ouvre l'URL de l'application dans un nouvel onglet.
Chaque carte propose également un bouton "Documentation" ouvrant la page de manuel utilisateur correspondante.

### 3.2. Barre de Recherche

*   Permet de rechercher des applications par leur nom.
*   La recherche est insensible à la casse et s'effectue en temps réel.
*   La barre de recherche reste visible en haut de la section des applications lors du défilement.

### 3.3. Filtres d'Affectation

Une colonne latérale "Affectation" contient trois types de filtres présentés sous forme d'accordéons (repliés par défaut) :

*   **Services ER :** Filtre par service (ex: `SI`, `CCX`, `COM`). Inclut une option `"Tous"`.
*   **Échelons :** Filtre par échelon géographique (ex: `ELSM 75`, `ELSM 77`). Inclut une option `"Tous les échelons"`.
*   **Catégories :** Filtre par catégorie fonctionnelle (ex: `Documentation`, `Pilotage`, `Métier`). Inclut une option `"Toutes"`.

**Logique de filtrage :**
*   La sélection d'un filtre spécifique (Service ER, Échelon ou Catégorie) désactive et réinitialise les deux autres types de filtres à leur valeur par défaut (`"Tous"` ou `"Toutes"`).
*   Les applications de catégories définies comme `"globales"` (ex: `"Ressources Humaines"`, `"Communication"`) peuvent s'afficher même si un filtre de service spécifique est actif, si elles correspondent également au filtre de catégorie (si celui-ci est actif et n'est pas `"Toutes"`).
*   La recherche textuelle s'applique toujours en dernier, sur les résultats des filtres d'affectation.

### 3.4. Indicateurs de Portée

*   **Applications Locales (Île-de-France) :**
    *   Cercle de fond de l'icône principale de couleur verte.
    *   Icône principale de couleur verte.
    *   Petite icône "punaise" (`fa-map-pin`) verte en haut à droite de la carte.
*   **Applications Nationales :**
    *   Cercle de fond de l'icône principale de couleur bleue.
    *   Icône principale de couleur bleue.
    *   Petite icône "drapeau" (`fa-flag`) bleue en haut à droite de la carte.

### 3.5. Design et Ergonomie

*   Interface épurée, professionnelle et moderne.
*   Design responsive pour une utilisation sur tous les appareils.
*   Utilisation de `Tailwind CSS` pour le style.
*   Icônes `Font Awesome` pour une meilleure identification visuelle.
*   Barres de défilement indépendantes pour la colonne des filtres et la grille des applications sur les écrans larges.

## 4. Structure du Projet et Technologies

*   **Fichier Unique :** L'ensemble du portail (HTML, CSS, JavaScript) est contenu dans un seul fichier `index.html` (ou le nom que vous lui avez donné).
*   **HTML5 :** Structure sémantique de la page.
*   **CSS3 (via `Tailwind CSS`) :** Mise en forme et design responsive. Quelques styles CSS personnalisés sont inclus dans la balise `<style>` pour des ajustements spécifiques.
*   **JavaScript (ES6+) :**
    *   Gestion dynamique des données des applications.
    *   Génération des cartes d'applications.
    *   Implémentation de la logique de recherche et de filtrage.
    *   Gestion des accordéons pour les filtres.
    *   Détermination de la portée (locale/nationale) et application des styles correspondants.
*   **Dépendances externes :**
    *   `Tailwind CSS` (via CDN).
    *   `Font Awesome` (via CDN).

## 5. Données des Applications

Les informations sur les applications sont stockées dans un tableau JavaScript `applications` au sein du fichier HTML. Chaque objet `application` dans ce tableau possède les propriétés suivantes :

*   `id`: (Numérique) Identifiant unique.
*   `name`: (Chaîne) Nom de l'application (nettoyé pour l'affichage).
*   `url`: (Chaîne) URL d'accès à l'application. Les URLs commençant par `#` sont traitées comme des placeholders non cliquables.
*   `service`: (Chaîne) Service principal associé (ex: `"SI"`, `"COM"`, `"À définir"`).
*   `category`: (Chaîne) Catégorie fonctionnelle (ex: `"Documentation"`, `"Métier"`, `"À définir"`).
*   `echelon`: (Chaîne) Échelon géographique concerné (ex: `"ELSM 75"`, `"À définir"`).
*   `icon`: (Chaîne) Classe Font Awesome pour l'icône principale (ex: `"fa-cogs"`).
*   `iconColor`: (Chaîne) Classe Tailwind CSS pour la couleur de l'icône principale (ex: `"text-blue-600"`).
*   `scope`: (Chaîne) Portée de l'application : `'local'`, `'national'`, ou `'unknown'`.
*   `docUrl`: (Chaîne) URL vers la documentation de l'application. Par défaut, un fichier `docs/<nom>.html` est supposé.

## 6. Installation et Utilisation

### 6.1. Prérequis

*   Un navigateur web moderne (Chrome, Firefox, Edge, Safari).

### 6.2. Lancement

Ouvrir le fichier HTML principal (ex: `index.html`) directement dans un navigateur web. Aucune installation de serveur ou de dépendances complexes n'est requise pour la version actuelle.

### 6.3. Utilisation

Consulter la section *3. Fonctionnalités Principales* de ce document pour comprendre comment interagir avec le portail.

## 7. Maintenance et Mise à Jour

### 7.1. Gestion des Applications

Pour ajouter, modifier ou supprimer une application :

1.  Ouvrir le fichier HTML du portail dans un éditeur de texte ou un IDE.
2.  Localiser le tableau JavaScript `const applications = [...]`.
3.  Modifier ce tableau en respectant la structure d'objet décrite à la section *5. Données des Applications*.
    *   **Ajout :** Ajouter un nouvel objet à la fin du tableau.
    *   **Modification :** Modifier les propriétés d'un objet existant.
    *   **Suppression :** Supprimer l'objet correspondant du tableau.
4.  S'assurer que la propriété `id` reste unique pour chaque application (la logique actuelle réassigne les IDs séquentiellement au chargement, mais il est bon de le garder à l'esprit si vous modifiez manuellement).
5.  Sauvegarder le fichier. Les modifications seront visibles au prochain rechargement de la page.

### 7.2. Personnalisation des Filtres

*   **Services ER et Catégories :** Les options de ces filtres sont générées dynamiquement à partir des valeurs uniques présentes dans les champs `service` et `category` des applications. Pour ajouter un nouveau service ou une nouvelle catégorie, il suffit de l'utiliser dans les données d'une ou plusieurs applications.
*   **Échelons :** La liste des échelons est actuellement codée en dur dans la fonction `renderEchelonFilters`. Pour la modifier, il faut éditer cette fonction.

## 8. Pistes d'Améliorations Futures (Optionnel)

*   **Externalisation des données :** Charger la liste des applications depuis un fichier `JSON` externe pour faciliter les mises à jour sans modifier le code HTML/JS.
*   **Interface d'administration :** Créer une interface simple (protégée) pour gérer la liste des applications sans avoir à éditer le code source.
*   **Authentification/Personnalisation :** Si nécessaire, intégrer un système d'authentification pour afficher des applications spécifiques à certains rôles ou utilisateurs.
*   **Statistiques d'utilisation :** Collecter des données anonymes sur les applications les plus consultées.
*   **Tests d'accessibilité approfondis :** Valider la conformité avec les standards d'accessibilité (WCAG).
*   **Internationalisation (i18n) :** Si le portail devait être utilisé dans d'autres langues.

## 9. Contact

Pour toute question, suggestion ou rapport de bug, veuillez contacter :
[Nom du service/personne responsable et adresse e-mail ou moyen de contact]
