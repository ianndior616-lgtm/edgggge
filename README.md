# EdGGe — Dota 2 Teammate Finder

Telegram Mini App на Next.js + PostgreSQL/Drizzle. Визуал не менялся.

## Важно для GitHub

В корне репозитория обязательно должны лежать `package.json`, `next.config.ts`, `tsconfig.json` и папка `src/`.
Next.js приложение находится в `src/app/`. Если `src/` не загружена, `next build` падает с `Couldn't find any pages or app directory`.

## Обязательные env

```env
DATABASE_URL=...
TELEGRAM_BOT_TOKEN=...
TELEGRAM_BOT_USERNAME=...
NEXT_PUBLIC_TELEGRAM_BOT_USERNAME=...
TELEGRAM_WEBHOOK_SECRET=...
APP_URL=https://...
ADMIN_TG_IDS=123456789
BOT_SETUP_SECRET=...
```

Если панель деплоя требует заполнить необязательные поля, используй:

```env
ADMIN_ACCESS_CODE=disabled
OPENDOTA_API_KEY=disabled
STEAM_WEB_API_KEY=disabled
```

В этой сборке слово `disabled` специально трактуется как отсутствие значения.

## Автоподгрузка Dota

Поддерживаются Dotabuff, STRATZ, OpenDota и Steam numeric profile. Публичные данные загружаются через OpenDota. Steam vanity `/id/name` работает только с настоящим `STEAM_WEB_API_KEY`.

## Локально

```bash
npm install
npm run db:push
npm run dev
```

## Перед деплоем

Проверь, что в GitHub видна папка `src`, а внутри `src/app/page.tsx` и `src/app/layout.tsx`.
