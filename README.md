<div align="center">

<img src="https://trymark1.vercel.app/logo.svg" alt="Mark1 Logo" width="80" />

# Mark1

**Build apps and websites by just chatting.**

[![Live Demo](https://img.shields.io/badge/Live%20Demo-trymark1.vercel.app-6366f1?style=for-the-badge&logo=vercel&logoColor=white)](https://trymark1.vercel.app/)
[![Next.js](https://img.shields.io/badge/Next.js-16-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![License](https://img.shields.io/badge/license-MIT-22c55e?style=for-the-badge)](./LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-f97316?style=for-the-badge)](https://github.com/Vaibhav0-07/mark1main/pulls)

</div>

---

## ✨ What is Mark1?

Mark1 is an AI-powered app and website builder — describe what you want to build, and Mark1 generates it for you. Think of it as your personal full-stack engineer that speaks plain English.

> *"Build a Netflix clone"* → Mark1 builds it.  
> *"Build a Spotify clone"* → Mark1 builds it.  
> *Describe your own idea* → Mark1 builds it.

---

## 🎥 Demo

Visit **[trymark1.vercel.app](https://trymark1.vercel.app/)** to try it live.

Some things you can ask Mark1 to build:

| Prompt | What you get |
|--------|-------------|
| 🎬 Build a Netflix clone | Streaming-style UI with browse/detail pages |
| 📦 Build an admin dashboard | Charts, tables, sidebar nav |
| 📋 Build a kanban board | Drag-and-drop columns and cards |
| 🗂️ Build a file manager | File tree, upload, preview |
| 📺 Build a YouTube clone | Video grid, player, search |
| 🛍️ Build a store page | Product cards, cart, checkout flow |
| 🏡 Build an Airbnb clone | Listings, filters, booking UI |
| 🎵 Build a Spotify clone | Music player, playlists, artists |

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Framework** | [Next.js 16](https://nextjs.org/) + React 19 |
| **Auth** | [Clerk](https://clerk.com/) |
| **Database** | PostgreSQL + [Prisma ORM](https://www.prisma.io/) |
| **AI Orchestration** | [Inngest](https://www.inngest.com/) + [Agent Kit](https://www.inngest.com/docs/agent-kit/overview) |
| **Code Sandbox** | [E2B Code Interpreter](https://e2b.dev/) |
| **UI Components** | [shadcn/ui](https://ui.shadcn.com/) + [Radix UI](https://www.radix-ui.com/) |
| **Styling** | [Tailwind CSS v4](https://tailwindcss.com/) |
| **Data Fetching** | [TanStack React Query](https://tanstack.com/query) |
| **Charts** | [Recharts](https://recharts.org/) |
| **Validation** | [Zod](https://zod.dev/) |
| **Infra** | [Vercel](https://vercel.com/) + Docker (local DB) |

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- Docker (for local PostgreSQL)
- Accounts for: [Clerk](https://clerk.com/), [Inngest](https://inngest.com/), [E2B](https://e2b.dev/)

### 1. Clone the repo

```bash
git clone https://github.com/Vaibhav0-07/mark1main.git
cd mark1main
```

### 2. Install dependencies

```bash
npm install
```

### 3. Set up environment variables

Create a `.env.local` file in the root:

```env
# Clerk Auth
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up

# Database (Docker Postgres)
DATABASE_URL=postgresql://postgres:password@localhost:5432/mark1

# Inngest
INNGEST_EVENT_KEY=
INNGEST_SIGNING_KEY=

# E2B Code Interpreter
E2B_API_KEY=

# AI Model
ANTHROPIC_API_KEY=
# or
OPENAI_API_KEY=
```

### 4. Start the database

```bash
docker compose up -d
```

### 5. Push the Prisma schema

```bash
npx prisma db push
```

### 6. Run the dev server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) and start building! 🎉

---

## 📁 Project Structure

```
mark1main/
├── prisma/                  # Database schema & migrations
├── public/                  # Static assets (logo, icons)
├── src/
│   ├── app/                 # Next.js App Router pages
│   │   ├── (auth)/          # Sign-in / sign-up pages
│   │   ├── api/             # API routes & Inngest functions
│   │   └── project/         # Project workspace
│   ├── components/          # Reusable UI components
│   ├── lib/                 # Utilities, Prisma client, helpers
│   └── hooks/               # Custom React hooks
├── sandbox-templates/       # E2B sandbox configurations
├── docker-compose.yml       # Local PostgreSQL setup
└── package.json
```

---

## 🗺️ Roadmap & Open TODOs

These are real features we want to build. **PRs for any of these are very welcome!**

### 🧠 AI & Core Features
- [ ] **Multi-model support** — let users choose between GPT-4o, Claude, Gemini, etc.
- [ ] **Streaming generation** — show code as it's written, not all at once
- [ ] **Context memory** — remember user preferences and past decisions across sessions
- [ ] **Prompt templates** — pre-built starting prompts with variables (e.g. "Build a {type} app for {industry}")
- [ ] **Error recovery** — automatically detect and fix broken generated code

### 🖥️ Editor & Workspace
- [ ] **In-browser code editor** — view and edit generated files with syntax highlighting (Monaco/CodeMirror)
- [ ] **Live preview** — side-by-side preview of the running app alongside the chat
- [ ] **File tree sidebar** — browse the full generated project structure
- [ ] **Dark/light theme toggle** for the workspace
- [ ] **Split pane resizing** — remember user's panel size preferences

### 📤 Export & Deploy
- [ ] **One-click deploy to Vercel** from within the app
- [ ] **Export as ZIP** — download the full generated project
- [ ] **GitHub push** — commit the generated project directly to a user's repo
- [ ] **StackBlitz / CodeSandbox** open-in-browser integration

### 🏠 Projects Dashboard
- [ ] **Project rename & delete**
- [ ] **Project thumbnails / screenshots**
- [ ] **Project sharing** — share a project link with a collaborator
- [ ] **Project forking** — clone someone else's public project as a starting point
- [ ] **Search & filter** across projects

### 🔐 Auth & User Experience
- [ ] **Usage limits & quota UI** — show how many generations are left
- [ ] **Onboarding flow** — guided first-generation experience for new users
- [ ] **Profile page** — user settings, API key management
- [ ] **Email notifications** for long-running builds

### 🧪 Quality & DX
- [ ] **Unit tests** for API routes and utility functions
- [ ] **E2E tests** with Playwright for the main user flows
- [ ] **CI/CD pipeline** (GitHub Actions) — lint, test, deploy on PR
- [ ] **Storybook** for UI components
- [ ] **Better error messages** throughout the app

---

## 🤝 Contributing

We'd love your help making Mark1 better! All skill levels are welcome — whether you're fixing a typo or shipping a major feature.

### How to Contribute

1. **Fork** the repo and create your branch from `master`
   ```bash
   git checkout -b feat/your-feature-name
   ```
2. **Make your changes** and add tests where applicable
3. **Commit** with a clear, descriptive message
   ```bash
   git commit -m "feat: add one-click Vercel deploy"
   ```
4. **Push** to your fork and open a Pull Request

### Good First Issues

Looking for a place to start? Look for issues tagged [`good first issue`](https://github.com/Vaibhav0-07/mark1main/issues?q=is%3Aissue+label%3A%22good+first+issue%22) or pick anything from the Roadmap above that interests you.

### What Makes a Good PR?

- **Focused** — does one thing well, not five things okay
- **Described** — explains *why* the change is needed, not just what it does
- **Tested** — includes evidence it works (screenshots, test output)
- **Clean** — follows the existing code style and runs `npm run lint` cleanly

### Not Sure Where to Start?

Open an issue and describe what you'd like to work on — we'll help you scope it and point you in the right direction.

---

## 📜 License

MIT © [Vaibhav](https://github.com/Vaibhav0-07) — see [LICENSE](./LICENSE) for details.

---

<div align="center">

Made with ❤️ — if you find Mark1 useful, give it a ⭐

</div>
