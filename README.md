# ConQuest

Turn studying into a real-life adventure — conquer campus study spots, earn points, and team up with friends to dominate the map.

# Demo Link
[![Watch the demo](https://img.youtube.com/vi/R_yqXzaxmXo/maxresdefault.jpg)](https://www.youtube.com/watch?v=R_yqXzaxmXo)


## Problem / Motivation
Studying alone is isolating and easy to put off. ConQuest brings back the collaborative, imaginative energy of childhood roleplay games and channels it into better study habits — turning campus into an interactive map where progress is social, visible, and a little competitive.

## Features
- **Conquer study spots** — claim real-life locations on campus by logging focused study time there
- **Social incentives** — earn a 2x point multiplier for studying with friends, rewarding collaboration over isolation
- **Community-driven difficulty** — the more popular a spot, the harder it is to conquer, based on live rankings
- **Leveling system** — each location has 10 levels with exponentially increasing time requirements, tracked per-user
- **Friends system** — send/accept friend requests, opt in to location sharing, and see friends' live locations on the map
- **AI-powered insights** — Gemini-generated location descriptions, personalized recommendations, and study insights (gracefully falls back to default content if no API key is configured)
- **Enhanced location data** — server-side geocoding and nearby-places lookup via the Google Maps API
- **Live interactive map** — built with Leaflet, updates in real time as users study and rankings shift

## Tech Stack
- **Frontend:** React 19 + Vite, Tailwind CSS, React Router
- **Backend:** Node.js + Express
- **Database & Auth:** Supabase (Postgres, real-time sync, Row Level Security)
- **Map:** Leaflet + react-leaflet
- **AI:** Google Gemini API
- **Location services:** Google Maps API (geocoding)

## Setup

### 1. Clone and install
```bash
git clone <your-repo-url>
cd ConQuest
npm run install:all
```

### 2. Configure environment variables
Copy the example files and fill in your own credentials:
```bash
cp client/.env.example client/.env
cp server/.env.example server/.env
```
You'll need a Supabase project (URL, anon key, service role key) and optionally a Google Gemini API key for AI features — the app runs fine without the Gemini key, just with fallback content instead of live AI responses.

### 3. Set up the database
Follow the instructions in [`database/DATABASE_SETUP_INSTRUCTIONS.md`](database/DATABASE_SETUP_INSTRUCTIONS.md) to run the schema in your Supabase SQL editor.

### 4. Run it
```bash
npm run dev
```
This starts the client (http://localhost:5173) and server (http://localhost:3001) together.

## My Role
I designed and built several of the app's core frontend features:
- The initial interactive map component (`MapView.jsx`) — the central "conquer study spots" experience
- The Friends system UI (`FriendsList.jsx`), enabling friend requests and location sharing
- The Leaderboard and Profile pages, including the profile photo feature
- The API service layer methods connecting the frontend to the friends/location backend endpoints
- The overall visual design pass — Tailwind styling and layout across the map, friends, and dashboard views

Teammates continued building on some of these components afterward. The current implementation reflects both my original work and later contributions from the team.

## Challenges & What We Learned
- Working with mapping and geolocation libraries inside a React app
- Designing gamification mechanics (points, levels, difficulty scaling) that motivate without undermining usability
- Handling real-time data updates and syncing user locations across the map
- Integrating a third-party AI API with fallback behavior when the service is unavailable

## What's Next
- Mobile app for on-the-go check-ins
- QR codes at physical study spots for easier check-ins
- School-wide leaderboards and longer-term group challenges
- Expanded map coverage for more study locations

## Team
Created in collaboration with Sophia Wei, Nathan Guan, and Alicia Yu at DubHacks 2025.
