# Восстановление рабочего окружения на macOS

Инструкция основана на настройке **Mac Apple Silicon + Zsh 5.9**. Не все команды подходят для Windows/Linux. Проверяй доступность версий и совместимость проектов перед установкой.

## 0. Клонировать репозиторий

```bash
git clone https://github.com/armanabramov/dev-setup.git
cd dev-setup
```

Перед любыми изменениями существующего Mac сохрани резервные копии: `~/.zshrc`, `~/.zprofile`, `~/.gitconfig` и экспорт профиля VS Code. **Никогда не копируй шаблоны поверх живых файлов без сравнения.**

## 1. Homebrew и инструменты Zsh

Установи Homebrew по официальной инструкции: https://brew.sh/ . После установки убедись, что `brew --prefix` указывает на корректный каталог (на исходном Mac — `/opt/homebrew`).

```bash
brew bundle --file Brewfile
```

`Brewfile` включает только пять проверенных нами утилит: `zsh-autosuggestions`, `zsh-syntax-highlighting`, `fzf`, `zoxide`, `fnm`. Это не полный экспорт всех Homebrew-пакетов исходного Mac.

Сравни [shell/zprofile.example](shell/zprofile.example) с `~/.zprofile` (там могут быть Python и Codex). Сравни [shell/zshrc.example](shell/zshrc.example) с `~/.zshrc` и перенеси нужные блоки вручную. После изменений:

```bash
zsh -n ~/.zshrc
# Затем открой новый терминал
```

Проверь `alias gs`, `type z`, `fnm --version`, поиск `Ctrl + R` и автоподсказки.

## 2. Git

Пример глобальных настроек: [git/gitconfig.example](git/gitconfig.example). Он **не содержит** имени и e-mail автора коммитов.

Не перезаписывай `~/.gitconfig` целиком. Для воссоздания алиасов используй команды из [git/aliases.md](git/aliases.md). Проверь:

```bash
git --version
git config --global --get-regexp '^alias\.'
git config --global --get core.editor
```

Редактор Git на исходном Mac — `code --wait`; для него требуется команда `code` в PATH.

## 3. Node.js / fnm

При наличии инициализации fnm в `.zshrc`:

```bash
fnm install 22.21.0
fnm default 22.21.0
fnm use 22.21.0
fnm current
node -p "process.execPath"
```

В каждом проекте используй свой `.node-version`. Не удаляй старую системную установку Node, пока не убедишься, что все глобальные CLI и проекты работают. Глобальный `json-server` был в старой установке Node; в новой установке fnm на момент проверки оставались `npm` и `corepack`.

## 4. VS Code

1. Установи VS Code и добавь команду `code` в PATH через `Shell Command: Install 'code' command in PATH`.
2. Включи **Settings Sync**, если хочешь синхронизировать профили, настройки, расширения и сниппеты. Это не синхронизация в данный репозиторий.
3. Создай профиль `Web Development`; установи расширения по [vscode/extensions.md](vscode/extensions.md).
4. Примени настройки по образцу [vscode/web-development.settings.jsonc](vscode/web-development.settings.jsonc), сверь горячие клавиши и сниппеты из папки `vscode/`.
5. Проверь `chat.disableAIFeatures` (не должен отключать нужные AI-функции) и открывай только **доверенные** собственные проекты.

**Экспорт рабочего профиля с исходного Mac ещё не добавлен.** Пример в репозитории восстановлен из наших шагов, не является байт-в-байт копией живого профиля.

## 5. Тестовый проект ESLint / Prettier

```bash
cd examples/vscode-web-lab
fnm use 22.21.0
npm ci
npm run lint
npm run format:check
```

Конфигурация `examples/vscode-web-lab/.vscode/tasks.json` даёт задачи `Quality: ESLint` и `Quality: Prettier Check`. Горячая клавиша для первой — `Ctrl + Option + L`.

**Предупреждение по безопасности:** в аудите 09.11.2026 были 4 замечания уровня moderate в зависимостях разработки (minimatch через ESLint 10.14.0), при `npm audit --omit=dev` — 0. Проверь актуальный `npm audit` после установки; не применяй `npm audit fix --force` вслепую.

## 6. Python, PHP, Codex

На исходном Mac Python 3.14.3 добавлен в `PATH` через `~/.zprofile`; `uv` ещё не установлен. PHP и Composer не обнаружены в PATH (возможно, существуют только в локальном серверном окружении). Отдельные профили WordPress и Python пока не настроены.

Codex CLI ранее был установлен; затем добавлено расширение `OpenAI.chatgpt` в VS Code. Правила `AGENTS.md` и `~/.codex/config.toml` в этом этапе **не создавались** и не публиковались.

## 7. После восстановления

```bash
git status
git st
alias gs
type z
fnm current
node --version
code --version
```

При изменении настроек обнови соответствующие шаблоны, [CHEATSHEET.md](CHEATSHEET.md) и [CHANGELOG.md](CHANGELOG.md), проверь `git diff` и только затем отправляй изменения в GitHub.

[На главную](README.md)
