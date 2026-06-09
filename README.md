# 🌌 Locus AI
**Where Idea Meets Reality**

Locus AI is a full-stack, AI-powered React app builder. Simply describe the application you want to build, and Locus AI will autonomously write, compile, and render production-ready React code live in your browser. 

Transform your ideas into functional prototypes and fully-fledged applications in seconds, complete with a live workspace, autonomous improvement agents, and a scalable architecture.

---

## ✨ Features

- **Prompt to App:** Describe your idea and watch Locus AI generate a complete React application in real-time.
- **Live Code Preview:** Integrated split-pane layout featuring a chat interface and a live Sandpack browser preview.
- **Autonomous Refinement:** Pro users gain access to our powerful AI agent (powered by the Cline SDK) that can iteratively improve your app, file by file.
- **Auto Error Fixing:** Automatic error detection in the preview pane with a "Fix with AI" one-click resolution.
- **Vision Capabilities:** Upload images or mockups directly into the chat to guide the AI's generation.
- **Project Workspaces:** Persistent chat histories and generated code saved across sessions.
- **Code Export:** Download your generated application as a `.zip` file containing a ready-to-run React project.
- **Tiered Billing:** Integrated credit system with Free, Starter, and Pro plans.

---

## 🛠️ Technology Stack

Locus AI is built with a modern, highly scalable full-stack architecture:

| Category | Technology |
|---|---|
| **Framework** | Next.js 15 (App Router, TypeScript) |
| **Styling** | Tailwind CSS v4, Shadcn UI |
| **Authentication & Billing** | Clerk |
| **Database & Storage** | Supabase (PostgreSQL), Supabase Storage |
| **ORM** | Prisma |
| **AI Models** | Google Gemini 3.5 Flash |
| **AI Agent SDK** | Cline SDK (`@cline/sdk`) |
| **Code Engine** | Sandpack (`@codesandbox/sandpack-react`) |
| **Security & Rate Limiting** | Arcjet |

---

## 🚀 Getting Started

### Prerequisites

- Node.js 22+
- A Supabase Project (Database & Storage)
- A Clerk Application
- A Google AI Studio API Key (Gemini)
- An Arcjet Key

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/dhruvi-git/locus-ai.git
   cd locus-ai
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Set up Environment Variables:**
   Create a `.env.local` file in the root of the project and add the following keys:
   ```env
   # Clerk Auth
   NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
   CLERK_SECRET_KEY=
   NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
   NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up

   # Supabase
   NEXT_PUBLIC_SUPABASE_URL=
   NEXT_PUBLIC_SUPABASE_ANON_KEY=
   DATABASE_URL= # Postgres connection string

   # AI Providers
   GEMINI_API_KEY=

   # Security
   ARCJET_KEY=
   ```

4. **Initialize the Database:**
   ```bash
   npx prisma generate
   npx prisma db push
   ```

5. **Run the Development Server:**
   ```bash
   npm run dev
   ```

6. Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🗄️ Database Schema

The application relies on two primary models in Prisma:

- **`User`**: Synchronized automatically with Clerk upon first login. Tracks user credits and subscription plan.
- **`Workspace`**: Represents an individual AI session. Stores chat messages, generated React files, dependencies, and metadata.

Images uploaded during a session are stored in a public Supabase Storage bucket (`workspace-images`).

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

## 📝 License

This project is licensed under the MIT License.
