# Wedding Template + Dashboard (Original ZIP retained)

This project preserves the original `wedding-template.zip` visuals and all 21 images, and adds a dynamic admin editor, SQLite-backed RSVP/wishes, and QRIS/bank gift cards.

## Deploy
- Upload the **contents of this folder** to the root of your existing GitHub repository (not the ZIP file as a single repository file). Keep `public/assets/` intact.
- Railway service should build Node 20+ and run `npm start`.
- Set `ADMIN_PASSWORD` to a strong private password and `SESSION_SECRET` to a random 32+ character string in Railway Variables. Do not commit these values.
- Add a Railway persistent volume mounted at `/data`, and set `DB_PATH=/data/wedding.db` **before production use**. If migrating from an existing SQLite DB, back it up and migrate its data before switching paths.
- The dashboard is `/admin`; invitation is `/`.

## Notes
- The original visuals and image files are included. No MP3 was supplied in the source ZIP. Add music only if you have permission to use it.
- The dashboard edits image **paths/URLs**, not binary uploads. For phone-based direct media uploads, a cloud storage service and upload endpoint must be added.
- QRIS and bank transfer are informational; the website does not verify payments.
- Only tokenized guest URLs can submit a tracked RSVP. Public visitors can submit wishes.
- This is an MVP; before a public high-traffic event, add rate limiting, CSRF protection, persistent sessions, backups and spam moderation.
- Current default names and details are sample placeholders; replace them in `/admin`.
