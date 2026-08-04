# Script-review

Build web minifié (auto-généré) de l'app **Script**, pour prévisualisation
rapide de l'écran d'accueil. Le code source réel vit dans le dépôt privé
`Scipt` (nom de dépôt hérité d'une coquille, le produit s'appelle Script) —
ce dépôt ne contient que la sortie de build, pas de logique.

**Important** : les boutons "Nouveau projet" / "Ouvrir un projet" ne
fonctionneront pas dans un navigateur classique. Ils dépendent des API
Tauri (choix de dossier, lecture/écriture de fichiers, SQLite) qui n'existent
que dans l'app installée (desktop). Ce build web sert uniquement d'aperçu
visuel de l'écran d'accueil, pas de l'app fonctionnelle complète.

Régénéré via `pnpm --filter @scipt/desktop build` dans le dépôt `Scipt`.
