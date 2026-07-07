# Spec: Hobbies Mobile App (`mobile-hobbies`)

This repository contains the standalone **Hobbies** React Native app, focusing on D&D utility tools and movie/anime logs.

---

## 🛠️ Tech Stack & Dependencies
* **Framework**: Expo SDK 57 + React Native 0.86
* **Language**: TypeScript
* **Icons**: `lucide-react-native`
* **Network Client**: Axios or native `fetch` (communicating with the shared backend)

---

## 📂 Folder Structure
```text
hobbies-app/
├── src/
│   ├── components/         
│   │   ├── ReviewCard.tsx     # Custom styled Movie/Anime review component
│   │   └── DndStatBox.tsx     # Display box for D&D ability stats
│   ├── screens/
│   │   ├── DndScreen.tsx      # Stat roller & Seed portrait downloader
│   │   └── ReviewsScreen.tsx  # Review log submission form & list feed
│   ├── services/
│   │   └── api.ts             # API connectors to reviews/D&D endpoints
│   └── App.tsx                # App entrypoint and tab/stack view
├── app.json
├── package.json
└── tsconfig.json
```

---

## ⚙️ App Requirements

### 1. D&D character generator
- **Stat roller**: Executes a 4d6-drop-lowest roll generating ability scores (STR, DEX, CON, INT, WIS, CHA).
- **Class selector**: Dropdown to select character class.
- **Portrait generator**: Fetches PNG avatars dynamically using random seeds from `https://api.dicebear.com/7.x/pixel-art/png?seed=...` and displays inside `<Image>`.
- **Saving characters**: Posts character statistics, name, and class to the database.

### 2. Anime & Movie Review logs
- **Log inputs**: Title, Rating selection (1-10), Category selector (Film / Anime), and written comments.
- **Reviews feed**: Displays historical logged reviews sorted by creation time.

---

## 🔌 Backend API Connections
This app integrates with the shared backend database using the following endpoints:

* `GET /reviews` -> Retrieves film/anime reviews.
* `POST /reviews` -> Logs a new movie or anime review.
* `GET /dnd/characters` -> Fetch saved user character sheets.
* `POST /dnd/characters` -> Save a new character sheet (sends name, class, stats JSON).
