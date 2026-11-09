# Расширения профиля Web Development

Установленный базовый список подтверждён выводом `code --list-extensions --profile "Web Development"`.

| Расширение (ID) | Назначение |
| --- | --- |
| `esbenp.prettier-vscode` | Форматирование |
| `dbaeumer.vscode-eslint` | Линтинг JS/TS |
| `editorconfig.editorconfig` | Базовые правила текстовых файлов |
| `eamodio.gitlens` | История и контекст Git |
| `vscode-icons-team.vscode-icons` | Тема иконок |
| `ms-ceintl.vscode-language-pack-ru` | Русский интерфейс VS Code |
| `OpenAI.chatgpt` | Codex, установлен позже |
| `openai.codex-audio` | Сопутствующее расширение, поставленное вместе с Codex |

GitHub Copilot Free пользователь тестировал и подтвердил работу подсказок, но точный ID расширения в обновлённом списке не проверяли; поэтому не выдаём его за зафиксированный экспорт.

## Установить в существующий профиль

```bash
code --install-extension esbenp.prettier-vscode --profile "Web Development"
code --install-extension dbaeumer.vscode-eslint --profile "Web Development"
code --install-extension editorconfig.editorconfig --profile "Web Development"
code --install-extension eamodio.gitlens --profile "Web Development"
code --install-extension vscode-icons-team.vscode-icons --profile "Web Development"
code --install-extension ms-ceintl.vscode-language-pack-ru --profile "Web Development"
code --install-extension OpenAI.chatgpt --profile "Web Development"
```

`openai.codex-audio` может установиться автоматически. Для работы Codex нужно отдельно войти в аккаунт ChatGPT; подписка ChatGPT Plus не заменяет тариф Copilot и не включает оплату внешнего API.

## Проверить

```bash
code --list-extensions --show-versions --profile "Web Development"
```

## Что намеренно не перенесли

Из исходного `Default`: Intelephense/PHP, Python, Live Server, Sass Compiler, Git Graph, дополнительные HTML/CSS-подсказки, Figma и др. Эти расширения можно постепенно распределить по будущим профилям **WordPress/PHP**, **Python**, **Experimental**. Полный актуальный экспорт Default с Mac сюда пока не загружен.

[О профиле](README.md)
