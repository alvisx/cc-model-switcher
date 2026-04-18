# cc-model — переключатель моделей для Claude Code

CLI-утилита для переключения между моделями в Claude Code. Меняет модель, API-эндпоинт и токен авторизации в `~/.claude/settings.json`.

## Установка

```bash
ln -s /path/to/cc-model-swither/cc-model /usr/local/bin/cc-model
```

## Использование

```bash
cc-model switch opus    # Claude Opus 4.7
cc-model switch glm     # GLM 5.1 (ZhipuAI)
cc-model status         # текущая модель
cc-model list           # список профилей
```

После переключения перезапусти сессию Claude Code.

## Конфигурация

Профили хранятся в `~/.cc-model/profiles.json` (вне репозитория). Шаблон — `profiles.example.json`.

```bash
mkdir -p ~/.cc-model
cp profiles.example.json ~/.cc-model/profiles.json
# Отредактируй ~/.cc-model/profiles.json — укажи свои токены
```

## Добавление нового профиля

Добавь запись в `~/.cc-model/profiles.json`:

```json
"имя-профиля": {
  "model": "model-id",
  "env": {
    "ANTHROPIC_AUTH_TOKEN": "токен",
    "ANTHROPIC_BASE_URL": "https://..."
  }
}
```

Если модель использует стандартный Anthropic API — оставь `"env": {}`.
