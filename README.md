# Marseille et les Calanques — carnet de voyage

Carnet de voyage interactif du séjour à Marseille du vendredi 6 au vendredi 13 novembre 2026 (une nuit à Balaruc, six à Marseille) : bloc « Aujourd'hui » qui suit le jour en cours, itinéraire et récit jour par jour avec carte, randonnées, visites, dossiers « Plus loin », logement, météo en direct, infos pratiques, et préparatifs regroupés en fin de page.

Publié sur **https://nogues.app/marseille/**.

## Organisation

| Élément | Rôle |
|---|---|
| `docs/index.html` | Le site complet, en un seul fichier (HTML, CSS et JavaScript) |
| `docs/.htaccess` | Exclut le carnet des moteurs de recherche (accessible par lien uniquement) |
| `.github/workflows/deploy-ovh.yml` | Publie `docs/` sur l'hébergement OVHcloud à chaque mise à jour |

Le contenu du séjour (jours, lieux, randonnées, visites, réservations) est regroupé au début du script de `docs/index.html`, dans les constantes `DAYS`, `PLACES`, `HIKES`, `VISITS` et `RESA` : c'est là qu'il faut intervenir pour modifier le programme.

## Publication

Chaque modification poussée sur `main` dans `docs/` déclenche la publication vers `www/marseille` sur l'hébergement OVHcloud de nogues.app. Le workflow attend trois secrets de dépôt (Settings > Secrets and variables > Actions) : `OVH_SFTP_HOST`, `OVH_SFTP_USER`, `OVH_SFTP_PASSWORD`, identiques à ceux des autres sites de nogues.app. La variable `OVH_TARGET_DIR` permet de changer le dossier de destination.

Sans ces secrets, le workflow se termine sans erreur mais ne publie rien. Une publication peut aussi être relancée à la main depuis l'onglet Actions (« Run workflow »).

## Services externes

Carte : Leaflet, fonds OpenStreetMap et OpenTopoMap. Météo : Open-Meteo, sans clé. Les statuts de réservation et cases cochées sont enregistrés dans le navigateur de chaque appareil.
