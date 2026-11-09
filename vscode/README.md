# VS Code: профиль Web Development

Профиль `Web Development` создавался из **Empty Profile**, тогда как `Default` оставался резервом старой конфигурации. Экспорт исходного `Default` рекомендовалось сохранить отдельно.

## Что уже проверено

- Prettier форматирует `test.js` при сохранении, если есть конфигурация проекта.
- Расширение ESLint после `ESLint: Restart ESLint Server` показывает проблемы прямо в редакторе; `npm run lint` работает в терминале.
- Настроены задачи `Quality: ESLint` и `Quality: Prettier Check`, горячая клавиша `Ctrl + Option + L` для ESLint.
- Пользовательские сниппеты `clg` и `afn` проверены.
- Shell Integration в терминале VS Code имеет статус «Расширенная».
- Codex CLI найден; расширение `OpenAI.chatgpt` установлено в `Web Development`. Более глубокую настройку `AGENTS.md` пользователь отложил.

## Файлы в этой папке

- [web-development.settings.jsonc](web-development.settings.jsonc) — реконструкция **рекомендованного** профиля (не проверенный экспорт пользовательских настроек).
- [web-development.keybindings.json](web-development.keybindings.json) — проверенная пользовательская клавиша.
- [web-development.code-snippets](web-development.code-snippets) — шаблоны, по которым настраивали сниппеты.
- [extensions.md](extensions.md) — список расширений и команды установки.
- [project-tasks.md](project-tasks.md) — как устроены проектные Tasks.

## Где лежат настройки на практике

1. **Настройки профиля и сниппеты** — в данных VS Code и Settings Sync, не в папке каждого проекта.
2. **Конфигурации ESLint, Prettier, EditorConfig и Tasks** — в конкретных проектах и в `examples/vscode-web-lab`.
3. **Git и Zsh** — в `~/.gitconfig`, `~/.zshrc` и `~/.zprofile`.

Не включай глобальный Prettier для всех языков без разбора: для PHP/WordPress потребуется другой подход.

## Как получить настоящую резервную копию

В VS Code открой `Profiles` → выбери `Web Development` → `Export Profile` и сохрани файл `.code-profile`. **Этот файл пока не был предоставлен и не добавлен в репозиторий.** Перед публичным размещением проверь личные данные, пути и настройки расширений.

[Восстановление окружения](../SETUP.md)
