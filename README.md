# CmonSite pour Claude

Ce plugin connecte Claude à l'éditeur de votre site [CmonSite](https://www.cmonsite.fr). Décrivez ce que vous voulez en langage naturel : Claude modifie vos pages, ajoute des sections, réécrit vos textes, insère des images, des icônes ou des liens et ajuste le design. Chaque modification s'applique en direct dans l'éditeur ouvert dans votre navigateur et s'annule en un clic.

## Prérequis

- Un site CmonSite et un accès à son éditeur.
- Un compte Claude permettant d'utiliser des plugins ou des connecteurs.

## Installation et connexion

1. Installez le plugin `cmonsite`.
2. À la première utilisation, Claude vous demande d'autoriser l'accès à votre compte CmonSite (connexion OAuth sur cmonsite.fr). Vous pouvez révoquer cet accès à tout moment depuis la rubrique « Applications connectées » de votre administration CmonSite.
3. Ouvrez l'éditeur de votre site et cliquez sur le bouton de jumelage pour que Claude puisse travailler sur la page affichée.

## Exemples de demandes

- « Réécris le texte de présentation de ma page d'accueil sur un ton plus chaleureux. »
- « Ajoute une section témoignages sous la bannière. »
- « Mets en avant mes trois produits les plus récents sur la page Boutique. »
- « Harmonise les couleurs des boutons avec celles de mon logo. »

## Contenu du plugin

- `.mcp.json` : déclare le serveur MCP distant de CmonSite.
- `skills/cmonsite/SKILL.md` : consignes de travail de Claude sur votre site.

## Données et services contactés

Ce plugin ne contient aucun code exécuté sur votre ordinateur. Il contacte un seul service : le serveur MCP de CmonSite, `https://www.cmonsite.fr/mcp`, hébergé et exploité par CmonSite (LORD OF WEB SARL).

Les échanges avec ce serveur contiennent :

- vos demandes de lecture et de modification (structure et contenu des pages, réglages de design, liste des pages et des produits) ;
- les images que vous demandez d'héberger sur votre site ;
- les recherches d'images, d'icônes et de polices, ainsi que les demandes de génération d'images par IA, qui consomment les crédits de votre site.

L'accès est limité au compte CmonSite que vous avez autorisé. Aucune donnée n'est envoyée à un autre service par ce plugin.

Politique de confidentialité : [cmonsite.fr/politique_confidentialite.php](https://www.cmonsite.fr/politique_confidentialite.php)

## Support

Pour toute question, contactez le support CmonSite depuis votre espace client sur [cmonsite.fr](https://www.cmonsite.fr).

## Licence

MIT, voir [LICENSE](LICENSE).
