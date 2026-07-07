# Project Configuration (AGENTS.md) - Mobile Hobbies

This file guides development inside the **`mobile-hobbies`** repository.

---

## 🏗️ Repository Overview
* **Name**: `mobile-hobbies`
* **Role**: Mobile D&D Toolkit & Reviews Log
* **Tech Stack**: Expo SDK 57 + React Native 0.86 + TypeScript + `lucide-react-native`
* **Backend Connection**: Queries the shared Supabase DB (`reviews` and `dnd_characters` tables).

---

## 📜 Development Rules
1. **D&D Stat Generation**: Implement a mathematically sound 4d6-drop-lowest formula.
2. **Portrait Seed Generator**: Construct Dicebear PNG image URLs based on random string seeds.
3. **Data Syncing**: Post review logs and D&D character details to the shared Supabase API. Use authenticated user IDs.
4. **Icons**: Import native vector icons from `lucide-react-native`.

---

## 📂 Backend Integration Details
- **Reviews Table (`reviews`)**: Columns `id`, `user_id`, `title`, `category` ('film'/'anime'), `rating` (1-10), `comment`.
- **D&D Table (`dnd_characters`)**: Columns `id`, `user_id`, `name`, `class`, `stats` (JSONB), `portrait_url`.
- **Endpoints**:
  - `GET /reviews` & `POST /reviews`
  - `GET /dnd/characters` & `POST /dnd/characters`
