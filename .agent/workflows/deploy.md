---
description: Deploy all local changes to GitHub and trigger a Vercel deployment
---

# Deploy Workflow

// turbo-all

1. Check what changed (Проверка измененных файлов):
```bash
git status
```

2. Stage all changes (Подготовка файлов к коммиту):
```bash
git add -A
```

3. Verify build stability locally (Локальная проверка сборки, чтобы избежать ошибок на сервере):
```bash
npm run build
```

4. Commit with a descriptive message (Создание коммита с описанием изменений):
```bash
git commit -m "deploy: update content and UI"
```

5. Push to GitHub (Отправка изменений в репозиторий, после чего Vercel начнет деплой автоматически):
```bash
git push
```

6. Confirm push was successful and inform the user that Vercel will start deploying automatically within ~1 minute.
(Подтверждение успешного пуша и уведомление о начале деплоя на Vercel).

7. (Optional/Опционально) Check deployment status using Vercel tools if available.
(Проверка статуса деплоя через инструменты Vercel).
