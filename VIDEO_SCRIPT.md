# 3-Minute Demo Script

## Intro

"This is my Week 10 Fullstack project, The Data Hub. It is a REST API backend built with Node.js, Express, Mongoose, and MongoDB Atlas."

## Demo Flow

1. Show the terminal running `npm run dev`.
2. Open Postman and send `POST /users` to create an author.
3. Copy the returned user `id`.
4. Send `POST /posts` using that `authorId`.
5. Send `GET /posts` and point to the populated `authorDetails`.
6. Send `GET /posts/recent/top-3` and explain that it uses aggregation.
7. Send `DELETE /posts/:id` to remove one post.
8. Open MongoDB Atlas `Browse Collections` and show the saved `users` and `posts`.
9. Send `POST /login` to show the mock token route still works.

## Code Highlight

"The route logic is in `src/app.js`, the MongoDB and memory store abstraction is in `src/data/blogStore.js`, database connection logic is in `src/lib/database.js`, and the Mongoose schemas are in `src/models`."

## Closing

"This project covers MongoDB Atlas connection, Mongoose schemas, CRUD operations, author relationships using `authorId`, and an aggregation route for the top 3 most recent posts."
