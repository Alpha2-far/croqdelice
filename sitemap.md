# Plan du site — CROQ’Délice (Sitemap Markdown)

Ce document présente l'arborescence complète, les rôles des pages et les commandes `curl` permettant aux agents, développeurs et robots d'indexer ou d'interroger les ressources du site officiel de **CROQ’Délice**.

**Nom commercial :** CROQ’Délice  
**Activité :** Restaurant de croque-monsieurs maison et formules à Cococodji (Bénin)  
**URL de référence :** `https://croqdelice.com`  
**Dernière mise à jour :** 31 octobre 2026

---

## 1. Arborescence & Pages Principales

### 1.1 Page d'Accueil (`/` ou `/index.html`)
- **Titre :** CROQ’Délice — Le goût du fait maison
- **Description :** Présentation du concept, vitrine des spécialités, accroche de commande WhatsApp et accès rapide au menu.
- **Ressources associées :** `styles.css`, `app.js`, `assets/hero.jpg`, `assets/logo.png`.
- **Exemple curl :**
  ```bash
  curl -sSL https://croqdelice.com/ | grep -i "<title>"
  ```

### 1.2 Menu Complet (`/menu.html`)
- **Titre :** Le menu — CROQ’Délice
- **Description :** Carte exhaustive des 6 recettes de croques artisanaux et des 3 formules complètes (boisson + frites) avec tarifs en FCFA.
- **Points d'ancrage :** `#croques` (les croques à l'unité), `#formules` (les formules complètes).
- **Exemple curl :**
  ```bash
  curl -sSL https://croqdelice.com/menu.html
  ```

### 1.3 À Propos (`/apropos.html`)
- **Titre :** À propos — CROQ’Délice
- **Description :** L'histoire de la marque, son ancrage local à Cococodji, son engagement pour le fait maison et lien vers son compte officiel TikTok (`@croqdelice4`).
- **Exemple curl :**
  ```bash
  curl -sSL https://croqdelice.com/apropos.html
  ```

### 1.4 Galerie Gourmande (`/galerie.html`)
- **Titre :** Galerie — CROQ’Délice
- **Description :** Galerie visuelle présentant les réalisations, les assiettes servies et les coulisses de la préparation en atelier.
- **Exemple curl :**
  ```bash
  curl -sSL https://croqdelice.com/galerie.html
  ```

### 1.5 Panier & Commande WhatsApp (`/panier.html`)
- **Titre :** Mon panier — CROQ’Délice
- **Description :** Interface de gestion des articles commandés, calcul du sous-total en FCFA et formulaire de transmission automatique vers WhatsApp (`+229 01 51 15 19 19`).
- **Exemple curl :**
  ```bash
  curl -sSL https://croqdelice.com/panier.html
  ```

---

## 2. Fichiers Techniques & Découverte IA

| Chemin | Format | Utilité | Exemple curl |
| :--- | :--- | :--- | :--- |
| `/llms.txt` | Texte Markdown | Fiche d'identité synthétique & tarifs pour LLM | `curl -sSL https://croqdelice.com/llms.txt` |
| `/sitemap.xml` | XML standard | Plan de site XML pour moteurs de recherche | `curl -sSL https://croqdelice.com/sitemap.xml` |
| `/sitemap.md` | Markdown | Présent document de découverte structurée | `curl -sSL https://croqdelice.com/sitemap.md` |
| `/rss.xml` | RSS 2.0 (XML) | Flux des créations culinaires et actualités | `curl -sSL https://croqdelice.com/rss.xml` |
| `/robots.txt` | Fichier texte | Consignes pour robots d'exploration web | `curl -sSL https://croqdelice.com/robots.txt` |

---

## 3. Endpoints & Commandes Utiles

Pour tester la disponibilité et les en-têtes HTTP du site :
```bash
# Vérifier la réponse HTTP 200 de l'accueil
curl -I https://croqdelice.com/

# Télécharger les informations machine pour IA
curl -s https://croqdelice.com/llms.txt | head -n 25

# Valider l'accès au flux RSS
curl -s https://croqdelice.com/rss.xml | grep "<title>"
```

