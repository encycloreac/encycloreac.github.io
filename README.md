# Encyclo-Réac — site Jekyll

## Structure

```
_config.yml          réglages du site
Gemfile               dit à GitHub Pages quelle version de Jekyll utiliser
index.html            page d'accueil (texte de présentation uniquement)
_layouts/
  default.html         squelette HTML commun (head, CSS...)
  home.html             gabarit de la page d'accueil (génère le sommaire A-Z)
  entry.html            gabarit d'une fiche
_includes/
  letter-group.html     bloc réutilisable : liste les fiches d'une lettre
_entries/
  ciskei.md              une fiche = un fichier de données
assets/css/style.css   toute la mise en forme, au même endroit
```

## Ajouter une nouvelle fiche

1. Copier `_entries/ciskei.md`, renommer (ex: `_entries/orania.md`).
2. Remplacer les champs en haut du fichier (entre les `---`) par les
   infos de la nouvelle entrée.
3. Écrire le texte de la notice en dessous du deuxième `---`.
4. `git add`, `git commit`, `git push`.

Le sommaire de la page d'accueil se met à jour tout seul, sans rien
toucher d'autre : il regarde tous les fichiers dans `_entries/` et
les classe par lettre automatiquement.

## Modifier la mise en page

Tout changement dans `_layouts/entry.html` (ou `home.html`, ou le CSS)
s'applique instantanément à **toutes** les fiches, sans avoir à les
modifier une par une.
