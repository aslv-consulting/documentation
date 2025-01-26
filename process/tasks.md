# Gestion des tâches

## Créer une branche a partir de la tâche

```bash
gh issue develop {task_number} --checkout
```

## Message des commits

Nous ne voulons qu'un seul commit par tâche. Pour cela, nous allons utiliser le rebase.

Le commit doit être sous cette forme:

```
{task_type}(#{issue_number}): {task_title}

Liste des modifications ex:
- Ajout de la fonctionnalité X
- Modification de la fonction Y

Closes #{issue_number}
```

Le `{task_type}` peut être:

- `feat` pour une nouvelle fonctionnalité
- `fix` pour une correction de bug
- `refactor` pour une refonte de code
- `style` pour une modification de style
- `docs` pour une modification de documentation
- `test` pour une modification de test
- `chore` pour une modification de configuration

## Commiter vos modifications

```bash
# Voir la liste des fichiers modifiés
git status

# Ajout des fichiers pour le commit
git add .

# Premier commit
git commit

# Autre commit
git commit -a --amend
```

## Sauvegarde des commits

Il faut sauvegarder vos commits chaque jour (Fini ou pas).

```bash
# Premier push
git push -u origin {branch_name}

# Autre push
git push -u origin {branch_name} --force
```

## Création d'une PR

```bash
gh pr create --assignee "{github_username}" --base main --fill --editor
```

## Visualisation d'une PR

```bash
gh pr view {pr_number}
```

## Visualisation des différences

```bash
gh pr diff {pr_number}
```

## Reviewer une PR

```bash
gh pr review {pr_number} --comment -b "{message}"
```

## Approuver une PR

```bash
gh pr review {pr_number} --approve
```

## Valider une PR

```bash
gh pr merge {pr_number} --squash --delete-branch
```

## Cloturer les stories / epics

Quand toutes les tâches d'une story ou d'une epic sont terminées, il faut la clôturer.

```bash
gh issue close {issue_number}
```
