# Git-алиасы: что настроено и зачем

## Встроенные в Git

| Команда | Выполняет |
| --- | --- |
| `git st` | `status --short --branch` |
| `git br` | `branch` |
| `git sw develop` | `switch develop` |
| `git new feature/x` | `switch -c feature/x` |
| `git lg` | `log --graph --oneline --decorate --all -20` |
| `git last` | `log -1 --stat` |
| `git df` | `diff` |
| `git ds` | `diff --staged` |
| `git unstage file` | `restore --staged file` |
| `git ci -m "msg"` | `commit -m "msg"` |
| `git root` | `rev-parse --show-toplevel` |

## Zsh-алиасы поверх Git

`g` → `git`, `gs` → `git st`, `ga` → `git add`, `gc` → `git ci`, `gl` → `git lg`, `gd` → `git df`, `gds` → `git ds`, `gsw` → `git sw`, `gb` → `git br`.

Сами Zsh-сокращения хранятся в [shell/zshrc.example](../shell/zshrc.example). Git-алиасы — в `~/.gitconfig`.

## Как восстановить, не переписывая живой .gitconfig

Выполни после проверки существующих значений:

```bash
git config --global init.defaultBranch main
git config --global core.editor 'code --wait'
git config --global alias.st 'status --short --branch'
git config --global alias.br 'branch'
git config --global alias.sw 'switch'
git config --global alias.new 'switch -c'
git config --global alias.lg 'log --graph --oneline --decorate --all -20'
git config --global alias.last 'log -1 --stat'
git config --global alias.df 'diff'
git config --global alias.ds 'diff --staged'
git config --global alias.unstage 'restore --staged'
git config --global alias.ci 'commit'
git config --global alias.root 'rev-parse --show-toplevel'
```

Проверка:

```bash
git config --global --get-regexp '^alias\.'
git config --global --get core.editor
```

Не создавали опасных сокращений для удаления изменений, force push и переписывания истории. Перед коммитом всегда полезно посмотреть `git status` и `git diff --cached`.

[К шпаргалке](../CHEATSHEET.md)
