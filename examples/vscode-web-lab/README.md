# VS Code Web Lab

Исходный учебный проект, который раньше лежал в корне `dev-setup`. Все первоначально опубликованные файлы перенесены сюда с сохранением содержимого: `test.js`, `package.json`, `package-lock.json`, `eslint.config.mjs`, `.prettierrc.json`, `.prettierignore`, `.node-version` и `.vscode/tasks.json`.

Дополнительно добавлен `.editorconfig` по конфигурации из нашего урока (этого файла не было в исходном GitHub-дереве).

## Запуск

```bash
cd examples/vscode-web-lab
fnm use 22.21.0
npm ci
npm run lint
npm run format:check
```

Задачи VS Code: `Quality: ESLint` и `Quality: Prettier Check`. Это **пример для обучения**, а не универсальные правила для WordPress, React и Next.js.

## Замечание по зависимостям

9 ноября 2026 года `npm audit` показывал **4 moderate** предупреждения в дереве devDependencies ESLint 10.14.0 (через minimatch 10.2.6), а `npm audit --omit=dev` — **0**. Версии в lock-файле намеренно сохранены из исходного проекта. Перед работой запусти актуальный аудит и не применяй `npm audit fix --force` без проверки совместимости.

[К главной](../../README.md)
