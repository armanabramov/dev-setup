# VS Code Tasks и проверка качества

Эталон из [тестового проекта](../examples/vscode-web-lab/.vscode/tasks.json).

| Задача | Команда npm |
| --- | --- |
| `Quality: ESLint` | `npm run lint` |
| `Quality: Prettier Check` | `npm run format:check` |

Запуск: `Cmd + Shift + P` → `Tasks: Run Task` → нужная задача. Для `Quality: ESLint` настроено `Ctrl + Option + L`.

**Привязка зависит от рабочего проекта:** если задачи с таким именем нет в `.vscode/tasks.json` текущего workspace, горячая клавиша не сможет её запустить. Настройки проекта не обязаны совпадать с этим примером.

`problemMatcher: []` оставлен пустым для простого первого теста. Такой Task показывает вывод в терминале, но не парсит его автоматически в панель `Problems`. Для подсветки ESLint в файлах используется отдельное расширение ESLint и его language server.

**Проверенные npm-скрипты:**

```json
{
  "scripts": {
    "lint": "eslint .",
    "lint:fix": "eslint . --fix",
    "format": "prettier . --write",
    "format:check": "prettier . --check"
  }
}
```

Prettier запускается из зависимостей проекта; `prettier.requireConfig=true` не форматирует файл без проектной конфигурации. Для WordPress/PHP вместо JS-only правил потребуется отдельная настройка.

[Горячие клавиши](../CHEATSHEET.md)
