# Mon Frigo

Application web en français pour suggérer des recettes en fonction des ingrédients disponibles.

## Fonctionnalités
- Saisie de plusieurs aliments, alias français/anglais pour les aliments courants.
- Catalogue TheMealDB chargé par initiales, trois requêtes simultanées, cache local de 24 heures. Le nombre réel chargé est affiché ; aucun volume minimum garanti.
- Classement selon la proportion d'ingrédients disponibles, liste des ingrédients manquants, filtres et favoris.
- Liste de courses locale, copie dans le presse-papiers.
- Interface responsive, aucune clé privée, aucun serveur applicatif.

## Limites importantes
Les titres, catégories et instructions de TheMealDB restent dans la langue d'origine (souvent l'anglais). Les traductions d'ingrédients reposent sur un dictionnaire limité, pas une traduction automatique complète. Les correspondances ne vérifient ni quantités, ni allergies, ni substitutions. Eau, sel et poivre sont supposés disponibles. Les recettes proposées peuvent nécessiter des achats. Le catalogue dépend de l'API externe et n'est pas une base exhaustive embarquée. Les ingrédients, favoris, courses et le cache restent dans localStorage, sans synchronisation entre appareils. Les requêtes et images sont téléchargées depuis TheMealDB ; ce service reçoit donc les informations de connexion usuelles du navigateur.

## Déploiement
Le workflow GitHub Actions tente d'activer et de déployer GitHub Pages à chaque push sur main. Si l'activation automatique est refusée par GitHub, un administrateur doit sélectionner Settings > Pages > Source > GitHub Actions, puis relancer le workflow. L'URL prévue est https://samaftersam.github.io/mon-frigo-recettes/ ; elle n'est accessible qu'après un déploiement réussi.

## Développement
Servir index.html avec un serveur HTTP statique (par exemple python -m http.server). Aucun build ni dépendance npm.

## Source des données
https://www.themealdb.com/api.php — recettes et images TheMealDB, service externe soumis à ses propres conditions. La clé de test publique 1 est utilisée pour cette application personnelle expérimentale ; vérifier les conditions et les besoins de licence avant un usage commercial ou une distribution plus large.
