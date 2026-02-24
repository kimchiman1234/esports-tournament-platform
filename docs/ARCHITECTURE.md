# System Architecture

## Overview
The Esports Tournament Platform is built with a microservices architecture consisting of:
- **Frontend**: React-based user interface
- **Backend**: Node.js/Express API server
- **Database**: MongoDB for data persistence
- **Payment**: Stripe integration for payment processing
- **Gaming API**: Riot Games API integration for League of Legends data

## Tech Stack

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB
- **Authentication**: JWT
- **Payment Processing**: Stripe API
- **External APIs**: Riot Games API

### Frontend
- **Framework**: React
- **State Management**: Redux (Phase 2)
- **UI Library**: Material-UI (Phase 2)
- **HTTP Client**: Axios

## Database Schema

### Collections
1. **Users**
   - Email, password hash, riot PUUID
   - Age verification, KYC status
   - Wallet balance, transaction history

2. **Tournaments**
   - Tournament details, entry fee, prize pool
   - Status (open, in-progress, completed)
   - Participants list

3. **Matches**
   - Match ID, participants, teams
   - Start time, end time, winner
   - Dispute status

4. **Transactions**
   - User ID, amount, type
   - Stripe transaction ID
   - Status (pending, completed, failed)

## API Endpoints (MVP)

### Authentication
- POST /api/auth/register
- POST /api/auth/login
- POST /api/auth/riot-oauth

### Tournaments
- GET /api/tournaments
- POST /api/tournaments
- POST /api/tournaments/:id/join
- GET /api/tournaments/:id

### Matchmaking
- POST /api/matchmaking/queue/join
- GET /api/matchmaking/queue/:id
- POST /api/matchmaking/queue/:id/leave

### Matches
- GET /api/matches/:id
- POST /api/matches/:id/report
- POST /api/matches/:id/dispute

### Payments
- POST /api/payments/process
- GET /api/payouts
- POST /api/payouts/request

## Deployment
- **Backend**: AWS EC2 / Heroku
- **Frontend**: Vercel / Netlify
- **Database**: MongoDB Atlas
- **CDN**: CloudFront (Phase 2)