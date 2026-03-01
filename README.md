# Mini Twitter - Full Stack Social Media Application

A mini Twitter application built with MERN Stack where users can register, login, post messages, and view tweets from all users.

## 🎯 Features

- **User Authentication**
  - User registration with email and username uniqueness validation
  - User login with JWT token authentication
  - Password encryption with bcrypt

- **Message Posting**
  - Create and publish tweet messages
  - View message timeline from all users
  - Messages displayed in reverse chronological order

- **User Interface**
  - Responsive design
  - Modern UI built with Ant Design
  - User avatar and profile information display

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI framework
- **Redux Toolkit** - State management
- **React Router v6** - Routing
- **Ant Design** - UI component library
- **Axios** - HTTP client

### Backend
- **Node.js** - Runtime environment
- **Express** - Web server framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB ODM
- **JWT** - Token-based authentication
- **bcrypt** - Password hashing

### Database
- **MongoDB Atlas** - Cloud database service

## 📦 Project Structure

```
project-blog/
├── tweet-client/          # Frontend application
│   ├── public/
│   ├── src/
│   │   ├── app/          # Redux store configuration
│   │   ├── components/   # React components
│   │   ├── pages/        # Page components
│   │   ├── services/     # API services
│   │   └── hooks/        # Custom hooks
│   └── package.json
│
├── tweet-server/          # Backend application
│   ├── handlers/         # Business logic handlers
│   ├── middleware/       # Middleware (authentication, etc.)
│   ├── models/           # MongoDB data models
│   ├── routes/           # API routes
│   ├── index.js          # Server entry point
│   ├── .env              # Environment variables (needs to be created)
│   └── package.json
│
└── README.md
```

## 🚀 Installation and Setup

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- MongoDB Atlas account

### 1. Clone the Repository

```bash
git clone <repository-url>
cd project-blog
```

### 2. Backend Setup

#### Install Dependencies

```bash
cd tweet-server
npm install
```

#### Configure Environment Variables

Create a `.env` file in the `tweet-server` directory by copying the example file:

```bash
cp .env.example .env
```

Then edit `.env` with your actual values:

```env
MONGODB_URI=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/<database>?appName=<cluster-name>
JWT_SECRET_KEY=your_jwt_secret_key_here
```

**How to get MongoDB URI:**
1. Create a free account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a new cluster (M0 Free tier)
3. Go to Security → Database Access, create a database user
4. Go to Security → Network Access, add your IP (or 0.0.0.0/0 for development)
5. Click "Connect" → "Drivers" → Copy the connection string
6. Replace `<password>` with your database user password
7. Replace `<database>` with `tweet-app` (or your preferred database name)

**Configuration:**
- `MONGODB_URI`: Your MongoDB Atlas connection string
- `JWT_SECRET_KEY`: Any random secure string (e.g., "mySecretKey123!@#")

#### Start Backend Server

```bash
npm start
```

Backend server will run on `http://localhost:8080`

### 3. Frontend Setup

#### Install Dependencies

```bash
cd tweet-client
npm install
```

#### Start Frontend Server

```bash
npm start
```

Frontend application will automatically open at `http://localhost:3000`

## 📝 API Endpoints

### Authentication
- `POST /api/auth/signup` - User registration
- `POST /api/auth/signin` - User login

### Messages
- `GET /api/messages` - Get all messages (authentication required)
- `POST /api/users/:id/messages` - Create new message (authentication required)
- `DELETE /api/users/:id/messages/:message_id` - Delete message (authentication required)

## 🌟 Usage

1. **Register Account**
   - Visit http://localhost:3000
   - Click "Sign Up" to create a new account
   - Enter email, username, and password

2. **Login**
   - Login with your registered email and password

3. **Post Messages**
   - After login, click "Create Message" in the top right corner
   - Enter your message content and submit
   - Message will appear in the home timeline

4. **View Messages**
   - Homepage displays messages from all users
   - Messages are sorted in reverse chronological order

## 🔧 Development Notes

### Frontend Development

Frontend is created with Create React App and supports hot reloading. The browser will automatically refresh when you make changes.

### Backend Development

Backend uses nodemon for auto-restart. The server will automatically restart when you make changes to the code.

### Environment Variables

**Important:** 
- The `.env` file contains sensitive information and is included in `.gitignore`
- Do not commit the `.env` file to version control
- Configure environment variables separately on the server during deployment

## 🙏 Acknowledgments

This project uses the following open-source technologies and services:
- React
- Node.js
- Express
- MongoDB
- Ant Design
- MongoDB Atlas
