---
name: cmonsite
description: Modifier un site CmonSite depuis Claude via le serveur MCP cmonsite — pages, sections, textes, images, liens et design, appliqués en direct dans l'éditeur CmonSite. À utiliser dès que l'utilisateur parle de son site CmonSite, de son éditeur, d'une page, d'une section ou du design de son site.
---

# CmonSite

Piloter le site CmonSite de l'utilisateur avec les outils du serveur MCP `cmonsite` (`https://www.cmonsite.fr/mcp`), déclaré dans ce plugin.

## Avant de commencer

1. Si les outils `cmonsite` ne sont pas disponibles, demander à l'utilisateur d'autoriser le connecteur CmonSite (connexion à son compte), puis réessayer.
2. Appeler `list_open_editors` :
   - un seul éditeur ouvert : il est utilisé d'office ;
   - plusieurs : demander à l'utilisateur lequel utiliser et passer son `editor_id` aux outils ;
   - aucun : lui demander d'ouvrir l'éditeur de son site et de cliquer sur le bouton de jumelage.
3. Avant toute modification, appeler `get_editing_guide` (règles), puis `get_page_outline` (état réel de la page).

## Règles de travail

- Répondre dans la langue de l'utilisateur.
- N'utiliser que les identifiants de widgets renvoyés par `get_page_outline` ; ne jamais en inventer.
- Pour créer ou styler du contenu, s'appuyer sur les outils de référence : `get_design_context` (identité visuelle), `get_design_rules` (design global), `list_patterns` puis `get_patterns` (sections modèles), `search_images`, `search_icons`, `search_fonts`. Ne jamais inventer un slug d'image, un chemin d'icône ou un nom de police.
- Liens internes : passer par `list_pages` ou `search_products` ; ne jamais inventer une URL.
- Autre page que celle affichée : `list_pages` ou `search_products`, puis `open_page`, et utiliser l'`editor_id` renvoyé.
- Image fournie par l'utilisateur : l'héberger avec `upload_image`. `generate_images` consomme les crédits du site : ne l'utiliser que si aucune photo de `search_images` ne convient, et le signaler.
- Chaque appel à `apply_operations` s'applique directement dans l'éditeur (un seul « annuler ») : résumer le changement prévu, l'appliquer, puis relire la page avec `get_page_outline` pour confirmer.
- Conserver le ton et la charte du site lors de la réécriture de textes, sauf demande contraire.
- Si un outil renvoie une erreur, l'expliquer simplement et proposer une alternative plutôt que de répéter la même action.
