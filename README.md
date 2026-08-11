## ConQuest

Turn studying into a real-life adventure — conquer campus study spots, earn points, and team up with friends to dominate the map.

[insert demo gif here]

## Motivation

Studying alone is isolating and easy to put off. ConQuest brings back the collaborative, imaginative energy of childhood roleplay games and channels it into better study habits — turning campus into an interactive map where progress is social, visible, and a little competitive.

## Features
Claim ("conquer") real-life study spots by logging focused study time there
2x point multiplier for studying with friends, rewarding collaboration over isolation
Community-driven spot rankings — the more popular a spot, the harder it is to conquer
Live interactive campus map that updates in real time as users study and rankings shift

## 🚀 Tech Stack

-**Frontend**: React 19 + Vite, Tailwind CSS, React Router
-**Backend**: Node.js + Express
-**Database/Auth**: Supabase (auth, real-time sync)
-**Map**: Leaflet + react-leaflet
-**AI**: Google Gemini API — server-side calls power three AI features (location descriptions, recommendations, insights)
-**Google Maps API**: used server-side for geocoding study-spot locations

## My Contribution

## 📁 Project Structure

```
web-app/
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # Reusable components
│   │   ├── contexts/       # React contexts
│   │   ├── lib/           # Utilities and configurations
│   │   ├── pages/         # Page components
│   │   └── services/      # API services
│   ├── .env.example       # Environment variables template
│   └── package.json
├── server/                 # Express.js backend
│   ├── server.js          # Main server file
│   ├── .env.example       # Environment variables template
│   └── package.json
├── .gitignore
└── package.json           # Root package.json with scripts
```

## 🛠️ Setup Instructions

### Prerequisites

- Node.js 20.19+ or 22.12+
- npm or yarn
- Git

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd web-app
```

### 2. Install Dependencies

```bash
# Install all dependencies (client + server)
npm run install:all

# Or install separately
npm install                    # Root dependencies
cd client && npm install      # Client dependencies
cd ../server && npm install   # Server dependencies
```

### 3. Environment Setup

#### Client Environment

Copy the example environment file and configure it:

```bash
cp client/.env.example client/.env.local
```

Edit `client/.env.local`:

```env
# Supabase Configuration
VITE_SUPABASE_URL=https://your-project-id.supabase.co
VITE_SUPABASE_ANON_KEY=your-supabase-anon-key

# API Configuration
VITE_API_URL=http://localhost:3001
```

#### Server Environment

```bash
cp server/.env.example server/.env
```

Edit `server/.env`:

```env
PORT=3001
```

### 4. Supabase Setup

1. Create a new project at [supabase.com](https://supabase.com)
2. Go to Settings → API
3. Copy your project URL and anon key
4. Update your `client/.env.local` file with these values
5. Enable authentication providers in Supabase dashboard:
   - Email/Password authentication
   - OAuth providers (Google, Microsoft, etc.)

### 5. Start Development

```bash
# Start both client and server
npm run dev

# Or start separately
npm run client:dev    # Client only (port 5173)
npm run server:dev    # Server only (port 3001)
```

## 📚 Available Scripts

### Root Scripts

- `npm run dev` - Start both client and server
- `npm run install:all` - Install all dependencies
- `npm run build` - Build for production

### Client Scripts

- `npm run client:dev` - Start Vite development server
- `npm run client:build` - Build client for production

### Server Scripts

- `npm run server:dev` - Start server with nodemon
- `npm run server:start` - Start server normally

## 🔧 API Endpoints

### Health Check
- `GET /api/health` - Server health status

### Items API
- `GET /api/items` - Get all items
- `POST /api/items` - Create new item
- `PUT /api/items/:id` - Update item
- `DELETE /api/items/:id` - Delete item

### Authentication API
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user

## 🎨 UI Components

### Authentication
- **SignIn**: Email/password login with OAuth options
- **SignUp**: User registration with validation
- **AuthContext**: Global authentication state management

### Pages
- **Dashboard**: Main application dashboard
- **Profile**: User profile management
- **Settings**: Application settings

## 🔐 Authentication Flow

1. **Supabase First**: Primary authentication through Supabase
2. **Backend Fallback**: Falls back to backend API if Supabase fails
3. **OAuth Support**: Google and Microsoft OAuth integration
4. **Session Management**: Automatic token refresh and session handling

## 🚀 Deployment

### Client Deployment

```bash
cd client
npm run build
# Deploy the 'dist' folder to your hosting service
```

### Server Deployment

```bash
cd server
npm start
# Deploy to your server platform (Heroku, Railway, etc.)
```

## 🛡️ Security Features

- Environment variable protection
- CORS configuration
- Input validation
- Secure authentication flow
- Protected API routes

## 📝 Development Notes

- **Hot Reload**: Both client and server support hot reload
- **Environment Variables**: Use `.env.local` for client, `.env` for server
- **API Communication**: Client communicates with server via REST API
- **Error Handling**: Comprehensive error handling throughout the app

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🆘 Support

If you encounter any issues:

1. Check the console for errors
2. Verify environment variables are set correctly
3. Ensure Supabase project is properly configured
4. Check that all dependencies are installed

For more help, please open an issue in the repository.
