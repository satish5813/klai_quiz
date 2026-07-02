# KL AI QuizApp — Student Client

The student-facing exam web app (React + Vite). It talks to the exam **API** (Express + MySQL)
hosted separately on the Hostinger VPS.

## Configure the API URL
The client reads `VITE_API_URL`. It's set in `.env` (committed, public URL — not a secret):

```
VITE_API_URL=https://p3azuzswx8ewrgojju6xhm1k.187.127.135.148.sslip.io
```

On Vercel you can also set `VITE_API_URL` in Project → Settings → Environment Variables
(the dashboard value overrides `.env`).

## Deploy on Vercel
1. Import this repo into Vercel (framework auto-detected: **Vite**; `vercel.json` is included).
2. Ensure env `VITE_API_URL` points to the live API (already in `.env`).
3. Deploy. Students open the Vercel URL → enter registration number → take the exam.

## Local dev
```
npm install
npm run dev        # http://localhost:5180 (proxies /api → localhost:4000 in dev)
npm run build      # production build → dist/
```

Scales to thousands of students: the client is a static bundle on Vercel's CDN; all exam
logic/state lives in the API + MySQL on the VPS.
