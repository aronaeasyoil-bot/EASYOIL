# EASYOIL — site institutionnel

21 pages en **français, anglais et arabe** (RTL), plus une page 404. Logo officiel et photos EASYOIL, accompagnés de visuels d’illustration pour le transport maritime, le gaz et les renouvelables.

Le site est entièrement statique : aucun serveur, aucune base de données, aucune dépendance npm à installer. Il peut être déplacé chez un autre hébergeur en publiant le dossier `dist`.

## Développement

Node.js 22 ou ultérieur.

```sh
npm run build
npm run check
npm start
```

Prévisualisation : http://127.0.0.1:4173

- `dist/content.js` : textes et traductions.
- `dist/app.js` : composants et formulaire.
- `dist/pages.js` : composition des pages, navigation et recherche.
- `dist/style.css`, `dist/modern.css` : présentation responsive.
- `dist/assets` : logo, photographies et illustrations.
- `build-pages.cjs` : génération des documents HTML.

Navigation fixe, menus déroulants, recherche locale (Ctrl/Cmd+K), fils d’Ariane, filtres des publications, carte à onglets, formulaires conditionnels et retour en haut. Les liens conservent la langue. Les URL canoniques utilisent le domaine sur lequel le site est consulté.

## Cloudflare Pages — configuration recommandée

Créer un projet **Pages** depuis ce dépôt GitHub :

| Paramètre | Valeur |
| --- | --- |
| Branche de production | `main` |
| Framework | Aucun |
| Répertoire racine | racine du dépôt |
| Commande de build | `npm run build && npm run check` |
| Dossier de sortie | `dist` |
| Variable `NODE_VERSION` | `22` |

L’intégration GitHub permet de publier automatiquement après chaque push sur `main`. L’autorisation Cloudflare/GitHub doit être accordée depuis le compte propriétaire ; aucun jeton ne doit être ajouté au dépôt.

Une publication manuelle est aussi possible en téléversant le contenu de `dist` dans Pages. Ce mode n’active pas à lui seul la publication automatique depuis GitHub.

Les en-têtes HTTP sont définis dans `dist/_headers`. Le fichier `404.html` fournit une vraie page d’erreur au lieu d’un repli implicite vers l’accueil. Les fichiers d’origine ne sont pas liés à ChatGPT Sites.

## Points à compléter pour l’exploitation commerciale

- Adresse officielle de réception et service d’envoi du formulaire : il prépare actuellement un fichier texte local, **sans envoi**.
- Dénomination légale, immatriculation, adresse et coordonnées de l’éditeur.
- Validation des contenus par EASYOIL et relecture de la version arabe.
- Domaine de production à connecter depuis Cloudflare une fois disponible.

Aucun volume, certification, client, contrat ou partenaire n’a été inventé. Les notes éditoriales expliquent des sujets énergétiques ; ce ne sont pas des annonces d’actualité. Les images générées restent illustratives. Fond de carte : Natural Earth, domaine public. Les polices sont fournies par Google Fonts.

## Limites d’hébergement

Cloudflare Pages est adapté à ce site statique. Les quotas et conditions de service s’appliquent toujours ; aucun hébergeur ne garantit une absence totale d’interruption. Ne pas ajouter de Functions ou de service payant sans réévaluer les coûts. Sauvegarder le dépôt et utiliser un domaine contrôlé par l’entreprise facilite un changement d’hébergeur.
