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

## Mise à jour du 13 septembre 2026

Source : commit `cf07d8d5ddec8b8b6ddd2ae7cdd136f63376c082` du dépôt privé `Scipt`.

- Scénario > Texte : bouton « Ajouter une page » et raccourci Ctrl+Entrée (Cmd+Entrée sur Mac).
- Flèches précédente/suivante et compteur de pages, défilement continu conservé.
- Sauts de page volontaires conservés dans la sauvegarde et pris en compte dans le PDF.
- Bouton « Soutenir Script » sous la liste des projets : contribution Stripe ponctuelle à montant libre.

Le JavaScript et le CSS de l'application sont compilés et minifiés. Les sources TypeScript/React et les source maps ne sont pas publiées ici. La minification réduit la taille du code, elle ne constitue pas un chiffrement du JavaScript exécuté par le navigateur.

La synchronisation Google Drive n'est pas encore disponible. Les anciens fichiers à nom haché sont conservés pour les onglets qui auraient encore une ancienne page HTML en cache.
