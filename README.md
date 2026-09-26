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

## Version anglaise (bilingue)

Le site gère maintenant deux langues :

```
index.html            page d'accueil française (racine du site)
en/index.html          page d'accueil anglaise (/en/)
_entries/               fiches françaises (ex: ciskei.md -> /ciskei/)
_entries_en/             fiches anglaises (ex: ciskei.md -> /en/ciskei/)
```

Chaque collection a son propre dossier, mais les deux utilisent le
même gabarit (`_layouts/entry.html`), qui affiche les libellés en
français ou en anglais selon la langue de la fiche (déterminée
automatiquement par `_config.yml` : tout ce qui est dans
`_entries_en/` reçoit `lang: en`).

### Ajouter la traduction d'une fiche existante

1. Copier `_entries_en/ciskei.md` (qui sert d'exemple), renommer avec
   le **même nom de fichier** que la version française
   (ex: `_entries_en/orania.md` pour traduire `_entries/orania.md`).
2. Traduire les champs et le texte.
3. `git add`, `git commit`, `git push`.

La fiche anglaise apparaît automatiquement dans le sommaire de
`/en/`, et le lien "English" en haut à droite de l'accueil français
mène vers `/en/`. Si une fiche n'a pas encore de traduction, elle
n'apparaît tout simplement pas dans le sommaire anglais — pas besoin
de traduire tout d'un coup.

## Modifier la mise en page

Tout changement dans `_layouts/entry.html` (ou `home.html`, ou le CSS)
s'applique instantanément à **toutes** les fiches, dans les deux
langues, sans avoir à les modifier une par une.

