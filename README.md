# MetaRoK Optimizer — V1 export

## Tester en local
1. Décompresser l'archive.
2. Ouvrir un terminal dans le dossier.
3. Lancer un serveur statique, par exemple :
   - Python : `python -m http.server 8000`
   - puis ouvrir `http://localhost:8000`

L'ouverture directe de `index.html` peut être bloquée par le navigateur car le fichier JSON est chargé en module.

## Déployer
Le dossier peut être publié sur Netlify, Cloudflare Pages ou GitHub Pages (site statique).
Aucun compte d'hébergement n'est connecté depuis cette conversation : cette archive n'est donc pas encore publiée sur une URL publique.

## Synchronisation MetaRoK
`data/marches.json` est une graine initiale relevée sur la page publique Meta Marches le 8 novembre 2026. Elle reprend les compositions visibles pour 5, 6 et 7 marches.
Elle n'inclut PAS la totalité des 38 entrées de la tierlist Open Field, les tiers, la jouabilité ni toutes les données de gear. Les champs sont explicitement marqués « À synchroniser » pour ne pas présenter ces informations comme vérifiées.

Pour une synchronisation automatique fiable, prévoir un service serveur (pas uniquement du JavaScript dans le navigateur) :
- récupérer la page MetaRoK et les pages de tierlist Open Field ;
- parser les compositions, tiers, rangs, types de troupes, recommandations de gear et jouabilité ;
- valider le schéma et détecter les changements ;
- conserver la dernière version valide et un historique ;
- ne publier une nouvelle version qu'après validation ;
- afficher la date du dernier succès et une alerte en cas d'échec.

Avant d'activer un robot de collecte régulier, vérifier les conditions d'utilisation, robots.txt et obtenir l'autorisation de MetaRoK si nécessaire. Une API ou un flux de données officiel serait préférable au scraping.

## Limites fonctionnelles de cette V1
- Inventaire par sets complets et qualité globale manuelle.
- Sélection/désélection des commandants.
- Liste initiale des marches 5/6/7 visibles sur MetaRoK.
- Calcul indicatif, non fondé sur un simulateur de dégâts.
- Pas de comptes utilisateurs ni de synchronisation automatique implémentée.
- Les scores et la liste exhaustive doivent être calibrés/complétés avant usage compétitif.

## Source de référence
https://meta-rok.com/marches/
https://meta-rok.com/tierlist/field/
