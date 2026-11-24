# Atelier — interface améliorée pour Suivi des demandes & devis

Cette version remplace uniquement l'interface publique (`public/index.html`, `public/style.css`, `public/app.js`). Le serveur Express, l'authentification, la base SQLite et les routes API d'origine sont conservés.

## Mise à jour dans GitHub Codespaces

1. Téléchargez et décompressez ce ZIP.
2. Dans votre dépôt GitHub, remplacez les trois fichiers existants du dossier `public/` par ceux du ZIP.
3. Ne remplacez pas `server.js`, `.env`, ni le dossier `data/`.
4. Dans Codespaces, utilisez Node 20 :
   ```bash
   nvm use 20
   npm start
   ```
5. Rechargez l'onglet de l'application en forçant le rafraîchissement (`Ctrl+Shift+R`).

## Ce qui change

- Nouvelle interface responsive avec navigation latérale et vues tableau de bord, demandes, pipeline et relances.
- Indicateurs calculés à partir des demandes existantes.
- Ajout d'une demande dans une fenêtre dédiée.
- Fiche détaillée pour modifier statut, montant et date de relance.
- Envoi manuel de l'accusé e-mail via la route SMTP existante (si SMTP configuré).
- Recherche, filtre par statut et export CSV.
- Les données restent dans l'API et la base SQLite existantes.

## Important — limites et précautions

- Le pipeline est une vue visuelle ; les étapes sont modifiées dans la fiche de demande.
- L'accusé e-mail ne fonctionne que si SMTP est correctement configuré. L'interface affiche une erreur si le service n'est pas configuré.
- Les graphiques et chiffres sont calculés depuis les données enregistrées ; aucune donnée de démonstration n'est ajoutée.
- La police Google Fonts nécessite une connexion internet ; le navigateur utilise des polices système en secours.
- Cette amélioration ne transforme pas le projet en service certifié prêt pour des données réelles. Avant production : HTTPS, sauvegardes et restauration testées, mise à jour/audit des dépendances, gestion des secrets, mentions RGPD et politique de conservation, supervision et tests de sécurité. L'application reste mono-administrateur.
- Votre fichier `.env` et votre base `data/` sont privés : ne les téléversez jamais sur GitHub.
