# Week 10 Submission Checklist

## Before Recording

- Run `npm install`
- Create `.env` from `.env.example`
- Add your real `MONGO_URI`
- Confirm Atlas Network Access allows your current IP or `0.0.0.0/0`
- Run `npm run dev`
- Open Postman and MongoDB Atlas dashboard

## Required Submission Items

- GitHub repository with full code
- Updated `Prompts.md`
- 3-minute demo video
- Google Form submission

## GitHub Push

- Use a Week 10 repository or folder name that matches your final submission
- Do not push `.env`
- Push your final branch after checking `README.md`, `Prompts.md`, and `VIDEO_SCRIPT.md`

## Demo Proof Points

- Show the server running on port `5000`
- Create a user with `POST /users`
- Create a post with `POST /posts` using the saved `authorId`
- Show `GET /posts` returning populated author details
- Show `GET /posts/recent/top-3`
- Delete one post with `DELETE /posts/:id`
- Open MongoDB Atlas `Browse Collections` to prove the data was saved in the cloud
- Show `POST /login` returning the mock token

## Deployment Note

- Company guidance for an Express backend points to Render
- [render.yaml](a:\company projects\week10-data-store\render.yaml) is included so the project is ready for a Render web service
- `MONGO_URI` must be added in Render environment variables before the deployment can work

## Final Check

- `.env` must stay private
- `node_modules` and `.npm-cache` must not be committed
- Keep `README.md`, `Prompts.md`, and the Postman collection in the repo
