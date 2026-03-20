# The Data Hub

Week 10 Fullstack internship project built with Node.js, Express, Mongoose, and MongoDB Atlas. The API now stores blog posts in a real database, supports author relationships, and includes an aggregation route for the latest posts.

## Features

- Express server with clean REST routes
- MongoDB Atlas connection through Mongoose
- `User` and `Post` schemas with `authorId` relationships
- CRUD routes for posts
- `GET /posts/recent/top-3` aggregation route
- Custom request logger middleware
- Mock login endpoint for submission demo
- Memory-mode automated tests for fast local verification

## Project Structure

```text
week10-data-store/
  src/
    app.js
    config/env.js
    data/blogStore.js
    lib/database.js
    middleware/requestLogger.js
    models/Post.js
    models/User.js
  tests/api.test.js
  .env.example
  server.js
```

## Setup

1. Install dependencies:

```bash
npm install
```

2. Create a `.env` file from `.env.example`.

3. Add your MongoDB Atlas URI:

```env
PORT=5000
DATA_STORE_MODE=mongo
MONGO_URI=mongodb+srv://username:password@cluster-url/week10DataHub?retryWrites=true&w=majority&appName=Week10DataHub
```

4. Start the API:

```bash
npm run dev
```

The API will start at `http://localhost:5000`.

## Scripts

- `npm run dev` starts the server
- `npm run dev:watch` starts the server in watch mode
- `npm start` starts the server normally
- `npm test` runs local memory-mode API checks
- `npm run check:mongo` verifies your Atlas URI and connection before you run the server

## Deployment

The internship FAQ recommends deploying an Express backend on Render.

### Render

This repository includes [render.yaml](a:\company projects\week10-data-store\render.yaml) so the service is deployment-ready.

Render configuration:

- Runtime: `Node`
- Build command: `npm install`
- Start command: `npm start`
- Health check path: `/`
- Required secret: `MONGO_URI`

Before creating the Render service:

1. Push this repository to GitHub
2. Connect the repo in Render
3. Provide the `MONGO_URI` secret
4. Keep `DATA_STORE_MODE=mongo`

## Core Endpoints

### `POST /users`

Creates a user so posts can reference a real author.

```json
{
  "name": "Nakul",
  "email": "nakul@example.com"
}
```

### `GET /users`

Returns all saved users.

### `POST /posts`

Creates a post in MongoDB. You can pass `authorId` or a plain `author` name.

```json
{
  "title": "Atlas Connected",
  "content": "This post is stored in MongoDB Atlas.",
  "authorId": "replace-with-user-id"
}
```

### `GET /posts`

Returns all saved posts with populated author details.

### `GET /posts/:id`

Returns one post by ID.

### `PUT /posts/:id`

Updates one or more post fields.

### `DELETE /posts/:id`

Deletes a post from the database.

### `GET /posts/recent/top-3`

Uses MongoDB aggregation to return the three most recent posts.

### `POST /login`

Returns a mock token for demo authentication.

## Postman Demo Flow

1. Send `POST /users` to create an author.
2. Send `POST /posts` using that `authorId`.
3. Send `GET /posts` and show the populated author details.
4. Send `GET /posts/recent/top-3` to show the aggregation route.
5. Send `DELETE /posts/:id` to prove database deletion works.
6. Open MongoDB Atlas `Browse Collections` to show the same saved data.

## Notes

- Keep `.env` out of GitHub. It is already ignored.
- For real submission proof, Atlas Network Access should allow your IP or `0.0.0.0/0`.
- Local tests use the memory store so you can verify routes without hitting Atlas every time.
- See [DAY2_ATLAS.md](a:\company projects\week10-data-store\DAY2_ATLAS.md) for the shortest Atlas setup flow.
