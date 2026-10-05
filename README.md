# MeetSpace — Real-Time Communication & Collaboration

CodeAlpha Task 4 implementation with multi-user WebRTC video, screen sharing, file sharing, collaborative whiteboard, JWT authentication, Socket.IO signaling, and PostgreSQL-backed users.

## Stack
- React + Vite
- Express
- Socket.IO
- WebRTC mesh topology
- PostgreSQL + bcrypt + JWT
- Canvas whiteboard

## Local setup
1. Install Node.js 20+ and PostgreSQL.
2. Run `npm install`.
3. Copy `.env.example` to `.env`.
4. Set `DATABASE_URL` and a strong `JWT_SECRET`.
5. Run `npm run dev`.
6. Open `http://localhost:5173` in two browser windows and join the same room.

## Railway
Use a Railway PostgreSQL service and app service. Set `DATABASE_URL`, `JWT_SECRET`, and `PUBLIC_URL`. Build command: `npm run build`. Start command: `npm start`. The Express server serves the Vite `dist` folder.

### WebRTC production note
Browser WebRTC media uses DTLS-SRTP encryption. HTTPS/WSS is required in production. For restrictive networks, configure a TURN server with `TURN_URL`, `TURN_USERNAME`, and `TURN_CREDENTIAL`.

The current architecture is a peer-to-peer mesh, best suited to small rooms. Larger rooms should use an SFU.
