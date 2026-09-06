# Samryetha Development

> **Yet Another OpenSource Forum. More modern, More code!!!**

Samryetha is a modern, open-source community forum. It started life as the discussion platform for the
Nanjing Foreign Language School community and grew into a clean, self-hostable forum you can run anywhere —
with real-time presence, threaded conversations, direct messages, and a moderation story that scales.

---

## ✨ What Samryetha looks like

- **Boards & threads** — public / members-only / private boards with per-policy posting.
- **A real comment tree** — YouTube-style threaded replies with continuous SVG connector lines, avatars as
  tree nodes, an inline reply composer, and buttery FLIP layout animations on post/delete.
- **Markdown or plain text** — pick per message; rendered server-side with a strict HTML sanitizer.
- **Talk to people** — in-app inbox & direct messages, follow authors, save threads.
- **Stay in the loop** — live notifications over SSE, search, online presence.
- **Built to moderate** — reports, bans, soft-delete with audit, content restoration, role-based access
  (member / moderator / admin), and per-board pins & locks.
- **Feedback & tasks, built in** — a feedback board and a dev task tracker live inside the product.

## 🧰 Tech

| Layer    | Stack |
| -------- | ----- |
| Frontend | React 19 · TypeScript · Vite SSR (Express) · Tailwind CSS |
| Backend  | Python 3 · FastAPI · SQLAlchemy · SQLite |
| Extras   | Argon2id, HMAC-signed storage, SSE, `markdown-it` + `nh3` sanitizing |

Dev is deliberately local-first (`python bootstrap.py --dev` gives you two servers and zero cloud deps);
typed interfaces leave room for Postgres / Redis / S3 / SMTP later.

---

## 📦 Repositories

| Repo | What it is |
| ---- | ---------- |
| [**Samryetha**](https://github.com/Samryetha-Development/Samryetha) | The main codebase — frontend + backend, docs, CI. Start here. |
| **.github** | This org: community health files, issue & PR templates, shared workflows (being added). |

---

## 🚀 Run it locally

```bash
# requires Node 22+, pnpm, uv, python 3.12
git clone https://github.com/Samryetha-Development/Samryetha
cd Samryetha
python bootstrap.py --dev
```

- Web app → http://localhost:3000
- API docs → http://localhost:3001/docs

Built-in dev accounts (`admin` / `dev`) are seeded on first boot.

---

## 🛠️ Development workflow

We keep main green. Before opening a PR, run the same gates CI runs:

```bash
cd frontend && npx tsc --noEmit      # frontend types
cd backend  && pytest                # backend tests
cd backend  && uv run ruff check src # lint (bug-class rules)
```

Branches are `feat/*`, `fix/*`. Contributors — human **or agent** — should read the
[`AGENTS.md`](https://github.com/Samryetha-Development/Samryetha/blob/dev/AGENTS.md) at the repo root;
it defines the project's conventions and is kept current as the ground truth for AI-assisted work.

## 🤝 Contributing

1. Open an **issue** first for anything non-trivial — we discuss before we build.
2. Branch from `dev` (that's where active work lands).
3. Keep commits focused and messages descriptive.
4. Open a PR against `dev`; CI must pass; two eyes review.

Community health files (`CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, issue/PR templates) are
being published to this org repository — watch this space.

---

## 📄 License

Samryetha is open source under the [MIT License](https://github.com/Samryetha-Development/Samryetha/blob/main/LICENSE).
