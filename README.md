# Chat App

A real-time chat application built with React, Node.js, Socket.IO, and MongoDB.

## Features

- Real-time messaging
- User authentication
- Online/offline status
- Image sharing
- Responsive design
- Dark/Light theme

## Tech Stack

### Frontend
- React 19
- Vite
- Tailwind CSS
- DaisyUI
- Socket.IO Client
- Zustand (State Management)
- Axios

### Backend
- Node.js
- Express.js
- Socket.IO
- MongoDB (Mongoose)
- JWT Authentication
- Cloudinary (Image Upload)
- CORS

## Project Structure

```
chart-app/
├── backend/                 # Node.js backend
│   ├── src/
│   │   ├── controllers/     # Route controllers
│   │   ├── lib/            # Utilities (DB, Socket, etc.)
│   │   ├── middleware/     # Auth middleware
│   │   ├── models/         # MongoDB models
│   │   └── routes/         # API routes
│   └── package.json
├── frontend/               # React frontend
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── pages/          # Page components
│   │   ├── store/          # Zustand stores
│   │   └── lib/            # Utilities
│   └── package.json
├── vercel.json            # Vercel configuration
└── package.json           # Root package.json
```


