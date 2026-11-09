# Zsh: терминал разработчика

На исходном Mac Zsh 5.9. `~/.zprofile` существовал, а `~/.zshrc` до начала работы отсутствовал. Добавили плагины без Oh My Zsh.

## Файлы

- [zprofile.example](zprofile.example): Homebrew, Python 3.14 и путь к Codex (в действительном `.zprofile` пути могут отличаться).
- [zshrc.example](zshrc.example): интерактивные опции, история, completion, Zsh-алиасы, prompt, fnm и плагины.

Оба файла — **безопасные примеры**, а не копии файлов с Mac. Не заменяй ими живые dotfiles без сравнения.

## Плагины

| Инструмент | Для чего |
| --- | --- |
| `zsh-autosuggestions` | Серое продолжение команды из истории; `→` для принятия |
| `zsh-syntax-highlighting` | Подсветка синтаксиса ввода |
| `fzf` | `Ctrl + R` — история, `Ctrl + T` — файлы, `Alt + C` — папки |
| `zoxide` | `z название` — переход в ранее посещённую папку |
| `vcs_info` | Git-ветка справа в prompt |
| `fnm` | Управление Node.js и переключение по `.node-version` |

**Порядок подключений важен:** сначала completion, затем fnm / fzf / zoxide / autosuggestions, подсветка синтаксиса — в конце.

## Проверка

```bash
zsh -n ~/.zshrc
# Открой новый терминал после редактирования.
alias gs
type z
fnm --version
fzf --version
setopt | grep -E 'interactivecomments|sharehistory'
```

Для теста zoxide:

```bash
cd ~/vscode-web-lab
cd ~
z vscode-web-lab
pwd
```

На исходном Mac этот тест сработал. Расширенная Shell Integration VS Code также подтверждена.

## Осторожность с историей

`HIST_IGNORE_SPACE` может исключать команды с ведущим пробелом из истории, но это **не средство защиты секретов**. Не передавай токены прямо в аргументах команд, если можно использовать более безопасную альтернативу, и не публикуй `~/.zsh_history`.

[Шпаргалка](../CHEATSHEET.md) · [Восстановление](../SETUP.md)
