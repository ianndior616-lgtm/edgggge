# Changes in this build

- Visual design left unchanged.
- Rewritten README to match the code that actually exists.
- Removed the hard-coded default admin password.
- Added multiple admins via `ADMIN_TG_IDS=id1,id2,id3`.
- Added `.env.example` without real secrets.
- Drizzle config now reads `DATABASE_URL` instead of a hard-coded local database.
- Added automatic Dota profile lookup from DotaBuff / STRATZ / OpenDota / Steam profile URLs.
- Added optional Steam vanity resolution through `STEAM_WEB_API_KEY`.
- Added OpenDota sync (nickname, avatar, rank, leaderboard, MMR estimate, W/L, top heroes).
- Dota sync data is stored in PostgreSQL and refreshed at most once per 6 hours for the same saved link.
- Existing form auto-fills nickname/MMR/avatar only when the user has not manually overridden them.
- Added optional `BOT_SETUP_SECRET` protection for `/api/bot/setup`.
- Added `db:push` and `db:generate` npm scripts.

After updating an existing database run:

```bash
npm install
npm run db:push
```
