# Raccourcis Neovim

Tous les raccourcis clavier pour Neovim doivent se faire en mode commande.

## Navigation

- `gg` : Déplacement au début du fichier
- `G` : Déplacement à la fin du fichier
- `Ctrl + u` : Déplacement d'une page vers le haut
- `Ctrl + d` : Déplacement d'une page vers le bas
- `0` : Déplacement au début de la ligne
- `$` : Déplacement à la fin de la ligne
- `w` : Déplacement d'un mot vers la droite
- `b` : Déplacement d'un mot vers la gauche
- `f espace` : aller à la prochaine occurence de l'espace
- `F espace` : aller à la précédente occurence de l'espace

## Recherche

- `nohlsearch` : Désactiver la recherche

## Regex

### Supprimer toutes les lignes de commentaires

```vim
:g/^#/d
```

- :g : Exécute une commande sur toutes les lignes correspondant à un motif.
- /^#/ : Motif de recherche pour les lignes commençant par `#`.
- d : Supprime les lignes correspondant au motif.

### Supprimer tous les lignes vides

```vim
:g/^$/d
```

- :g : Exécute une commande sur toutes les lignes correspondant à un motif.
- /^$/ : Motif de recherche pour les lignes vides.
- d : Supprime les lignes correspondant au motif.

## Plugins

### Marckdown Preview

- `:MP` : Ouvrir la prévisualisation du fichier markdown
