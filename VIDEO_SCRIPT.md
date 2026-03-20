# Week 10 Demo Lines

## Opening

"Hello, this is my Week 10 Fullstack project, The Data Hub. It is a REST API backend built with Node.js, Express, Mongoose, and MongoDB Atlas support."

## What This Project Does

"This backend allows me to create users, create blog posts, connect posts to authors using `authorId`, fetch all posts, delete posts, and also fetch the top 3 most recent posts."

## Terminal Intro

"First, I am running the server locally on port 5000. The API is active and ready for testing in Postman."

## Postman Flow

"I will start by creating a user with the `POST /users` route."

"Now I will copy the returned user ID and use it in the `POST /posts` route so this post is linked to a real author."

"Next, I will open `GET /posts` to show that the saved post is coming back with populated author details."

"Now I will call `GET /posts/recent/top-3` to demonstrate the recent-post aggregation route."

"Finally, I will delete one post using `DELETE /posts/:id` to show that real CRUD operations are working."

## Atlas Proof

"Now I am opening MongoDB Atlas Browse Collections. Here you can see the same `users` and `posts` data saved in the cloud database, which proves the backend is using persistent storage."

## Code Highlight

"The main route logic is inside `src/app.js`, the data store and MongoDB handling is in `src/data/blogStore.js`, the database connection logic is in `src/lib/database.js`, and the Mongoose schemas are in `src/models`."

## Closing

"This project covers MongoDB Atlas integration, Mongoose schemas, user-post relationships, CRUD APIs, aggregation, and submission-ready documentation."
