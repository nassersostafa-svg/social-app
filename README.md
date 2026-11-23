# Social Media API

A social media backend with a REST API, a GraphQL endpoint and real-time chat, built with Express and TypeScript on MongoDB.

## Features

- **Authentication**: JWT access + refresh tokens, email verification, Google login
- **Posts**: create, update, delete posts with image uploads (AWS S3), likes
- **Comments**: comment on posts with authorization rules
- **Real-time chat**: one-to-one chat over Socket.IO with online/offline presence and typing indicators (see `CHAT_FEATURES_README.md`)
- **GraphQL**: an alternative GraphQL API for users and posts alongside the REST controllers
- **Security**: helmet, CORS, rate limiting, input validation with zod, bcrypt password hashing

## Tech stack

Express 5 · TypeScript · MongoDB (Mongoose) · Socket.IO · GraphQL (graphql-http) · JWT · AWS S3 (multer) · zod · nodemailer

## Project structure

```
src/
  modules/
    auth/
    user/
    post/
    comment/
    chat/        # Socket.IO gateway, events, service
    graphql/     # GraphQL schema and types
  middleware/
  DB/
  utils/
FE/            # minimal front-end demo for the chat
```

## Getting started

```bash
npm install
npm run start:dev   # tsc --watch + node --watch
```

Set the environment variables (`.env`):

```env
PORT=3000
DB_URL=<your MongoDB connection string>
SALT=10
ACCESS_USER_TOKEN_SIGNATURE=...
ACCESS_SYSYEM_TOKEN_SIGNATURE=...
REFRESH_USER_TOKEN_SIGNATURE=...
ACCESS_TOKEN_EXPIRES_IN=...
REFRESH_TOKEN_EXPIRES_IN=...
EMAIL=<gmail address>
EMAIL_PASSWORD=<gmail app password>
WEB_CLIENT_IDS=<Google OAuth client id>
AWS_REGION=...
AWS_ACCESS_KEY_ID=...
AWS_SECRET_ACCESS_KEY=...
AWS_BUCKET_NAME=...
```
