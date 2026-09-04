# Site web — A.I.S.C Space Exploration Technologies SA

Site vitrine multi-pages, statique (HTML / CSS / JS), sans dépendance de build ni base de données. Il peut être hébergé tel quel sur n'importe quel hébergement web classique.

## Contenu du dossier

```
aisc-site/
├── index.html          Page d'accueil (FR) — mission, activités, vision
├── a-propos.html       À propos (FR) — identité légale, activités, partenaires, valeurs
├── equipe.html         Équipe (FR)
├── contact.html        Contact (FR) — coordonnées, carte, formulaire
├── en/                 Version anglaise du site (mêmes pages, contenu traduit)
│   ├── index.html
│   ├── about.html
│   ├── team.html
│   └── contact.html
├── assets/
│   ├── css/style.css   Feuille de style unique (design system du site)
│   ├── js/script.js    Menu mobile, animations, formulaire, retour en haut
│   ├── fonts/nasalizationrg.otf   Police de la marque (titres et logo)
│   └── img/            Images optimisées pour le web
│       ├── earth-launch.jpg
│       ├── spaceport.jpg
│       ├── control-room.jpg
│       ├── favicon.svg
│       ├── logo-header.png              logo AISC (version chrome claire, pour fonds sombres — header/footer)
│       ├── logo-print.png               même logo en version sombre (pour fonds clairs, print/letterhead)
│       ├── logo-original-ameliore.jpg   (ancien logo fourni, nettoyé — conservé en secours)
│       └── partners/                    logos des partenaires (Progenis BioSystems, ExoMecha)
└── README.md
```

## Mettre le site en ligne

Ce sont des fichiers statiques : il suffit de copier l'intégralité du dossier `aisc-site/` chez un hébergeur. Quelques options simples :

- **Hébergeur mutualisé classique (OVH, o2switch, etc.)** : envoyez le contenu du dossier par FTP/SFTP dans le répertoire public de votre domaine (souvent `www/` ou `public_html/`), en conservant la structure des dossiers.
- **Netlify / Vercel / GitHub Pages / Cloudflare Pages** : glissez-déposez le dossier `aisc-site/` (ou connectez un dépôt Git contenant ces fichiers) — aucune configuration de build n'est nécessaire.
- **Nom de domaine** : une fois en ligne, pointez votre domaine (ex. `aisc-space.com`) vers l'hébergement choisi.

Aucune base de données ni langage serveur (PHP, Node…) n'est requis.

## Version anglaise (EN)

Le site est désormais bilingue : le dossier `en/` contient une version anglaise complète (mêmes 4 pages, même design, contenu traduit). Un sélecteur **FR / EN** est présent dans le menu de chaque page (à côté du bouton « Nous contacter ») et renvoie systématiquement vers l'équivalent exact de la page consultée, dans l'autre langue.

Les pages anglaises partagent le même CSS, le même JavaScript et les mêmes images que les pages françaises (elles y font référence via `../assets/...`) — il n'y a donc qu'un seul design system à maintenir pour les deux langues. Le formulaire de contact s'adapte aussi automatiquement à la langue de la page (labels et messages en anglais sur `en/contact.html`).

Pour modifier un texte anglais, éditez directement le fichier correspondant dans `en/` — la structure HTML est identique à la version française, seul le texte change.

### Bambara

Une version en bambara n'a pas été ajoutée à cette livraison : il n'existe pas de vocabulaire standardisé pour les termes techniques du site (« spatioport », « société anonyme », « ingénierie spatiale »…), et une traduction de qualité insuffisante desservirait l'image de l'entreprise. Si vous souhaitez une version bambara, la meilleure approche est de préparer une traduction avec un locuteur natif (ou de me fournir une traduction validée) ; je peux ensuite l'intégrer au site selon la même structure que la version anglaise (`bm/index.html`, etc.).

## Modifier le contenu

Chaque page est un fichier HTML autonome et lisible : le texte peut être modifié directement dedans avec n'importe quel éditeur (VS Code, Notepad++...). La mise en forme (couleurs, espacements, polices) est centralisée dans `assets/css/style.css` — une modification y est répercutée sur toutes les pages, FR et EN comprises.

Pour changer une couleur de la marque, modifiez les variables en haut du fichier CSS (section `:root`), par exemple :

```css
--cyan: #49d3ff;   /* couleur d'accent principale */
--gold: #f0a83d;   /* couleur d'accent secondaire */
```

## Formulaire de contact

Le formulaire de la page `contact.html` fonctionne en mode `mailto:` : il ouvre le client email du visiteur avec le message pré-rempli, à destination de `aisc.space.technologies@gmail.com`. Aucun serveur n'est nécessaire, mais cela suppose que le visiteur ait un client email configuré sur son appareil.

Si vous préférez que les messages arrivent directement sans ouvrir de client email, il faudra brancher un service tiers de formulaires (ex. Formspree, Web3Forms) ou un petit script serveur — n'hésitez pas à me le demander, je peux l'intégrer.

## Police de caractères

La police `Nasalization` (fichier `assets/fonts/nasalizationrg.otf`) que vous avez fournie est utilisée pour le logo et les titres. Pensez à vérifier que vous disposez bien d'une licence d'usage commercial/web pour cette police avant la mise en ligne définitive — certaines polices "gratuites" ne sont autorisées que pour un usage personnel.

## Carte de localisation

La page Contact intègre une carte Google Maps pointant vers l'adresse du siège (ACI, Baco Djicoroni, Bamako). Un lien "Ouvrir dans Google Maps" est fourni en secours si la carte ne s'affiche pas (bloqueurs de publicité, etc.).
