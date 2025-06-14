# ♟️ Chess Master

Chess Master is a full-stack web application that allows users to play chess in various modes, including local multiplayer, global multiplayer, and against Stockfish AI. The platform also features user authentication, player profiles, and chess puzzles to enhance your skills.

---

## 🚀 Live Demo

- **Frontend:** [chess-master-two.vercel.app](https://chess-master-two.vercel.app/)
- **Backend:** [chess-master-hk3o.onrender.com](https://chess-master-hk3o.onrender.com/)

---

## 🧩 Features

- **Multiple Game Modes:**
  - Play against Stockfish AI
  - Local multiplayer
  - Global multiplayer (real-time)
  - Random matchmaking
  - Chess puzzles
- **User Authentication:** Secure registration, login, and logout
- **Player Profiles:** Track your stats, match history, and progress
- **Real-time Gameplay:** Powered by Socket.IO for smooth multiplayer
- **Modern UI:** Built with React and Tailwind CSS
- **Responsive Design:** Works great on desktop and mobile

---

## 🗂️ Project Structure

```
backend/    # Node.js/Express backend (API, authentication, database, WebSockets)
frontend/   # React frontend (UI, game logic, assets)
```

---

## ⚙️ Getting Started

### Prerequisites
- Node.js (v16 or higher recommended)
- npm or yarn

### Backend Setup
```sh
cd backend
npm install
# Configure your .env file (MONGO_URI, JWT_SECRET, etc.)
npm start
```

### Frontend Setup
```sh
cd frontend
npm install
npm run dev
```

---

## 🛠️ Technologies Used
- **Frontend:** React, Vite, Tailwind CSS
- **Backend:** Node.js, Express, MongoDB
- **Authentication:** JWT (JSON Web Tokens)
- **Real-time:** Socket.IO (WebSockets)

---

## 📡 WebSocket Events

Chess Master uses Socket.IO for real-time multiplayer features. Key events include:
- `connection` / `disconnect`: Player joins/leaves
- `waitingCount`: Updates number of players in queue
- `gameAssigned`: Notifies players of a new game
- `move`: Send/receive chess moves
- `gameState`: Sync board state
- `opponent`: Opponent info
- `color`: Assigns white/black
- `opponentReconnected`: Handles reconnections

---

## 📚 Backend API Endpoints

All endpoints are prefixed with `/user` or `/profile` and expect/return JSON.

### Authentication & User
- `POST /user/register` — Register a new user.  
  **Body:** `{ username, email, password }`
- `POST /user/login` — Log in a user.  
  **Body:** `{ email, password }`  
  **Returns:** JWT token (in cookie) and user info.
- `POST /user/logout` — Log out the current user (clears cookie).
- `GET /user/:userId` — Get user info by user ID.

### Match History
- `POST /user/:userId/match-history` — Add a match to a user's history.  
  **Body:** `{ opponent, status }`  
  `status` is one of `"win"`, `"lose"`, `"draw"`.
- `GET /user/:userId/match-history` — Get a user's match history.

### Profile (Requires Auth)
- `GET /profile/` — Get the current user's profile (from JWT).
- `GET /profile/settings` — Get user profile settings (placeholder).

### Other
- `GET /stockfish` — Get the best move from Stockfish AI.  
  **Query params:** Follows Stockfish API.
- `GET /health` — Health check endpoint.

---

## 👤 Author

**Kolli Lokesh Reddy**

---

## 📝 License

This project is licensed under the MIT License.
