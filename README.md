# C Pearl White — Full Stack Project

## Project Structure

```
cpearl/
├── frontend/
│   └── index.html          # Main storefront (improved)
├── backend/
│   ├── index.js            # Express API server
│   ├── routes/
│   │   ├── auth.js         # Admin login + JWT
│   │   ├── products.js     # Product CRUD
│   │   ├── orders.js       # Order save + retrieve
│   │   └── media.js        # Image upload + compress
│   ├── middleware/
│   │   ├── authGuard.js    # JWT verify middleware
│   │   └── rateLimiter.js  # Rate limiting
│   ├── firebase.js         # Firebase Admin SDK init
│   └── package.json
├── firebase.json           # Firebase Hosting + Functions config
├── .firebaserc             # Firebase project config
└── README.md
```

## Tech Stack
- **Frontend**: HTML5, CSS3, Vanilla JS
- **Backend**: Node.js 18 + Express 4
- **Database**: Firebase Realtime Database
- **Storage**: Firebase Storage (images)
- **Auth**: JWT (jsonwebtoken)
- **Deploy**: Firebase Hosting (frontend) + Firebase Functions (backend API)

## Setup & Deploy

### 1. Install Firebase CLI
```bash
npm install -g firebase-tools
firebase login
```

### 2. Install backend dependencies
```bash
cd backend
npm install
```

### 3. Set environment variables
```bash
firebase functions:secrets:set ADMIN_PASSWORD
firebase functions:secrets:set JWT_SECRET
```

### 4. Deploy everything
```bash
firebase deploy
```

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/auth/login | Admin login → JWT |
| GET | /api/products | Get all products |
| POST | /api/products | Create product (auth) |
| PUT | /api/products/:id | Update product (auth) |
| DELETE | /api/products/:id | Delete product (auth) |
| POST | /api/orders | Save new order |
| GET | /api/orders | Get all orders (auth) |
| POST | /api/media/upload | Upload + compress image (auth) |
