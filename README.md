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

## Deployment

This is a full-stack application that requires separate deployment for frontend and backend.

### Backend Deployment (Railway - Recommended)

1. **Create Railway Account**
   - Go to [Railway](https://railway.app/)
   - Sign up with GitHub

2. **Deploy Backend**
   - Create new project
   - Connect your GitHub repository
   - Set root directory to `backend`
   - Railway will automatically detect Node.js

3. **Environment Variables**
   Add these environment variables in Railway:
   ```
   MONGODB_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret_key
   CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
   CLOUDINARY_API_KEY=your_cloudinary_api_key
   CLOUDINARY_API_SECRET=your_cloudinary_api_secret
   NODE_ENV=production
   ```

4. **Get Backend URL**
   - After deployment, copy your Railway app URL
   - Example: `https://your-app.railway.app`

### Frontend Deployment (Vercel)

1. **Create Vercel Account**
   - Go to [Vercel](https://vercel.com/)
   - Sign up with GitHub

2. **Deploy Frontend**
   - Import your GitHub repository
   - Vercel will automatically detect the frontend configuration
   - The `vercel.json` file is already configured

3. **Environment Variables**
   Add this environment variable in Vercel:
   ```
   VITE_API_URL=https://your-backend-url.railway.app/api
   ```

4. **Update CORS Settings**
   After getting your Vercel domain, update the CORS origins in:
   - `backend/src/index.js`
   - `backend/src/lib/socket.js`
   
   Replace `your-app-name.vercel.app` with your actual Vercel domain.

### Alternative Backend Deployment Options

#### Render
1. Go to [Render](https://render.com/)
2. Create new Web Service
3. Connect GitHub repository
4. Set root directory to `backend`
5. Build command: `npm install`
6. Start command: `npm start`
7. Add the same environment variables as Railway

#### Heroku
1. Go to [Heroku](https://heroku.com/)
2. Create new app
3. Connect GitHub repository
4. Set root directory to `backend`
5. Add the same environment variables

## Local Development

### Prerequisites
- Node.js (v18 or higher)
- MongoDB database
- Cloudinary account

### Setup

1. **Clone Repository**
   ```bash
   git clone <repository-url>
   cd chart-app
   ```

2. **Backend Setup**
   ```bash
   cd backend
   npm install
   ```
   
   Create `.env` file:
   ```
   PORT=5001
   MONGODB_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret
   CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
   CLOUDINARY_API_KEY=your_cloudinary_api_key
   CLOUDINARY_API_SECRET=your_cloudinary_api_secret
   ```

3. **Frontend Setup**
   ```bash
   cd frontend
   npm install
   ```

4. **Run Development Servers**
   ```bash
   # Terminal 1 - Backend
   cd backend
   npm run dev
   
   # Terminal 2 - Frontend
   cd frontend
   npm run dev
   ```

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

## Troubleshooting

### Common Issues

1. **CORS Errors**
   - Make sure your backend CORS settings include your frontend domain
   - Check that `credentials: true` is set

2. **WebSocket Connection Issues**
   - Verify the WebSocket URL is correct
   - Check that your backend supports WebSocket connections

3. **Environment Variables**
   - Ensure all environment variables are set correctly
   - Check that variable names match exactly

4. **Database Connection**
   - Verify your MongoDB connection string
   - Ensure your database is accessible from your deployment platform

### Support

If you encounter any issues, check:
1. The deployment logs in your hosting platform
2. Browser console for frontend errors
3. Backend server logs for API errors

## License

ISC 