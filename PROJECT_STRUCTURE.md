# Spotify Clone - Complete Project Structure

## 📁 Directory Layout

```
spotify-clone/
│
├── frontend/                          # React.js Frontend
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Player/
│   │   │   ├── Sidebar/
│   │   │   ├── SearchBar/
│   │   │   ├── Playlist/
│   │   │   └── NowPlaying/
│   │   ├── pages/
│   │   │   ├── Home/
│   │   │   ├── Search/
│   │   │   ├── Playlist/
│   │   │   ├── Library/
│   │   │   └── Profile/
│   │   ├── services/
│   │   │   ├── api.js
│   │   │   ├── auth.js
│   │   │   └── player.js
│   │   ├── context/
│   │   │   ├── AuthContext.js
│   │   │   ├── PlayerContext.js
│   │   │   └── PlaylistContext.js
│   │   ├── styles/
│   │   ├── App.js
│   │   └── index.js
│   ├── package.json
│   └── README.md
│
├── backend/                           # Node.js + Express Backend
│   ├── src/
│   │   ├── config/
│   │   │   ├── database.js
│   │   │   ├── aws.js
│   │   │   └── auth.js
│   │   ├── controllers/
│   │   │   ├── authController.js
│   │   │   ├── userController.js
│   │   │   ├── songController.js
│   │   │   ├── playlistController.js
│   │   │   └── searchController.js
│   │   ├── models/
│   │   │   ├── User.js
│   │   │   ├── Song.js
│   │   │   ├── Playlist.js
│   │   │   ├── Artist.js
│   │   │   └── Album.js
│   │   ├── routes/
│   │   │   ├── auth.js
│   │   │   ├── users.js
│   │   │   ├── songs.js
│   │   │   ├── playlists.js
│   │   │   └── search.js
│   │   ├── middleware/
│   │   │   ├── auth.js
│   │   │   ├── errorHandler.js
│   │   │   └── validation.js
│   │   ├── utils/
│   │   │   ├── fileUpload.js
│   │   │   ├── jwt.js
│   │   │   └── recommendations.js
│   │   └── server.js
│   ├── .env.example
│   ├── package.json
│   └── README.md
│
├── database/                          # Database Schema
│   ├── schema.sql
│   ├── migrations/
│   └── seeds/
│
├── docs/                              # Documentation
│   ├── API_DOCUMENTATION.md
│   ├── SETUP_GUIDE.md
│   ├── ARCHITECTURE.md
│   └── DEVELOPMENT_GUIDE.md
│
├── .gitignore
├── docker-compose.yml
└── README.md
```

## 🏗️ System Architecture

### Frontend (React)
- **UI Components**: Player, Sidebar, Search, Playlists
- **State Management**: Context API / Redux
- **Audio Playback**: HTML5 Audio API
- **HTTP Client**: Axios

### Backend (Node.js)
- **Framework**: Express.js
- **Authentication**: JWT (JSON Web Tokens)
- **Database**: PostgreSQL
- **Cache**: Redis
- **File Storage**: AWS S3

### Database Schema
```
Users Table:
- id, email, password, username, profile_pic, created_at

Songs Table:
- id, title, artist_id, album_id, duration, file_url, cover_url

Artists Table:
- id, name, bio, profile_pic

Albums Table:
- id, title, artist_id, release_date, cover_url

Playlists Table:
- id, user_id, title, description, created_at

Playlist_Songs Table:
- id, playlist_id, song_id, added_at

UserLikes Table:
- id, user_id, song_id, created_at
```

## 🎯 Core Features

### Phase 1 (MVP)
- [x] User Authentication (Sign up, Login, Logout)
- [x] Music Upload (Admin only initially)
- [x] Music Player (Play, Pause, Seek, Volume)
- [x] User Library
- [x] Basic Search

### Phase 2
- [ ] Playlists (Create, Edit, Delete, Add Songs)
- [ ] Favorites/Likes
- [ ] User Profiles
- [ ] Follow Artists
- [ ] Share Playlists

### Phase 3
- [ ] Recommendations Algorithm
- [ ] Radio Feature
- [ ] Listening History
- [ ] Social Features (Comments, Shares)
- [ ] Mobile App

### Phase 4
- [ ] Premium Features
- [ ] Payment Integration
- [ ] Offline Download
- [ ] Lyrics Display
- [ ] Podcasts Support

## 🚀 Tech Stack Summary

| Component | Technology |
|-----------|------------|
| Frontend | React.js, Redux, Axios |
| Backend | Node.js, Express.js |
| Database | PostgreSQL |
| Cache | Redis |
| File Storage | AWS S3 |
| Authentication | JWT, bcrypt |
| Deployment | Docker, AWS/Heroku |
| Testing | Jest, Supertest |

## 📊 API Endpoints Overview

```
Authentication:
POST   /api/auth/register
POST   /api/auth/login
POST   /api/auth/logout

Users:
GET    /api/users/:id
PUT    /api/users/:id
GET    /api/users/:id/library

Songs:
GET    /api/songs
GET    /api/songs/:id
POST   /api/songs (admin only)
GET    /api/songs/stream/:id

Playlists:
GET    /api/playlists
POST   /api/playlists
GET    /api/playlists/:id
PUT    /api/playlists/:id
DELETE /api/playlists/:id
POST   /api/playlists/:id/songs
DELETE /api/playlists/:id/songs/:songId

Search:
GET    /api/search?q=query

Recommendations:
GET    /api/recommendations
POST   /api/recommendations/personalized
```

## ⏱️ Development Timeline

- **Week 1-2**: Setup, Database, Authentication
- **Week 3-4**: Music Upload, Player
- **Week 5-6**: Search, Library
- **Week 7-8**: Playlists, User Profiles
- **Week 9-10**: Recommendations, Testing
- **Week 11-12**: Deployment, Optimization

---

**Next Steps**: 
1. Setup frontend and backend
2. Configure database
3. Implement authentication
4. Create basic player UI
