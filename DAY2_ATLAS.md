# Day 2 Atlas Setup

## Goal

Today we connect the Week 10 backend to MongoDB Atlas and prove the data is saving in the cloud.

## Step 1: Create Cluster

1. Open `https://cloud.mongodb.com`
2. Create a new project
3. Choose the free `M0` cluster
4. Wait for the cluster to finish deploying

## Step 2: Create Database User

1. Open Atlas `Security`
2. Go to `Database Access`
3. Add a new database user
4. Give it a username and password
5. Use `Read and write to any database`

Tip:
Use a strong password with letters and numbers to avoid URI encoding confusion.

## Step 3: Allow Network Access

1. Open `Network Access`
2. Click `Add IP Address`
3. Choose `Add My Current IP Address`

Fallback for demos:
Use `0.0.0.0/0` if your IP keeps changing.

## Step 4: Copy the Connection String

1. Open your cluster
2. Click `Connect`
3. Choose `Drivers`
4. Select `Node.js`
5. Copy the `mongodb+srv://...` URI

Replace the database name part with:

```text
week10DataHub
```

## Step 5: Update `.env`

Open [`.env`](a:\company projects\week10-data-store\.env) and set:

```env
PORT=5000
DATA_STORE_MODE=mongo
MONGO_URI=mongodb+srv://YOUR_USERNAME:YOUR_PASSWORD@YOUR_CLUSTER_URL/week10DataHub?retryWrites=true&w=majority&appName=Week10DataHub
```

## Step 6: Verify the Connection

Run:

```powershell
Set-Location 'a:\company projects\week10-data-store'
cmd /c npm.cmd run check:mongo
```

If this succeeds, start the server:

```powershell
cmd /c npm.cmd run dev
```

## Step 7: Postman Test Order

### `POST /users`

```json
{
  "name": "Nakul",
  "email": "nakul@example.com"
}
```

### `POST /posts`

Use the `id` returned by `POST /users`:

```json
{
  "title": "My first Mongo post",
  "content": "Atlas connection is working.",
  "authorId": "PASTE_USER_ID_HERE"
}
```

### Then run

1. `GET /posts`
2. `GET /posts/recent/top-3`
3. `DELETE /posts/:id`

## Step 8: Atlas Proof

Open Atlas `Browse Collections` and show:

- `users`
- `posts`

That is the main proof for Day 2.
