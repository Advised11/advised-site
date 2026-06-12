# Advised — Site (Astro)

Site vitrine de **Advised**, activité de freelance SEO de Francis Ndimba.
Design : univers Klimb (Figtree, dégradés violets, mode sombre maîtrisé).

## Stack
- [Astro](https://astro.build) — site statique, ultra-rapide et bon pour le SEO
- Aucune dépendance front lourde : HTML/CSS, une pincée de JS vanilla
- Polices Figtree + JetBrains Mono (chargées via Google Fonts dans `src/styles/advised.css`)

## Démarrer en local

Prérequis : **Node.js 18+**.

```bash
npm install
npm run dev      # http://localhost:4321
```

Build de production :

```bash
npm run build    # génère /dist
npm run preview  # prévisualise le build
```

## Structure

```
astro/
├─ public/                 # fichiers servis tels quels
│  ├─ favicon.svg
│  ├─ francis.png          # portrait (page À propos)
│  ├─ logo-light.png       # logo clair (nav/footer sombres)
│  └─ logo-dark.png        # logo sombre (fonds clairs)
├─ src/
│  ├─ layouts/Base.astro   # <head>, Nav, Footer, scripts globaux
│  ├─ components/
│  │  ├─ Nav.astro
│  │  └─ Footer.astro
│  ├─ pages/               # une route = un fichier
│  │  ├─ index.astro       # /
│  │  ├─ services.astro    # /services
│  │  ├─ a-propos.astro    # /a-propos
│  │  └─ contact.astro     # /contact
│  └─ styles/advised.css   # design system complet (couleurs, typo, composants)
├─ astro.config.mjs
└─ package.json
```

## À personnaliser

1. **Portrait & logo** : déjà intégrés (`public/francis.png`, `public/logo-*.png`,
   favicon généré). Remplacez simplement les fichiers pour les mettre à jour.
3. **Liens** : LinkedIn, Calendly et l'email sont centralisés en haut de
   `Nav.astro` et `Footer.astro`.
4. **Cas clients** : LumApps, Groupe SEB, Rubix et SMAC sont intégrés avec leurs
   résultats chiffrés (source : présentation Advised).
5. **Mentions légales / Confidentialité** : liens présents dans le footer, pages à créer.

## Formulaire de contact

Le formulaire (`/contact`) pointe par défaut vers `mailto:contact@advised-seo.fr`.
Pour un envoi sans ouverture du client mail, branchez un service comme
[Formspree](https://formspree.io) ou [Web3Forms](https://web3forms.com) :
remplacez l'attribut `action` du `<form>` par l'endpoint fourni.

## Déploiement

### Vercel / Netlify (recommandé)
1. Poussez ce dossier sur GitHub.
2. « New Project » → importez le repo → le framework Astro est détecté automatiquement.
3. Build command `npm run build`, output `dist`. C'est tout.

### GitHub Pages
1. Décommentez/adaptez `base` dans `astro.config.mjs` si le site est servi depuis un
   sous-dossier (`https://user.github.io/advised`).
2. Ajoutez l'action officielle `withastro/action` dans `.github/workflows/`.

---
© Advised — Francis Ndimba.
