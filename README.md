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
