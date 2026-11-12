# Les Saveurs de Ruth — Site traiteur

Site vitrine statique en français, prêt pour GitHub et **Cloudflare Pages**. Aucun serveur ni base de données requis.

## Structure

```text
public/
  index.html               # Page principale
  favicon.svg              # Icône du site
  _headers                 # En-têtes de sécurité
  assets/css/style.css     # Styles
  assets/js/main.js        # Navigation, galerie et formulaire WhatsApp
```

## Publication avec GitHub et Cloudflare Pages

1. Créer un dépôt GitHub (par exemple `les-saveurs-de-ruth`).
2. Mettre **le contenu de ce dossier** à la racine du dépôt (le dossier `public` doit être visible à la racine).
3. Dans le tableau de bord Cloudflare, ouvrir **Workers & Pages**, puis créer une application **Pages** en connectant le dépôt GitHub.
4. Dans la configuration de la construction :
   - **Framework preset** : `None` (Aucun)
   - **Build command** : laisser vide
   - **Build output directory** : `public`
   - **Root directory** : `/` (racine du dépôt)
5. Déployer. Cloudflare fournit une adresse `*.pages.dev`. Les nouveaux commits GitHub déclencheront ensuite les redéploiements si l'intégration est activée.

> Choisir **Pages (connexion Git)**, pas un projet Workers avec une commande de compilation.

## Tester localement

Ouvrir `public/index.html` dans un navigateur pour vérifier les sections. Pour reproduire les chemins absolus (`/assets/...`), démarrer un serveur statique depuis `public` :

```bash
cd public
python -m http.server 8000
```

Puis ouvrir `http://localhost:8000`.

## Contact et devis

Le numéro WhatsApp est configuré dans `public/assets/js/main.js` : **+225 07 98 98 79 74** (`2250798987974`). Le formulaire construit un message prérempli et ouvre WhatsApp; le visiteur confirme l'envoi. Il n'y a ni collecte de données côté serveur, ni paiement en ligne.

Les images illustratives proviennent d'Unsplash et les polices de Google Fonts : **leur affichage demande une connexion Internet**. Les coordonnées e-mail restent « Adresse à renseigner » dans la rubrique contact. Remplacer les images d'illustration par des photos autorisées du traiteur si possible.

## Personnalisation

- Texte, formules, tarifs et contenus : `public/index.html`
- Couleurs et présentation : `public/assets/css/style.css`
- WhatsApp et interactions : `public/assets/js/main.js`

## Portrait de la cheffe

La photo fournie est intégrée à l’accueil (bannière), à la section de présentation et à la galerie. Elle est stockée localement dans `public/assets/images/cheffe-ruth.webp` afin d’être déployée automatiquement par Cloudflare Pages.
