# Audit Staff Booking — Supabase + GitHub + Netlify

## Setup
1. Create a Supabase project.
2. Supabase > SQL Editor > run `supabase/schema.sql`.
3. Supabase > Authentication > Users: create login users.
4. Insert each user's profile in `profiles`, for example:
   `insert into public.profiles(id,full_name,role) values('AUTH-USER-UUID','Admin User','admin');`
5. For staff users, also insert a matching row in `staff` with `user_id` set to the Auth user's UUID.
6. Copy `.env.example` to `.env.local` and fill the Supabase URL + anon key.
7. Run locally: `npm install` then `npm run dev`.
8. Push to GitHub.
9. Netlify > Add new site > Import from Git. Build command `npm run build`, publish directory `dist`.
10. Add Netlify environment variables `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY`.

Roles: admin, manager, staff, viewer.

Never expose a Supabase service-role key in frontend code or Netlify public variables.
