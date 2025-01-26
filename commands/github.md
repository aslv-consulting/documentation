# Commandes Github cli

## Gestion des issues

### Créer une issue

```bash
gh issue create --assignee "{github_username}" --title "{issue_title}" --template "{issue_template}" --editor
```

### Lister les issues

```bash
gh issue list --json number,title,labels,state,updatedAt,comments --jq '.[] | select(.state == "OPEN") | {number: .number, labels: (if (.labels | length) == 0 then ["No Labels"] else [.labels[].name] end), title: .title, updatedAt: .updatedAt, comments_count: (.comments | length)} | [.number, (if (.labels | length) == 0 then "No Labels" else (.labels | join(", ")) end), .comments_count, .updatedAt, .title] | @tsv' | awk 'BEGIN {print "Number\tLabels\tComments\tUpdated\tTitle"} {print}' | column -t
```

### Visualiser une issue

```bash
gh issue view {issue_number}
```

### Editer une issue

```bash
gh issue edit {issue_number}
```

## Gestion des pull requests

### Créer une pull request

```bash
gh pr create --assignee "{github_username}" --base main --fill --editor
```

### Lister les pull requests

```bash
gh pr list --json number,title,state,updatedAt,comments --jq '.[] | select(.state == "OPEN") | {number: .number, title: .title, updatedAt: .updatedAt, comments_count: (.comments | length)} | [.number, .comments_count, .updatedAt, .title] | @tsv' | awk 'BEGIN {print "Number\tComments\tUpdated\tTitle"} {print}' | column -t
```

### Visualiser une pull request

```bash
gh pr view {pr_number}
```

### Visualiser les différences

```bash
gh pr diff {pr_number}
```

### Reviewer une pull request

```bash
gh pr review {pr_number} --comment -b "{message}"
```

### Approuver une pull request

```bash
gh pr review {pr_number} --approve
```

### Valider une pull request

```bash
gh pr merge {pr_number} --squash --delete-branch
```
