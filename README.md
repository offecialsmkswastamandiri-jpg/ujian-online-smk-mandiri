# Ujian Online SMK Swasta Mandiri

Starter application for Supabase + Vercel, with Blogger as the school portal and PWA support.

## Included
- Supabase Auth email/password login and profile-role checks.
- Dashboard and CRUD screens for subjects, question banks, exams, sessions, participants/tokens, and announcements.
- Question editor, separate private answer-key RPC, question approval, and exam question mapping.
- Student exam list, server-side start/save/submit RPC workflow, timer deadline display, and objective grading on submission.
- Proctor attempt overview, results CSV export, school branding settings, Excel/CSV question import preview, student template download.
- AI question-generation UI and server endpoint guarded by Supabase Auth profile checks.
- PWA manifest, app icon, and service worker.

## Important implementation limits
This is an initial runnable application package, not a claim that every requested production feature is complete. Full student account provisioning from Excel, printable participant cards/QR, PDF reports, item discrimination analysis, detailed live proctor event workflow, complete rubric-based AI essay review, scheduled auto-submit worker, and offline answer queue are not end-to-end implemented yet. The current exam submit RPC automatically scores exact JSONB matches for non-essay questions; multiple-select normalization and teacher-finalized essay grading need further work before official use.

The AI endpoint requires `OPENAI_API_KEY` in Vercel Environment Variables. No secret is included in this package. The Supabase publishable key is public by design; never add a service-role key to frontend code.

## Run locally
1. Install Node.js 20+.
2. `npm install`
3. `npm run dev`
4. Open the URL printed by Vite.

## Supabase target
Project: `yhcswjsoshlxmeegzxyl` (`PortalSMKSMandri`). The implementation session applied database migrations for security lockdown and the exam platform core. See `database/README.md`.

Supabase Auth must contain a user with an active matching row in `public.profiles`. Existing custom-password LMS users were not automatically converted to Supabase Auth.

## Deploy
See `DEPLOYMENT.md`. The Vercel connector returned HTTP 403 for deployment operations due to an authorization/scope mismatch; deployment is not verified online yet.
