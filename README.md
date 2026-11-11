# SafetyReport — simple aviation voluntary reporting portal

A small Next.js application with a public voluntary reporting form and a server-side Supabase insert endpoint.

## 1. Prerequisites
- Node.js 20.9 or later
- A Supabase project
- A Vercel account and GitHub repository

## 2. Set up Supabase
1. Create a Supabase project.
2. Open SQL Editor.
3. Run `supabase/schema.sql`.
4. Open Project Settings > API.
5. Copy the Project URL and the `service_role` secret key. Keep the service role key private.

## 3. Run locally
```bash
npm install
cp .env.example .env.local
```
Add values to `.env.local`:
```env
NEXT_PUBLIC_SUPABASE_URL=https://YOUR-PROJECT.supabase.co
SUPABASE_SERVICE_ROLE_KEY=YOUR_SERVICE_ROLE_SECRET
```
Then:
```bash
npm run dev
```
Open http://localhost:3000.

## 4. Deploy to Vercel
1. Upload the CONTENTS of this folder to the ROOT of a GitHub repository.
2. In Vercel, import that repository.
3. Framework preset: Next.js. Root Directory: `./`.
4. Add `NEXT_PUBLIC_SUPABASE_URL` and `SUPABASE_SERVICE_ROLE_KEY` in Project Settings > Environment Variables (Production, Preview as appropriate).
5. Deploy.

## Important limitations
This is a minimal submission prototype. It does not include an administrator dashboard, reporter follow-up workflow, file uploads, rate limiting, email notifications, or a completed identity-separation design. The public form can submit reports, but there is no user-facing report retrieval. Do not use it for real or sensitive operational reports until a security review, access-controlled case-management interface, retention policy, anti-abuse controls, and applicable legal/privacy review are completed. Do not publish the service-role key or put it in any `NEXT_PUBLIC_` variable.
