# Foosball API ⚽

![Foosball Table]([https://via.placeholder.com/800x200?text=Foosball+API+Logo](https://plus.unsplash.com/premium_photo-1661893934486-bdf06cfcb2f7?fm=jpg&q=60&w=3000&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NXx8Zm9vc2JhbGx8ZW58MHx8MHx8fDA%3D))

Welcome to the **Foosball API**, a powerful backend built with **NestJS** to manage foosball games, track statistics, and enhance community engagement. Whether you're running casual matches or organizing competitive tournaments, this API provides the tools you need with a modular and scalable design.

---

## 🌟 Features

### Game Component
The **Game Component** is the core of the Foosball API, designed to manage and analyze foosball matches comprehensively.

- **Real-Time Statistics Tracking**:  
  Track game statistics as they happen using **NestJS's WebSocket support**. Connect to our WebSocket endpoint to get live updates on scores, player actions, and game events. This feature is perfect for real-time dashboards or live match updates.

- **Retrieve Statistics by Games**:  
  Access detailed statistics for any game, past or present, via RESTful endpoints. For example:
  ```bash
  GET /games/:id/stats
  ```
  Retrieve data like final scores, player contributions, and match duration to analyze performance or generate reports.

### Notification Listeners
Stay informed with our event-driven **Notification Listeners**, built using **NestJS's event emitter module**.

- **Listening for Game Start Events**:  
  The system listens for events like the start of a game and instantly notifies subscribed clients or services, ensuring you never miss a kickoff.

- **MVP Polls**:  
  After a game ends, an MVP poll is launched. Players and spectators can vote for the Most Valuable Player through the API, with results aggregated in real-time for an interactive experience.

### Telegram Integration
The **Telegram Integration** feature connects your foosball community directly to Telegram for seamless communication.

- **Sending Messages**:  
  Automatically send messages to your Telegram group for key events, such as:
  - "Game has started between Player A and Player B!"
  - "New tournament generated—check the schedule!"
  Configure your Telegram bot token in the `.env` file to enable this feature.

- **Tournament Schedule Screenshots**:  
  Generate and send screenshots of tournament schedules to your Telegram group. These visuals help participants plan and discuss upcoming matches easily.  

### Organizations
The **Organizations** feature lets you manage foosball activities within specific groups.

- **Track Statistics Inside Your Organization**:  
  Create an organization (e.g., for your company or club) to track isolated statistics. Monitor leaderboards, win rates, and player performance specific to your group, making it ideal for internal leagues or friendly competitions.

### Seasons
Organize your foosball data with the **Seasons** feature.

- **Seasonal Management**:  
  Define seasons to segment games, tournaments, and statistics over time. This allows you to:
  - Reset stats for a fresh start each season
  - Compare performance across seasons
  - Archive past seasons for historical reference  
  Seasons keep your data structured and meaningful.

### Player Statistics
Get detailed insights into player performance with the **Player Statistics** feature.

- **Available Statistics**:  
  Access a wide range of metrics for each player, such as:
  - Win/loss record
  - Goals scored and conceded
  - Win rate percentage
  - Performance trends over time
  - Head-to-head stats against opponents  
  Retrieve this data via:
  ```bash
  GET /players/:id/stats
  ```
  Use these stats to build leaderboards, analyze skills, or integrate with other tools.

---

## 🚀 Getting Started

### Prerequisites
- **Node.js** (v14 or higher)
- **MongoDB** (local or cloud-hosted)
- **Git**

### Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/vkorop/foosball-api.git
   ```

2. **Switch to the Dev Branch**:
   ```bash
   cd foosball-api
   git checkout dev
   ```

3. **Install Dependencies**:
   ```bash
   npm install
   ```

4. **Configure Environment Variables**:
   - Copy the example `.env` file:
     ```bash
     cp .env.example .env
     ```
   - Update `.env` with your MongoDB connection string, Telegram bot token, and other settings (e.g., `PORT`).

5. **Launch the Server**:
   ```bash
   npm run start:dev
   ```
   The API will be available at `http://localhost:3000` (or your configured port).

---

## 🛠️ API Endpoints

### 🎮 Games
- **Create a Game**  
  `POST /games`  
  **Request**:  
  ```json
  {
    "player1": "playerID1",
    "player2": "playerID2"
  }
  ```  
  **Response**:  
  ```json
  {
    "id": "gameID",
    "player1": "playerID1",
    "player2": "playerID2",
    "score": { "player1": 0, "player2": 0 },
    "status": "ongoing"
  }
  ```

- **Get Game Statistics**  
  `GET /games/:id/stats`

### 🏆 Players
- **Get Player Statistics**  
  `GET /players/:id/stats`  
  **Response**:  
  ```json
  {
    "id": "playerID",
    "name": "John Doe",
    "wins": 10,
    "losses": 5,
    "goalsScored": 25,
    "winRate": 66.67
  }
  ```

---

## 🤝 Contributing

We welcome contributions! To get started:
1. Fork the repository.
2. Create a branch (`git checkout -b feature/your-idea`).
3. Commit your changes (`git commit -m "Add your idea"`).
4. Push to your branch (`git push origin feature/your-idea`).
5. Submit a pull request.

---

## 📜 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## 📬 Contact

Have questions? Open an issue or reach out at [your-email@example.com](mailto:vlad.koropets@gmail.com).

_"Spin, score, and stats—Foosball API brings the game to life!"_
