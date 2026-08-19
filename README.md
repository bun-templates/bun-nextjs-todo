# Bun + Next.js Todo

A full-stack todo application built with [Bun](https://bun.com), [Next.js](https://nextjs.org), and PostgreSQL.

## Quick Start

```bash
# Install dependencies
bun install

# Set up database (copy .env.example and add your DATABASE_URL)
cp .env.example .env.local

# Seed the database
bun run db:seed

# Start development server
bun dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Prerequisites

- [Bun](https://bun.com/docs/installation) installed
- PostgreSQL database (local or cloud)

### Database Setup

You need a PostgreSQL database. You can use:
- **Local**: Install PostgreSQL and create a database
- **Cloud**: [Neon](https://neon.tech), [Supabase](https://supabase.com), [Railway](https://railway.com), or [Vercel Postgres](https://vercel.com/docs/storage/vercel-postgres)

Add your connection string to `.env.local`:

```bash
DATABASE_URL="postgresql://username:password@hostname:port/database"
```

**Local PostgreSQL (Docker, any OS):**
```bash
docker compose up -d
```

Then add to `.env.local`:
```bash
DATABASE_URL="postgres://postgres:postgres@localhost:5432/todo"
```

Set `POSTGRES_PORT` before `docker compose up` if port 5432 is already taken on your machine.

**Local PostgreSQL (macOS, Homebrew):**
```bash
brew install postgresql
brew services start postgresql
createdb mydb
```

Then add to `.env.local`:
```bash
DATABASE_URL="postgresql://$(whoami)@localhost:5432/mydb"
```

## Tech Stack

- **Runtime**: [Bun](https://bun.com)
- **Framework**: [Next.js](https://nextjs.org)
- **Database**: PostgreSQL (via Bun's native SQL API)
- **UI**: [ShadCN](https://ui.shadcn.com/) + [Tailwind CSS](https://tailwindcss.com/)
- **Validation**: [Zod](https://zod.dev/)

## Scripts

- `bun dev` - Start development server
- `bun build` - Build for production
- `bun start` - Start production server
- `bun run db:seed` - Seed the database (creates table and sample data)
- `bun run lint` - Run Biome linter
- `bun run format` - Format code with Biome

## Deployment

For deployment instructions and hosting options, see Bun's [deployment guides](https://bun.com/docs/guides/deployment/vercel).
