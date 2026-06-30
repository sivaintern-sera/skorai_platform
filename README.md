# skorai_platform

Skorai Platform starter with Neon Postgres and Prisma.

## Stack

- Neon Postgres
- Prisma ORM
- TypeScript

## Setup

1. Install dependencies:

   ```bash
   npm install
   ```

2. Copy the environment template:

   ```bash
   cp .env.example .env
   ```

3. Add your Neon connection strings to `.env`:

   - `DATABASE_URL`: pooled Neon connection string for app runtime
   - `DIRECT_URL`: direct Neon connection string for Prisma migrations

4. Generate the Prisma client:

   ```bash
   npm run db:generate
   ```

5. Create and apply the first migration:

   ```bash
   npm run db:migrate
   ```

## Database Scripts

- `npm run db:generate` - generate Prisma Client
- `npm run db:migrate` - create/apply local development migrations
- `npm run db:deploy` - apply migrations in production
- `npm run db:studio` - open Prisma Studio
- `npm run db:push` - sync schema without creating a migration

## Project Layout

```text
prisma/schema.prisma   Prisma data model
prisma.config.ts       Prisma datasource and migration config
src/db.ts              Shared Prisma client using Neon adapter
.env.example           Neon environment variable template
```

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
