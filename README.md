# Dev Setup

Мой справочник и версионируемые **шаблоны** рабочего окружения разработчика на macOS (Apple Silicon): VS Code, Git, Zsh, Node.js, инструменты качества кода.

> Репозиторий публичный. Здесь только проверенные для публикации примеры и инструкции. **Это не автоматическая копия всех настроек Mac.** Реальные файлы `~/.zshrc`, `~/.zprofile`, `~/.gitconfig` и экспорт профиля VS Code ещё нужно сверить с примерами и добавить вручную после проверки секретов.

## Быстрый доступ

| Хочу… | Где смотреть |
| --- | --- |
| Вспомнить сокращения и хоткеи | [CHEATSHEET.md](CHEATSHEET.md) |
| Восстановить окружение на Mac | [SETUP.md](SETUP.md) |
| Понять конфигурацию терминала | [shell/zsh.md](shell/zsh.md) |
| Посмотреть Git-алиасы | [git/aliases.md](git/aliases.md) |
| Разобраться с VS Code и профилями | [vscode/README.md](vscode/README.md) |
| Увидеть эталон JavaScript-проекта | [examples/vscode-web-lab](examples/vscode-web-lab) |
| Посмотреть историю и дальнейшие планы | [CHANGELOG.md](CHANGELOG.md) |
| Безопасно публиковать конфигурации | [SECURITY.md](SECURITY.md) |

## Проверенное окружение на 9 ноября 2026 года

- **Mac:** macOS 15.7.1, ARM64 (Apple Silicon), Zsh 5.9.
- **Редактор:** VS Code 1.141.0; профиль `Web Development`.
- **Расширения:** Prettier, ESLint, EditorConfig, GitLens, vscode-icons, русский языковой пакет; позже установлен Codex (и автоматически сопутствующее Codex Audio). AI-инструменты описаны в [vscode/extensions.md](vscode/extensions.md).
- **Node:** 22.21.0, npm 10.9.4, `fnm` 1.39.0; исходный Node в `/usr/local/bin` оставлен в системе.
- **Git:** 2.51.1, основная ветка `main`, редактор `code --wait`, собственные алиасы.
- **Терминал:** Homebrew, fzf 0.75.0, zoxide 0.10.0, zsh-autosuggestions 0.7.1, zsh-syntax-highlighting 0.8.0; Git-ветка в prompt; Shell Integration VS Code — расширенная.
- **Python:** 3.14.3, установлен из Python.framework. **PHP и Composer** не обнаружены в PATH на момент аудита.

## Как всё хранится

- **Settings Sync** VS Code — синхронизация пользовательских настроек, профилей, расширений и сниппетов между VS Code. Это *не* Git-репозиторий.
- **Этот GitHub-репозиторий** — документация, версии шаблонов и пример проекта. Изменения сюда попадают после `git commit` + `git push`.
- **Домашние dotfiles** — остаются на Mac. Файлы `*.example` здесь нужно считать образцами, а не точной экспортированной копией.

## Поддержка репозитория

После изменения рабочих настроек: обновить соответствующий пример и шпаргалку, затем добавить запись в [CHANGELOG.md](CHANGELOG.md).

```bash
git status
git diff
git add .
git diff --cached
git commit -m "docs: update development setup"
git push
```

**Перед каждой публикацией** проверь изменения и секреты — см. [SECURITY.md](SECURITY.md). Не запускай копирование шаблонов поверх живых файлов конфигурации без сравнения.
