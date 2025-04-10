# 🔐 Secret Server – Project Overview

## Introduction
Build a **Secret Server** – a simple web application that allows users to store and share confidential messages via unique, randomly generated URLs.

Each secret:
- Can only be viewed a **limited number of times**
- May have a **Time-To-Live (TTL)** in minutes
- Will be permanently **deleted** once either limit is reached

> ✅ Focus on clean, maintainable code – write something you’d be proud to ship!

---

## 🚧 Project Requirements

### Backend
- Implement a RESTful API using **Node.js** and **Express.js**
- Use **MongoDB** for data persistence (any supporting libraries are welcome)
- Store secrets **securely** (encryption is highly recommended)
- Write **tests** to ensure reliability and correctness

### Frontend
- Create a minimal but functional **React** application
- Core features:
    - Create and store a new secret
    - Retrieve and display a secret (if the hash is known)

### Optional
- Use **Next.js** if you’d like to serve both backend and frontend from a single app

### Deployment
- Share your solution via a public Git hosting platform (GitHub, GitLab, etc.)
- Provide **clear setup instructions**
- Use **Docker Compose** for local development setup (preferred)

---

## 📦 API Endpoints

### `GET /api/secret/:hash`

Fetch a secret by its unique hash.

- **Auth required:** No
- **Response:**
```json
{
  "hash": "string",
  "secretText": "string",
  "createdAt": "2024-01-01T12:00:00.000Z",
  "expiresAt": "2024-01-01T13:00:00.000Z",
  "remainingViews": 0
}
```

### `GET POST /api/secret`

Fetch a secret by its unique hash.

- **Auth required:** No
- **Request Body:**
```json
{
  "secret": "This is the secret text",
  "expireAfterViews": 5,
  "expireAfter": 60
}

```

- expireAfterViews: Number of allowed views before expiration

- expireAfter: Time-to-live in minutes (use 0 for no expiration)

- Response: Returns the same structure as GET /api/secret/:hash.

---

### 🧠 Need Help?
If anything is unclear, feel free to ask questions — it's better to clarify than assume.

---

Happy coding! 🚀

