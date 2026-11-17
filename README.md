# Wedding Invitation MVP

Website undangan digital Modern Minimalist dengan dashboard admin, daftar tamu, RSVP, ucapan, editor konten dan ekspor CSV.

## Local

1. Install Node.js 20+.
2. `npm install`
3. Copy `.env.example` to `.env`; set strong `ADMIN_PASSWORD` and random `SESSION_SECRET` (32+ chars).
4. `npm start`
5. Open `/` for invitation and `/admin` for dashboard.

## Railway

Set `ADMIN_PASSWORD`, `SESSION_SECRET`, `NODE_ENV=production`, `DB_PATH=/data/wedding.db`. Add persistent volume at `/data`. Start command: `npm start`. Use HTTPS. **Before production:** replace Express default in-memory session store with persistent store, add login rate limiting, CSRF protection, anti-spam and database backups. Do not commit `.env` or real guest data.

## Features

Personalized invitation `/?to=TOKEN`, RSVP, guest list, CSV export, public wishes, content editing. QR check-in, Excel import, photo uploads and mass WhatsApp are future enhancements.
