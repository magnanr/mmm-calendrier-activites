# Calendrier des activités — MMM

Page d'administration du calendrier des activités des Moucheurs du Montréal Métropolitain. Remplace le chiffrier
Excel exporté en PDF et publié sur le site du club — les activités sont maintenant ajoutées, modifiées et
supprimées directement en ligne, sans avoir à renvoyer un fichier à qui que ce soit.

**Site en ligne :** https://calendrieractivites.moucheursmontrealmetro.ca/admin.html

## Contenu du repo

| Fichier | Rôle |
|---|---|
| `admin.html` | Page d'administration — gestion des catégories, ajout/modification/suppression d'activités, aperçu public en bas de page |
| `CNAME` | Domaine personnalisé pour GitHub Pages |

Le code du Worker (API) et le schéma de la base de données D1 sont conservés séparément (pas dans ce repo, qui ne
contient que le HTML public de GitHub Pages) — voir `GUIDE-CONFIG-ADMIN.md` fourni au moment du déploiement pour
les détails complets.

## Comment ça fonctionne

- La **lecture** du calendrier (l'aperçu tout en bas de la page) est publique, sans mot de passe.
- L'**écriture** (catégories et activités) est protégée par un mot de passe, réservé aux personnes du CA
  désignées pour tenir le calendrier à jour.
- Toutes les données vivent dans une base Cloudflare D1, lues et écrites via un Worker Cloudflare — rien n'est
  stocké dans ce repo GitHub, qui ne sert qu'à héberger la page elle-même.

## Prochaine étape

Une page de consultation publique dédiée (`index.html`), plus soignée visuellement et sans le formulaire
d'administration, sera ajoutée à ce même repo une fois l'espace admin validé.

## Outils apparentés

Même patron technique (GitHub Pages + Worker Cloudflare + D1) que :
- MMM+ Agora — Dépannage accès
- Disponibilités des instructeurs (`mmminstlancer.moucheursmontrealmetro.ca`)

