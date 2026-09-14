# Script-review

Build web minifié (auto-généré) de l'app **Script** — cette fois, la vraie
version web interactive (`apps/web`), pas juste un écran d'accueil. Le code
source réel vit dans le dépôt privé `Scipt` (nom de dépôt hérité d'une
coquille, le produit s'appelle Script) — ce dépôt ne contient que la sortie
de build, pas de logique.

**Ce qui fonctionne** : créer un projet, écrire un scénario (Fountain,
autocomplétion, verrouillage de numéros de scène, export PDF), ajouter des
panneaux de storyboard avec upload d'image. Les projets sont stockés dans ce
navigateur (SQLite en WebAssembly + IndexedDB) — **pas dans un vrai fichier**.
Vider le cache/les données du site efface les projets. Ceci sert à essayer
l'app et donner un aperçu, pas à y stocker du vrai travail — utilise l'app
installée (desktop, Tauri) pour ça.

Régénéré via `pnpm --filter @scipt/web build` dans le dépôt `Scipt`.

## Mise à jour du 14 septembre 2026

Source : dépôt privé `Scipt`, branche `claude/celtx-fyw3sq` (commit non renseigné —
archive reçue sans historique Git ; à compléter lors du prochain commit).

- L'option « Google Sheets » a été retirée du menu d'export (budget, planning, découpage) : il ne reste que PDF, Excel et, pour le budget, CSV. Après un export Excel, une aide explique comment l'ouvrir dans Excel/LibreOffice ou l'importer dans Google Sheets.
- Correction : cocher plusieurs formats à la fois (ex. PDF + Excel) ne téléchargeait que le premier fichier, le navigateur bloquant le second téléchargement déclenché juste après. Les formats sélectionnés sont désormais regroupés dans une seule archive ZIP.

## Mise à jour du 13 septembre 2026

Source : commit `a25114b0a2e06a98f0b3c05d9461c3727bafad4b` du dépôt privé `Scipt`.

- Scénario > Texte : bouton « Ajouter une page » et raccourci Ctrl+Entrée (Cmd+Entrée sur Mac).
- Flèches précédente/suivante et compteur de pages, défilement continu conservé.
- Sauts de page volontaires conservés dans la sauvegarde et pris en compte dans le PDF.
- Bouton « Soutenir » avec cœur après le sélecteur de thème dans la barre du projet, également présent sous la liste des projets : contribution Stripe ponctuelle à montant libre.
- Export scénario au choix : scénario, synopsis, note d'intention, personnages et statistiques, réunis dans un PDF ou séparés dans un ZIP.
- Exports Excel propres et modifiables pour le découpage, le planning et le budget ; les mêmes fichiers peuvent être importés dans Google Sheets sans connexion à Script.
- Le budget conserve ses valeurs numériques, ses formules et ses totaux séparés par devise.
- Libellé « Exporter le storyboard » clarifié.
- Contraste des cartes de planning corrigé dans le thème sombre.
- Dans le budget, le planning et le découpage, un unique bouton « Exporter » ouvre un choix PDF, Excel, Google Sheets et, pour le budget, CSV.

Le JavaScript et le CSS de l'application sont compilés et minifiés. Les sources TypeScript/React et les source maps ne sont pas publiées ici. La minification réduit la taille du code, elle ne constitue pas un chiffrement du JavaScript exécuté par le navigateur.

La synchronisation Google Drive n'est pas encore disponible. Les anciens fichiers à nom haché sont conservés pour les onglets qui auraient encore une ancienne page HTML en cache.
