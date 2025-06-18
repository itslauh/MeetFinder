# MeetFinder
> Flutter / Axum / PostgreSQL application to find the time to meet with friends.

# MeetFinder

> A Flutter / Axum / PostgreSQL application to find the best time to meet with friends.

## Overview

MeetFinder is a full-stack application that helps groups of friends find the optimal time to meet. The backend is built with **Axum** (a high-performance web framework in Rust), **PostgreSQL** for data persistence, and a **Flutter** frontend for cross-platform mobile support.

---

## Backend: Axum in Rust

Axum is an ergonomic and modular async web framework that leverages Rust's type safety and performance. It integrates seamlessly with the Tokio runtime and Tower ecosystem.

### 🔧 Features Covered
- RESTful routing and handler setup
- Extractors for path, query, and JSON body data
- State management via Axum’s `State` extractor
- JSON serialization with Serde
- Middleware and error handling
- PostgreSQL integration via SQLx
- JWT-based authentication
- Testing with Tower’s `oneshot` requests
- Production-ready deployment with Docker

### 📁 Structure

- `main.rs` – Application entry point and router setup
- `handlers/` – Route handler functions (GET/POST, etc.)
- `models/` – Structs for database models and request/response types
- `auth/` – Middleware for handling JWT authorization
- `db/` – SQLx-based database interactions

### 🚀 Deployment

To deploy the backend:
```bash
cargo build --release
./target/release/meetfinder
```

Or use Docker:
```bash
docker build -t meetfinder-backend .
docker run -e DATABASE_URL=... -p 3000:3000 meetfinder-backend
```

---

## Frontend: Flutter

The Flutter app connects to the Axum backend and provides:
- Secure authentication
- A clean UI for submitting and viewing time proposals
- Real-time updates via REST API

---

## Database: PostgreSQL

MeetFinder uses PostgreSQL for storing:
- User accounts
- Availability proposals
- Group meeting metadata

Schema migrations are managed using SQLx’s offline mode and macros.

---

## Getting Started

1. Clone the repo
2. Set up PostgreSQL and run the migrations
3. Configure `.env` with your `DATABASE_URL` and other secrets
4. Start the backend using `cargo run` or Docker
5. Run the Flutter app on your device or emulator

---

## License

MIT License © 2025 Laurens van Wezel
